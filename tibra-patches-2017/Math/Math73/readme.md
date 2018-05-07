
# Patches of Math73 from Defects4J 
Total patches 19
## Patch 1 of bug id Math73
### Patch Diff Hash-SHA-256:

1c88f9c34b825048ce87b8410b396cc3f6d8d25941079a32a81aed8ca752f06c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 2 of bug id Math73
### Patch Diff Hash-SHA-256:

2976b12933de5bcc438e2662e21992a5a51b8bdac2f8e358f614e05714232a80

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -38,6 +38,7 @@
 			setResult(yMin, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
```


---
## Patch 3 of bug id Math73
### Patch Diff Hash-SHA-256:

27111512247dd0f6501e2229a496ecea92b9ec19565869798d069449e4a15a28

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -38,6 +38,9 @@
 			setResult(yMin, 0);
 			return result;
 		}
+		if ((yInitial * (defaultFunctionValueAccuracy)) >= 0) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(("function values at endpoints do not have different signs, " + "endpoints: [{0}, {1}], values: [{2}, {3}]"), min, max, yInitial, defaultFunctionValueAccuracy);
+		}
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
```


---
## Patch 4 of bug id Math73
### Patch Diff Hash-SHA-256:

702439bb9e6ae43ec9acbd850a29e2295cdb0b2e3462e27b19a5cef4fdd2a041

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,29 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if (yInitial > 0) {
+			if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+				setResult(min, 0);
+				defaultAbsoluteAccuracy = min;
+			}else
+				if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
+					setResult(max, 0);
+					defaultAbsoluteAccuracy = max;
+				}else {
+					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
+				}
+
+		}else
+			if (yInitial < 0) {
+				defaultAbsoluteAccuracy = solve(f, min, yMin, max, yMax, min, yMin);
+			}else {
+				if (yMin == 0.0) {
+					defaultAbsoluteAccuracy = min;
+				}else {
+					defaultAbsoluteAccuracy = max;
+				}
+			}
+
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 5 of bug id Math73
### Patch Diff Hash-SHA-256:

7e2777df01786b69fb064c28d95d0b5a59718759473b80c888e093981886bdfe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -34,9 +34,8 @@
 			return result;
 		}
 		double yMin = f.value(min);
-		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
-			setResult(yMin, 0);
-			return result;
+		if (!(isBracketing(min, absoluteAccuracy, f))) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(("function values at endpoints do not have different signs.  " + "Endpoints: [{0}, {1}], Values: [{2}, {3}]"), min, absoluteAccuracy, f.value(min), f.value(absoluteAccuracy));
 		}
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
```


---
## Patch 6 of bug id Math73
### Patch Diff Hash-SHA-256:

2dfffb00750c3615b677f650131fce4d346b1117e7cd067ab66064df85adc51e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -26,7 +26,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(relativeAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```


---
## Patch 7 of bug id Math73
### Patch Diff Hash-SHA-256:

8615828a2130833722610a0d81b169194fb6a42d38afc06b42f2225b95dcfbb7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,9 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if ((iterationCount) <= 0) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("bad value for maximum iterations number: {0}", iterationCount);
+		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 8 of bug id Math73
### Patch Diff Hash-SHA-256:

e2d15978b83d65541cd0618d6db3d8bdd4abf7a9a9a361df2d6f6f55c218995c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -46,8 +46,8 @@
 			setResult(yMax, 0);
 			return result;
 		}
-		if ((yInitial * yMax) < 0) {
-			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
+		if (initial >= yMax) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("endpoints do not specify an interval: [{0}, {1}]", initial, yMax);
 		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 9 of bug id Math73
### Patch Diff Hash-SHA-256:

738ad3a9fe761061aaa0a81abc740b4aa3e8d1ede98302304160cc60768dbae0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,9 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if (!(isSequence(defaultFunctionValueAccuracy, initial, min))) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("invalid interval, initial value parameters:  lower={0}, initial={1}, upper={2}", defaultFunctionValueAccuracy, initial, min);
+		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 10 of bug id Math73
### Patch Diff Hash-SHA-256:

c831129b70fce92b0fdd9fd2b277e53154bba117877f58c3d872d49677e0a625

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 11 of bug id Math73
### Patch Diff Hash-SHA-256:

a15a0a88503bc188349f3d1358ae08be05919848d9a5c67c48013f29d7bc4639

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(this.f, min, max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 12 of bug id Math73
### Patch Diff Hash-SHA-256:

91f39b0dc14d24fabc0f564ed78a3a02181fa0783467a15fbf98abbcdc81d6d4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		verifyBracketing(min, max, f);
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 13 of bug id Math73
### Patch Diff Hash-SHA-256:

328b00f3a0aba1d851e79ee924bfa3f00d2607fac55b11d03584c5f994d6ad71

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(this.f, min, max, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 14 of bug id Math73
### Patch Diff Hash-SHA-256:

f35b007a0281f69a645c6f65a7e37f58258ed162aa8a87903d456164c666f3a0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -117,6 +117,9 @@
 				double p1;
 				if (x0 == x2) {
 					p = dx * r3;
+					if ((y0 * y1) >= 0) {
+						throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(("function values at endpoints do not have different signs, " + "endpoints: [{0}, {1}], values: [{2}, {3}]"), functionValue, dx, y0, y1);
+					}
 					p1 = 1.0 - r3;
 				}else {
 					double r1 = y0 / y2;
```


---
## Patch 15 of bug id Math73
### Patch Diff Hash-SHA-256:

d1bad4c923ab93fe2b613e94bb2e558f3751d73c09e1545897dc2146ea7ce8eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		verifySequence(min, absoluteAccuracy, max);
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 16 of bug id Math73
### Patch Diff Hash-SHA-256:

6ba0fc5e1098d0fae919d6426de21b5c6dd2dbc6af75960199b58cd9f7a3451f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,9 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if (!(isSequence(yMax, initial, yInitial))) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("invalid interval, initial value parameters:  lower={0}, initial={1}, upper={2}", yMax, initial, yInitial);
+		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 17 of bug id Math73
### Patch Diff Hash-SHA-256:

32aad8f910f411512a8ce5b0227c10a5d2f2df2fcf7b8c748a4fc280acf50b0d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -26,7 +26,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(min, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```


---
## Patch 18 of bug id Math73
### Patch Diff Hash-SHA-256:

27057eca6f3577312e937e093d6cef3a46f25575c68b1299f1604fb39dd7a287

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(this.f, min, max, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 19 of bug id Math73
### Patch Diff Hash-SHA-256:

41e6e38474b632c0b99b74243dd20ccbfcd728567b87bc7413e577ce2f16fbd3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -34,6 +34,7 @@
 			return result;
 		}
 		double yMin = f.value(min);
+		verifyBracketing(min, max, f);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
 			return result;
```


---