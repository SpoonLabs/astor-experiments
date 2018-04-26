
# Patches of Math58 from Defects4J 
Total patches 1
## Patch 1 of bug id Math58
### Patch Diff Hash-SHA-256:

dbda022d37b255437822ca85be753632a626f080916254df5320a2aab8bb9eef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/function/Gaussian.java	
+++ /fixed/org/apache/commons/math/analysis/function/Gaussian.java	
@@ -72,7 +72,7 @@
 			if ((param.length) != 3) {
 				throw new org.apache.commons.math.exception.DimensionMismatchException(param.length, 3);
 			}
-			if ((param[2]) <= 0) {
+			if ((param[0]) <= 0) {
 				throw new org.apache.commons.math.exception.NotStrictlyPositiveException(param[2]);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---