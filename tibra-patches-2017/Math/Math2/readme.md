
# Patches of Math2 from Defects4J 
Total patches 8
## Patch 1 of bug id Math2
### Patch Diff Hash-SHA-256:

f4a0a06238952d5602288481bdd10fddcf313095f4dfca537d7ee29ce2072c19

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,8 +55,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (p == 1.0) {
+				return upper;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 2 of bug id Math2
### Patch Diff Hash-SHA-256:

92390a80b7a2db71df925be3b33d6bea9504008d8f2e8642605aaf9948ed5f8c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -47,18 +47,6 @@
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
-		if (chebyshevApplies) {
-			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
-			double tmp = mu - (k * sigma);
-			if (tmp > lower) {
-				lower = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-			k = 1.0 / k;
-			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 3 of bug id Math2
### Patch Diff Hash-SHA-256:

83fe0aa2ca8f54172d46d630222fdca538ca2d6544e89002ae2c8b1f55d74739

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,6 +55,9 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
+			if (mu < 0) {
+				return 0;
+			}
 			if (tmp < upper) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
```


---
## Patch 4 of bug id Math2
### Patch Diff Hash-SHA-256:

a8c403f57a4847aeb2f28954e42c456b8f727d8ff8a72127cf7577d31b0b4b19

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,9 +55,15 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (upper < 0) {
+				k = 0.0;
+			}else
+				if (upper >= upper) {
+					k = 1.0;
+				}else {
+					k = 1.0 - (org.apache.commons.math3.special.Beta.regularizedBeta(mu, (upper + 1.0), (upper - upper)));
 			}
+
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 5 of bug id Math2
### Patch Diff Hash-SHA-256:

22d5a0c410c95571088060f53156c4524c60dae0daa0a787b1b1c4ca3e262dbb

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -56,7 +56,6 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 6 of bug id Math2
### Patch Diff Hash-SHA-256:

48fcec25ef3d80369804acde373501752664e70fe69a139f34130f76cceb48a8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,9 +55,6 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 7 of bug id Math2
### Patch Diff Hash-SHA-256:

061787c99ca1035eb347dccae88885275295d8f1c5231493c65b595c28568a58

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,8 +55,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (lower > lower) {
+				throw new org.apache.commons.math3.exception.NumberIsTooLargeException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SUCCESS_LARGER_THAN_POPULATION_SIZE, lower, lower, true);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 8 of bug id Math2
### Patch Diff Hash-SHA-256:

73d7ec287640ebd2e71bff38bf055c6ca8f3bc6835e598cebfdbb821e19979ca

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -56,7 +56,7 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+				k = org.apache.commons.math3.util.FastMath.exp(((mu + tmp) - sigma));
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---