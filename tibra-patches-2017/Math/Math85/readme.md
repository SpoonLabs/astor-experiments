
# Patches of Math85 from Defects4J 
Total patches 2
## Patch 1 of bug id Math85
### Patch Diff Hash-SHA-256:

53f083212d5a1928221e73ccf79dd542dbe77fb9ca346c126d382765b544e6e8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -49,7 +49,6 @@
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
 		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a, b };
 	}
```


---
## Patch 2 of bug id Math85
### Patch Diff Hash-SHA-256:

4dee6b798156cfcbcbded8bd4c2fdd41dace7c74d9e19a67f75cda7a5453655f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -48,9 +48,6 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
-		}
 		return new double[]{ a, b };
 	}
```


---