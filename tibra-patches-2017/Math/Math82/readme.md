
# Patches of Math82 from Defects4J 
Total patches 8
## Patch 1 of bug id Math82
### Patch Diff Hash-SHA-256:

37fcda00169ed74bc9f3588ce75e76dc2d80c30aec6e5c4c283121058003d13f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				this.f = f;
 				minPos = i;
 			}
 		}
```


---
## Patch 2 of bug id Math82
### Patch Diff Hash-SHA-256:

fdd307c86c444fe2ecbfb66b79fbe0dee2a623724676b19fafd5db7594429d6b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minValue = minValue;
 				minPos = i;
 			}
 		}
```


---
## Patch 3 of bug id Math82
### Patch Diff Hash-SHA-256:

0dd8aab49dc13f94fdc259f9d9f1ac8270e2779605e939ac7916cceb3ca917dc

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minPos = org.apache.commons.math.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS;
 				minPos = i;
 			}
 		}
```


---
## Patch 4 of bug id Math82
### Patch Diff Hash-SHA-256:

a089c4fdeafd1428fd7fa220f133ab37c70d717be3e1254224db3aeb091f3c17

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -18,10 +18,9 @@
 		double minValue = 0;
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
-			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0)
 				minPos = i;
-			}
+
 		}
 		return minPos;
 	}
```


---
## Patch 5 of bug id Math82
### Patch Diff Hash-SHA-256:

e861f974d021eafa9ca6a7a410cae59148a1d232c5bcaf8138dffb6b9127ccd2

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				this.constraints = constraints;
 				minPos = i;
 			}
 		}
```


---
## Patch 6 of bug id Math82
### Patch Diff Hash-SHA-256:

d80a656eed9c7566fea16d3a2f0ed74f63cc27f061861fa85fd5e4b5d877af5e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minValue = DEFAULT_EPSILON;
 				minPos = i;
 			}
 		}
```


---
## Patch 7 of bug id Math82
### Patch Diff Hash-SHA-256:

f57b392ed0d741c011bee8e9ee137ff7f71ff76ae9f9beb5a0ac33c35a0bf5a5

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -18,10 +18,9 @@
 		double minValue = 0;
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
-			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0)
 				minPos = i;
-			}
+
 		}
 		return minPos;
 	}
@@ -98,7 +97,7 @@
 
 	@java.lang.Override
 	public org.apache.commons.math.optimization.RealPointValuePair doOptimize() throws org.apache.commons.math.optimization.OptimizationException {
-		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, constraints, goalType, restrictToNonNegative, epsilon);
+		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, this.constraints, goalType, restrictToNonNegative, epsilon);
 		solvePhase1(tableau);
 		tableau.discardArtificialVariables();
 		while (!(isOptimal(tableau))) {
```


---
## Patch 8 of bug id Math82
### Patch Diff Hash-SHA-256:

4686a537ba6445684d123fd11a24ed2470ecddc650bb6a0a601b8eb637d912bb

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -20,6 +20,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
 				minValue = tableau.getEntry(0, i);
+				minValue -= minValue;
 				minPos = i;
 			}
 		}
@@ -98,7 +99,7 @@
 
 	@java.lang.Override
 	public org.apache.commons.math.optimization.RealPointValuePair doOptimize() throws org.apache.commons.math.optimization.OptimizationException {
-		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, constraints, goalType, restrictToNonNegative, epsilon);
+		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, this.constraints, goalType, restrictToNonNegative, epsilon);
 		solvePhase1(tableau);
 		tableau.discardArtificialVariables();
 		while (!(isOptimal(tableau))) {
```


---