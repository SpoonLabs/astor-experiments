
# Patches of Math2 from Defects4J 
Total patches 11
## Patch 1 of bug id Math2
### Patch Diff Hash-SHA-256:

496a52808bcd2658e1f42bcc8414ab26464c689cb62e6c7e75f81e5395bb1b9f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -58,7 +58,6 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 2 of bug id Math2
### Patch Diff Hash-SHA-256:

41a93e73b2bf5c74b7ec735e0ece931e7b8363a57b2c678c931123d8bfdbfca6

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,18 +49,6 @@
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

ed40558a844b3e8b3d0198d2433f742c79b87511694b7e5dd251cf6648a8513a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
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
+		if (p == 1.0) {
+			return upper;
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 4 of bug id Math2
### Patch Diff Hash-SHA-256:

38f03d87c5cda18bdcf2e6fbccede66b6b6481c42362766937602282316e8fe1

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,8 +57,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (p == 0.0) {
+				return lower;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 5 of bug id Math2
### Patch Diff Hash-SHA-256:

a4446d0ee15926cb21f3f2955513748447a144cbda0a15e1f34e901bddc4e0fc

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,8 +57,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (java.lang.Double.isInfinite(p)) {
+				throw new org.apache.commons.math3.exception.NotFiniteNumberException(p);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 6 of bug id Math2
### Patch Diff Hash-SHA-256:

a1760e800c73de211b8cbd8712e0ee285c3e8e3edc34c2b100ffb431e4b48ff0

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
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
+		if (p == 0.0) {
+			return lower;
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 7 of bug id Math2
### Patch Diff Hash-SHA-256:

daffc27a408c795e67763d543fd069176312c3d14b743583eadb39fc3fdb0ab8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,9 +57,6 @@
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
## Patch 8 of bug id Math2
### Patch Diff Hash-SHA-256:

ea17bd4da9a1037b321fd38b060be14de8da5197fa7f94025b90c53340d1cd6c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
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
+		if (java.lang.Double.isNaN(p)) {
+			throw new org.apache.commons.math3.exception.NotANumberException();
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 9 of bug id Math2
### Patch Diff Hash-SHA-256:

3fe3e61efb9f80ccabbb9a5aba12c4d32bf3b9ad067af3866f3e3dcfd9744051

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
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
+		if (java.lang.Double.isInfinite(p)) {
+			throw new org.apache.commons.math3.exception.NotFiniteNumberException(p);
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 10 of bug id Math2
### Patch Diff Hash-SHA-256:

9a679ee964b5fc58bb69603c2994452601da0120cb32fef051bd651b5e80b363

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
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
+		if ((p < 0) || (p > 1)) {
+			throw new org.apache.commons.math3.exception.OutOfRangeException(p, 0, 1);
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 11 of bug id Math2
### Patch Diff Hash-SHA-256:

ceae2e4a2e181de9f1af349aea59bd2ff4f7c99c247caac9545cc16ec41d8d81

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -58,7 +58,7 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+				tmp = mu + (k * sigma);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---