
# Patches of Math72 from Defects4J 
Total patches 12
## Patch 1 of bug id Math72
### Patch Diff Hash-SHA-256:

abd856aa857ba9c800ffda74f7e6f1cea7b4c1faf5f441aae9f1089db2813668

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -74,6 +74,76 @@
 					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
 				}
 
+			while ((iterationCount) < (maximalIterationCount)) {
+				if ((java.lang.Math.abs(absoluteAccuracy)) < (java.lang.Math.abs(result))) {
+					sign = yMax;
+					yMax = yMax;
+					yMax = sign;
+					relativeAccuracy = result;
+					result = absoluteAccuracy;
+					absoluteAccuracy = relativeAccuracy;
+				}
+				if ((java.lang.Math.abs(result)) <= (functionValueAccuracy)) {
+					setResult(yMax, iterationCount);
+					return result;
+				}
+				double dx = yMax - yMax;
+				double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(yMax))), absoluteAccuracy);
+				if ((java.lang.Math.abs(defaultFunctionValueAccuracy)) <= (defaultAbsoluteAccuracy)) {
+					setResult(yMax, iterationCount);
+					return result;
+				}
+				if (((java.lang.Math.abs(functionValueAccuracy)) < (defaultAbsoluteAccuracy)) || ((java.lang.Math.abs(relativeAccuracy)) <= (java.lang.Math.abs(result)))) {
+					functionValue = 0.5 * (defaultFunctionValueAccuracy);
+					functionValueAccuracy = functionValue;
+				}else {
+					double r3 = (result) / (relativeAccuracy);
+					double p;
+					double p1;
+					if (sign == yMax) {
+						ret = (defaultFunctionValueAccuracy) * sign;
+						defaultAbsoluteAccuracy = 1.0 - sign;
+					}else {
+						double r1 = (relativeAccuracy) / (absoluteAccuracy);
+						double r2 = (result) / (absoluteAccuracy);
+						ret = sign * ((((defaultFunctionValueAccuracy) * (defaultAbsoluteAccuracy)) * ((defaultAbsoluteAccuracy) - (defaultAbsoluteAccuracy))) - ((yMax - sign) * ((defaultAbsoluteAccuracy) - 1.0)));
+						defaultAbsoluteAccuracy = (((defaultAbsoluteAccuracy) - 1.0) * ((defaultAbsoluteAccuracy) - 1.0)) * (sign - 1.0);
+					}
+					if (ret > 0.0) {
+						defaultAbsoluteAccuracy = -(defaultAbsoluteAccuracy);
+					}else {
+						ret = -ret;
+					}
+					if (((2.0 * ret) >= (((1.5 * (defaultFunctionValueAccuracy)) * (defaultAbsoluteAccuracy)) - (java.lang.Math.abs(((defaultAbsoluteAccuracy) * (defaultAbsoluteAccuracy)))))) || (ret >= (java.lang.Math.abs(((0.5 * (functionValueAccuracy)) * (defaultAbsoluteAccuracy)))))) {
+						functionValue = 0.5 * (defaultFunctionValueAccuracy);
+						functionValueAccuracy = functionValue;
+					}else {
+						functionValueAccuracy = functionValue;
+						functionValue = ret / (defaultAbsoluteAccuracy);
+					}
+				}
+				sign = yMax;
+				relativeAccuracy = result;
+				if ((java.lang.Math.abs(functionValue)) > (defaultAbsoluteAccuracy)) {
+					yMax = yMax + (functionValue);
+				}else
+					if ((defaultFunctionValueAccuracy) > 0.0) {
+						yMax = yMax + (0.5 * (defaultAbsoluteAccuracy));
+					}else
+						if ((defaultFunctionValueAccuracy) <= 0.0) {
+							yMax = yMax - (0.5 * (defaultAbsoluteAccuracy));
+						}
+
+
+				result = f.value(yMax);
+				if (((result) > 0) == ((absoluteAccuracy) > 0)) {
+					yMax = sign;
+					absoluteAccuracy = relativeAccuracy;
+					functionValue = yMax - sign;
+					functionValueAccuracy = functionValue;
+				}
+				(iterationCount)++;
+			} 
 		}else
 			if (sign < 0) {
 				ret = solve(f, min, yMin, max, yMax, min, yMin);
```


---
## Patch 2 of bug id Math72
### Patch Diff Hash-SHA-256:

5be14423e0114409aa6e295ccef0462e9545d179799feb0a874fc18e93473365

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			absoluteAccuracy = ((java.lang.Math.abs(functionValueAccuracy)) > (java.lang.Math.abs(max))) ? functionValueAccuracy : max;
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 3 of bug id Math72
### Patch Diff Hash-SHA-256:

5b41a9dd07337ea3ee49190f30ff114ff69c0d0cdb368e4cf6ac613cb82762b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			absoluteAccuracy = java.lang.Double.POSITIVE_INFINITY;
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 4 of bug id Math72
### Patch Diff Hash-SHA-256:

a9e6f782611481864fa4a2d5d2fbeb86772c2e5aacac158d3831f1b56d6f6973

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -34,6 +34,7 @@
 			return result;
 		}
 		double yMin = f.value(min);
+		absoluteAccuracy = solve(f, min, yMin, max, defaultAbsoluteAccuracy, min, yMin);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
 			return result;
```


---
## Patch 5 of bug id Math72
### Patch Diff Hash-SHA-256:

e77c2c17a95e41242c76bcdf7c30f891c7a44cb2fffffe4c15db2c5fa8d58f87

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,17 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+				setResult(min, 0);
+				absoluteAccuracy = min;
+			}else
+				if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+					setResult(max, 0);
+					absoluteAccuracy = max;
+				}else {
+					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMin);
+				}
+
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 6 of bug id Math72
### Patch Diff Hash-SHA-256:

45ab09b9cf732f872d8c8492b5b7dae17f87e6df67375a2fa92768b7bbf2ba58

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -69,6 +69,13 @@
 			}else
 				if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 					setResult(max, 0);
+					if ((absoluteAccuracy) >= 0.0) {
+						double dplus = max + (java.lang.Math.sqrt(absoluteAccuracy));
+						double dminus = max - (java.lang.Math.sqrt(absoluteAccuracy));
+						absoluteAccuracy = ((java.lang.Math.abs(result)) > (java.lang.Math.abs(absoluteAccuracy))) ? result : absoluteAccuracy;
+					}else {
+						absoluteAccuracy = java.lang.Math.sqrt(((max * max) - (absoluteAccuracy)));
+					}
 					ret = max;
 				}else {
 					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
```


---
## Patch 7 of bug id Math72
### Patch Diff Hash-SHA-256:

9d2dcd1d01588503ea4422e62d95b0f15ae427f7f4aaacd83474bae47874da96

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,15 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			if ((defaultAbsoluteAccuracy) != 0) {
+				absoluteAccuracy = (result) - (((2.0 * max) * ((result) - min)) / (defaultAbsoluteAccuracy));
+				while (((absoluteAccuracy) == min) || ((absoluteAccuracy) == (result))) {
+					absoluteAccuracy += absoluteAccuracy;
+				} 
+			}else {
+				absoluteAccuracy = min + ((java.lang.Math.random()) * (max - min));
+				defaultAbsoluteAccuracy = java.lang.Double.POSITIVE_INFINITY;
+			}
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 8 of bug id Math72
### Patch Diff Hash-SHA-256:

6122fb80612347b9a33ad4108016b0355f839ae87cd8a19d697ea52804331bfd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			absoluteAccuracy = initial;
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 9 of bug id Math72
### Patch Diff Hash-SHA-256:

0b22495eb6811dd2af3d6504300882e9afbb99d092cabd5366ad988e1cc749cd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,7 @@
 		}
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+			absoluteAccuracy = min;
 			setResult(yMin, 0);
 			return result;
 		}
```


---
## Patch 10 of bug id Math72
### Patch Diff Hash-SHA-256:

e2c2b57b33f2ccb6e67decc4fe3422540efe28d95f822d3f5fb56d9e2e94cf00

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -69,6 +69,7 @@
 			}else
 				if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 					setResult(max, 0);
+					absoluteAccuracy = java.lang.Double.POSITIVE_INFINITY;
 					ret = max;
 				}else {
 					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
```


---
## Patch 11 of bug id Math72
### Patch Diff Hash-SHA-256:

0c7c20dd8b13fdac98346f2181fa176eef7038a247d4e645bfae3a2de4577606

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,7 @@
 		}
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+			absoluteAccuracy = org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(min, max);
 			setResult(yMin, 0);
 			return result;
 		}
```


---
## Patch 12 of bug id Math72
### Patch Diff Hash-SHA-256:

d1194dff529551204da0fb59d57655272bf49f21d11c84bf392a766ff3dedff1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,15 @@
 		}
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+			if (((org.apache.commons.math.util.MathUtils.sign(functionValueAccuracy)) + (org.apache.commons.math.util.MathUtils.sign(defaultFunctionValueAccuracy))) == 0.0) {
+				relativeAccuracy = initial;
+				defaultAbsoluteAccuracy = defaultFunctionValueAccuracy;
+			}else {
+				relativeAccuracy = absoluteAccuracy;
+				absoluteAccuracy = initial;
+				defaultAbsoluteAccuracy = functionValue;
+				functionValueAccuracy = defaultFunctionValueAccuracy;
+			}
 			setResult(yMin, 0);
 			return result;
 		}
```


---