
# Patches of Math78 from Defects4J 
Total patches 13
## Patch 1 of bug id Math78
### Patch Diff Hash-SHA-256:

61d92b523b53fd4400b7e5594fad6f776385fef400a67d5e35826d078ab3c022

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -131,7 +131,7 @@
 				}
 				if (((2.0 * p) >= (((1.5 * dx) * p1) - (java.lang.Math.abs((tolerance * p1))))) || (p >= (java.lang.Math.abs(((0.5 * oldDelta) * p1))))) {
 					delta = 0.5 * dx;
-					oldDelta = delta;
+					y1 = y1 + (0.5 * y1);
 				}else {
 					oldDelta = delta;
 					delta = p / p1;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math78
### Patch Diff Hash-SHA-256:

e509ad23cc762d2bedc7e9a57a6031d843ff0f0f11a34f930e5641336833b9c3

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,7 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
-			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((interpolator.getCurrentTime()) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math78
### Patch Diff Hash-SHA-256:

3339363937cc3e4c7880c02e838ba266cc3b64ae3545924a6b724cefccda7311

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,7 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
-			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs(((convergence) - t1))) / (pendingEventTime))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math78
### Patch Diff Hash-SHA-256:

034ebe851f2390581b75aca3fb6b48d6b41c2e131d8b3eac1a000b75a8cd4dfd

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,7 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
-			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs(((pendingEventTime) - t1))) / (convergence))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math78
### Patch Diff Hash-SHA-256:

9cabe8feab82f4bd18ed1fbdb80df00782e59696e75d13fe3f953fb28184def1

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,7 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
-			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (convergence)))) / (pendingEventTime))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math78
### Patch Diff Hash-SHA-256:

44c5fb3f2b9ccdd34f3c501800ff5ef43724d56ec4111cd058e50ebaf1d8fe1a

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,7 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
-			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (pendingEventTime)))) / (convergence))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math78
### Patch Diff Hash-SHA-256:

1b1af128d55fef9241a69b54d29fbd445c17b60221b87b651f7d6a3c0ad4e53b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = (((functionValueAccuracy) - 1.0) * ((functionValueAccuracy) - 1.0)) * ((functionValueAccuracy) - 1.0);
 				oldDelta = delta;
 			}
 			i++;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math78
### Patch Diff Hash-SHA-256:

c37a84f6a6c866671bdcd19807d1986565034e669874289f7f6c8b915514a828

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = x1 / x1;
 				oldDelta = delta;
 			}
 			i++;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math78
### Patch Diff Hash-SHA-256:

10c3cd73cfc35e0bbda789cebdf4dbaba06a0145a09e7a47014ca0ad335d59f1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = ((functionValueAccuracy) - 1.0) * ((functionValueAccuracy) - 1.0);
 				oldDelta = delta;
 			}
 			i++;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math78
### Patch Diff Hash-SHA-256:

9d4adc0e532092f34f249f958d0bc5d54b900c66a343c65114ed6549c99f8339

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = (functionValueAccuracy) / (functionValueAccuracy);
 				oldDelta = delta;
 			}
 			i++;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math78
### Patch Diff Hash-SHA-256:

02c29737b38b1ffb241fbe8feb1d3358ecdbad96cee8d946d4453cd38e0439fd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = 1.0 - (functionValueAccuracy);
 				oldDelta = delta;
 			}
 			i++;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math78
### Patch Diff Hash-SHA-256:

41f1f1fc80e196cb03ae5445e93bb758a85f9334607467dfd583df8a5231951b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -119,7 +119,7 @@
 					p = dx * r3;
 					p1 = 1.0 - r3;
 				}else {
-					double r1 = y0 / y2;
+					double r1 = -delta;
 					double r2 = y1 / y2;
 					p = r3 * (((dx * r1) * (r1 - r2)) - ((x1 - x0) * (r2 - 1.0)));
 					p1 = ((r1 - 1.0) * (r2 - 1.0)) * (r3 - 1.0);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math78
### Patch Diff Hash-SHA-256:

13591ef4ebd5e1a2b6a73c6f8f4ddab573eb31c16cf067682d885f6ed4767496

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = delta / delta;
 				oldDelta = delta;
 			}
 			i++;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---