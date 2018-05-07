
# Patches of Math78 from Defects4J 
Total patches 9
## Patch 1 of bug id Math78
### Patch Diff Hash-SHA-256:

d82cd2aacb90b7c92b3de99926d90530d781506cd4a1f5a31d99dbdea69a7339

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,6 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
+			final double t0 = interpolator.getPreviousTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
```


---
## Patch 2 of bug id Math78
### Patch Diff Hash-SHA-256:

6a834048d1cc66e056c6ecc1f7c0b875e6669f0650045397cc8543bd77c5232d

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -70,6 +70,7 @@
 	public boolean evaluateStep(final org.apache.commons.math.ode.sampling.StepInterpolator interpolator) throws org.apache.commons.math.ConvergenceException, org.apache.commons.math.ode.DerivativeException, org.apache.commons.math.ode.events.EventException {
 		try {
 			forward = interpolator.isForward();
+			final double t0 = interpolator.getPreviousTime();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
```


---
## Patch 3 of bug id Math78
### Patch Diff Hash-SHA-256:

75f4b24af1d4e591072a972990fa71be4b4fe63e17fc64a7512a2e8c6d96d4b6

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -77,6 +77,7 @@
 			double ga = g0;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
 			for (int i = 0; i < n; ++i) {
+				ta = tb;
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
 				final double gb = handler.g(tb, interpolator.getInterpolatedState());
```


---
## Patch 4 of bug id Math78
### Patch Diff Hash-SHA-256:

f4e2c5dfe9995807cd70b63ccf034dc4ced72130431f83fef243b269893b79e1

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -73,6 +73,7 @@
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
+			final double t0 = interpolator.getPreviousTime();
 			double ta = t0;
 			double ga = g0;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
```


---
## Patch 5 of bug id Math78
### Patch Diff Hash-SHA-256:

055000c32bd3c0a225ab04bffdd554831a7ccf2fa659778d7b3d46766e559034

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -72,6 +72,7 @@
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			final double t0 = interpolator.getPreviousTime();
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```


---
## Patch 6 of bug id Math78
### Patch Diff Hash-SHA-256:

a0ca07e4f7e62ec66974ec3abf78efebc8220ce610e19d49507c18aacc501d9b

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -69,6 +69,7 @@
 
 	public boolean evaluateStep(final org.apache.commons.math.ode.sampling.StepInterpolator interpolator) throws org.apache.commons.math.ConvergenceException, org.apache.commons.math.ode.DerivativeException, org.apache.commons.math.ode.events.EventException {
 		try {
+			final double t0 = interpolator.getPreviousTime();
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
```


---
## Patch 7 of bug id Math78
### Patch Diff Hash-SHA-256:

a45ed2d440f50621e71e5f0ed2689e1c10bea10bc6d7fd2983f2802a138039d2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -155,6 +155,7 @@
 				x2 = x0;
 				y2 = y0;
 				delta = x1 - x0;
+				delta = 0.5 * oldDelta;
 				oldDelta = delta;
 			}
 			i++;
```


---
## Patch 8 of bug id Math78
### Patch Diff Hash-SHA-256:

392367a8a7c0bda67202fb47c9effd3be699b56d1beaef35357b4e56b719b498

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -76,6 +76,7 @@
 			double ta = t0;
 			double ga = g0;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
+			ta = tb;
 			for (int i = 0; i < n; ++i) {
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
```


---
## Patch 9 of bug id Math78
### Patch Diff Hash-SHA-256:

5580ffc13a373e0f907695693604f59311a13d9d87f9dd8a9c6cf2377a2ea910

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = 0.5 * oldDelta;
 				oldDelta = delta;
 			}
 			i++;
```


---