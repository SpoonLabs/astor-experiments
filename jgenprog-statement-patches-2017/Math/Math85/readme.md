
# Patches of Math85 from Defects4J 
Total patches 5
## Patch 1 of bug id Math85
### Patch Diff Hash-SHA-256:

08afa6dd3983030516105e6aef7055875773cfca563a00da3505aad92b3ec375

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -47,7 +47,6 @@
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
 		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 2 of bug id Math85
### Patch Diff Hash-SHA-256:

bee6f38e123be7db2428f846afae914b1857229aab097c82a6b3e62ef2251981

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,8 +46,8 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
+		if (((initial < lowerBound) || (initial > upperBound)) || (lowerBound >= upperBound)) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("invalid bracketing parameters:  lower bound={0},  initial={1}, upper bound={2}", lowerBound, initial, upperBound);
 		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 3 of bug id Math85
### Patch Diff Hash-SHA-256:

ffd22459d5e35c6ae18c95157d34279d57a91c499ad1900a7f548340a47d9d68

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,9 +46,6 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
-		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 4 of bug id Math85
### Patch Diff Hash-SHA-256:

fec7b1dd59d10094026d94e252c2e102c7e8e2118f55f4561a59ee8d5264cf5e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,8 +46,8 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
+		if (maximumIterations <= 0) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("bad value for maximum iterations number: {0}", maximumIterations);
 		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 5 of bug id Math85
### Patch Diff Hash-SHA-256:

0a66163b1d904a32de72089a1bb391e15166a8649f5336248170bf35d7cd60a6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,8 +46,8 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
+		if (function == null) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("function is null");
 		}
 		return new double[]{ a , b };
 	}
```


---