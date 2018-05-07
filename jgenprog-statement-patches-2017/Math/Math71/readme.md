
# Patches of Math71 from Defects4J 
Total patches 7
## Patch 1 of bug id Math71
### Patch Diff Hash-SHA-256:

6fd3b56ad870203ac3e4947d92a8fdf040b35bf53cf832676b470b0755528a32

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -80,6 +80,9 @@
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
 				final double gb = handler.g(tb, interpolator.getInterpolatedState());
+				if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
+					return false;
+				}
 				if ((g0Positive) ^ (gb >= 0)) {
 					if ((ga * gb) > 0) {
 						final double epsilon = (forward ? 0.25 : -0.25) * (convergence);
```


---
## Patch 2 of bug id Math71
### Patch Diff Hash-SHA-256:

95b9aeafe336253e5e5b3bf601bb232441a7b5e69d24646fc2b353ee8fe07515

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -93,6 +93,7 @@
 						}
 					}
 					increasing = gb >= ga;
+					pendingEvent = true;
 					final org.apache.commons.math.analysis.UnivariateRealFunction f = new org.apache.commons.math.analysis.UnivariateRealFunction() {
 						public double value(final double t) throws org.apache.commons.math.FunctionEvaluationException {
 							try {
```


---
## Patch 3 of bug id Math71
### Patch Diff Hash-SHA-256:

86917fc8afb925d331e5c1f6c8f3c758abd8ed61b3c2e409ba004d83e5c710c0

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -72,6 +72,7 @@
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			pendingEvent = true;
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```


---
## Patch 4 of bug id Math71
### Patch Diff Hash-SHA-256:

a2acc33707c1edd61ed28a2f886529e52f280b6677e7d606cab293b0f9e11eb8

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,6 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
+			pendingEvent = true;
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
```


---
## Patch 5 of bug id Math71
### Patch Diff Hash-SHA-256:

161877ad531298f0ec12b4b3ac6ef3b8a7719971fece3b1e2638a6ac79997cf5

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -109,6 +109,9 @@
 					solver.setAbsoluteAccuracy(convergence);
 					solver.setMaximalIterationCount(maxIterationCount);
 					final double root = ta <= tb ? solver.solve(f, ta, tb) : solver.solve(f, tb, ta);
+					if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
+						return false;
+					}
 					if (((java.lang.Math.abs((root - ta))) <= (convergence)) && ((java.lang.Math.abs((root - (previousEventTime)))) <= (convergence))) {
 						ta = tb;
 						ga = gb;
```


---
## Patch 6 of bug id Math71
### Patch Diff Hash-SHA-256:

19a2db8c937466a2544a8f442fb4fca284c4c6fb2869acec388da693262a714d

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -75,6 +75,7 @@
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
+			pendingEvent = true;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
 			for (int i = 0; i < n; ++i) {
 				tb += h;
```


---
## Patch 7 of bug id Math71
### Patch Diff Hash-SHA-256:

c38c38cd1b2222fbd276db68aaf60d8dc582c2a91bba6169d9e7a01af8ca2823

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -112,7 +112,10 @@
 					if (((java.lang.Math.abs((root - ta))) <= (convergence)) && ((java.lang.Math.abs((root - (previousEventTime)))) <= (convergence))) {
 						ta = tb;
 						ga = gb;
-					}else
+					}else {
+						if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
+							return false;
+						}
 						if ((java.lang.Double.isNaN(previousEventTime)) || ((java.lang.Math.abs(((previousEventTime) - root))) > (convergence))) {
 							pendingEventTime = root;
 							if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
@@ -121,7 +124,7 @@
 							pendingEvent = true;
 							return true;
 						}
-					
+					}
 				}else {
 					ta = tb;
 					ga = gb;
```


---