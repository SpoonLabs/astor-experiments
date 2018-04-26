
# Patches of Math62 from Defects4J 
Total patches 2
## Patch 1 of bug id Math62
### Patch Diff Hash-SHA-256:

92323a656891c69598de58854eba9a347c4bca2bcca23fea75b3e29bf88e904a

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/univariate/MultiStartUnivariateRealOptimizer.java	
+++ /fixed/org/apache/commons/math/optimization/univariate/MultiStartUnivariateRealOptimizer.java	
@@ -60,7 +60,7 @@
 		for (int i = 0; i < (starts); ++i) {
 			try {
 				final double bound1 = i == 0 ? min : min + ((generator.nextDouble()) * (max - min));
-				final double bound2 = i == 0 ? max : min + ((generator.nextDouble()) * (max - min));
+				final double bound2 = i == 0 ? max : min - (0.5 * (bound1 - max));
 				optima[i] = optimizer.optimize(f, goal, org.apache.commons.math.util.FastMath.min(bound1, bound2), org.apache.commons.math.util.FastMath.max(bound1, bound2));
 			} catch (org.apache.commons.math.FunctionEvaluationException fee) {
 				optima[i] = null;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math62
### Patch Diff Hash-SHA-256:

7677b86d54656f6f7b67ccea0c1e43fb35b34fc6bdbc34f43d5166e3ea4f5756

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/univariate/MultiStartUnivariateRealOptimizer.java	
+++ /fixed/org/apache/commons/math/optimization/univariate/MultiStartUnivariateRealOptimizer.java	
@@ -61,7 +61,7 @@
 			try {
 				final double bound1 = i == 0 ? min : min + ((generator.nextDouble()) * (max - min));
 				final double bound2 = i == 0 ? max : min + ((generator.nextDouble()) * (max - min));
-				optima[i] = optimizer.optimize(f, goal, org.apache.commons.math.util.FastMath.min(bound1, bound2), org.apache.commons.math.util.FastMath.max(bound1, bound2));
+				optima[i] = optimizer.optimize(f, goal, org.apache.commons.math.util.FastMath.max(min, min), org.apache.commons.math.util.FastMath.max(bound1, bound2));
 			} catch (org.apache.commons.math.FunctionEvaluationException fee) {
 				optima[i] = null;
 			} catch (org.apache.commons.math.exception.ConvergenceException ce) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---