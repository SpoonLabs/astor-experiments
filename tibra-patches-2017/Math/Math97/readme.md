
# Patches of Math97 from Defects4J 
Total patches 5
## Patch 1 of bug id Math97
### Patch Diff Hash-SHA-256:

5b5f608b6459ef85ada2e01e532f65003ad571f47ca3d8dd0f88131d4e6f8bd7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -38,6 +38,10 @@
 
 	public double solve(double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
 		clearResult();
+		if ((java.lang.Math.abs((max - (result)))) <= (absoluteAccuracy)) {
+			setResult(max, defaultMaximalIterationCount);
+			return max;
+		}
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
```


---
## Patch 2 of bug id Math97
### Patch Diff Hash-SHA-256:

e66a9662d5c678dc0396bb5b6cf5cce0063d72bb88b33651f9ced672be05a92c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -38,6 +38,7 @@
 
 	public double solve(double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
 		clearResult();
+		max += absoluteAccuracy;
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
@@ -66,13 +67,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---
## Patch 3 of bug id Math97
### Patch Diff Hash-SHA-256:

df9cf33fb73c3617a08e326ad2863cd50f8a09ca7aa2eb10c514ca08a0977505

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -41,6 +41,7 @@
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
+		max += defaultAbsoluteAccuracy;
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
 		if (sign >= 0) {
@@ -66,13 +67,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---
## Patch 4 of bug id Math97
### Patch Diff Hash-SHA-256:

0aea14ea990040da7f59f708756b1a0e6c76bb8ff7ea883c8c66e7b226957c1b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -40,6 +40,9 @@
 		clearResult();
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
+		while ((max == (functionValueAccuracy)) || (max == (result))) {
+			max += absoluteAccuracy;
+		} 
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
@@ -66,13 +69,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---
## Patch 5 of bug id Math97
### Patch Diff Hash-SHA-256:

ebfb6666819925a34582374a0648c270235c856b18f780880245beb279976e0e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -40,6 +40,9 @@
 		clearResult();
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
+		while ((max == (defaultAbsoluteAccuracy)) || (max == (result))) {
+			max += absoluteAccuracy;
+		} 
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
@@ -66,13 +69,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---