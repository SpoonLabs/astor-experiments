
# Patches of Math73 from Defects4J 
Total patches 10
## Patch 1 of bug id Math73
### Patch Diff Hash-SHA-256:

fc6c66cb7d6c2e485e64f163c8911a7742ece23857ed1d1b1856ce836075092a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,6 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		verifyBracketing(min, max, f);
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 2 of bug id Math73
### Patch Diff Hash-SHA-256:

be03ce6fb61e671dbfb2ce3eace729e5b33a09da0ed19b28f0070374f95223d7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 3 of bug id Math73
### Patch Diff Hash-SHA-256:

6169208900ea8e481adc32c24cf95dc7119811bbcc84ef9f7d54fd018dbe71c2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 4 of bug id Math73
### Patch Diff Hash-SHA-256:

26b8bde6fbf8002ffa55f9f86953c519f981199de2368fa080319e90b477075d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 5 of bug id Math73
### Patch Diff Hash-SHA-256:

7b1e9239dd73db3794bb8324f3279016517036278d867c0da428aeea5193956f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,6 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
+		verifyBracketing(min, max, f);
 		double yMax = f.value(max);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
```


---
## Patch 6 of bug id Math73
### Patch Diff Hash-SHA-256:

9e3b4de696e3bed2ce1edf50eede88d55538cb64591452bd888aa6ef34fcb732

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,7 @@
 			setResult(initial, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
```


---
## Patch 7 of bug id Math73
### Patch Diff Hash-SHA-256:

d1c2d4467e868c9c0bee6551a6541dd6b3965e0ddaf2fe188f0b616b7a14584a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -40,6 +40,7 @@
 			setResult(yMin, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
```


---
## Patch 8 of bug id Math73
### Patch Diff Hash-SHA-256:

f03e6f3977a1fdb8ac8f0f7fa8654494bb41876ab650fc8a34cfe749a8aac086

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 			return result;
 		}
 		double yMin = f.value(min);
+		verifyBracketing(min, max, f);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
 			return result;
```


---
## Patch 9 of bug id Math73
### Patch Diff Hash-SHA-256:

103006e353c2d1eb1b89b5f52e3615bd813cbd346cd88dbd52b48455e2bc3188

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -48,6 +48,7 @@
 			setResult(yMax, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
```


---
## Patch 10 of bug id Math73
### Patch Diff Hash-SHA-256:

ad5f0297dd7deacf74ea2306bdb57264cac8c62e6a80cfd6450d2435967596ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -44,6 +44,7 @@
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
 		double yMax = f.value(max);
+		verifyBracketing(min, max, f);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```


---