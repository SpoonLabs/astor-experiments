
# Patches of Math2 from Defects4J 
Total patches 28
## Patch 1 of bug id Math2
### Patch Diff Hash-SHA-256:

35644d794c519d674a1e44e32fe569467f65aa1867f00d0b573968347617ebcc

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/HypergeometricDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/HypergeometricDistribution.java	
@@ -126,7 +126,7 @@
 	}
 
 	public double getNumericalVariance() {
-		if (!(numericalVarianceIsCalculated)) {
+		if (!((sampleSize) <= (numberOfSuccesses))) {
 			numericalVariance = calculateNumericalVariance();
 			numericalVarianceIsCalculated = true;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math2
### Patch Diff Hash-SHA-256:

28ffe414e15898c16989e82c4b499276512bc07e77f41334e9d8b3bb068eae13

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -48,7 +48,7 @@
 		}
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
-		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
+		final boolean chebyshevApplies = lower < lower;
 		if (chebyshevApplies) {
 			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
 			double tmp = mu - (k * sigma);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math2
### Patch Diff Hash-SHA-256:

85809bf18b0b8a71b6552e26a42b620880869efe36c6ae687b45a70e826fdfa8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/HypergeometricDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/HypergeometricDistribution.java	
@@ -126,7 +126,7 @@
 	}
 
 	public double getNumericalVariance() {
-		if (!(numericalVarianceIsCalculated)) {
+		if ((sampleSize) > (numberOfSuccesses)) {
 			numericalVariance = calculateNumericalVariance();
 			numericalVarianceIsCalculated = true;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math2
### Patch Diff Hash-SHA-256:

7abf130da6378e7fca26a2fb1850cfd7d2bbfdb0794b7c92fe553fa3125fb630

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -48,7 +48,7 @@
 		}
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
-		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
+		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (lower == lower)) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
 		if (chebyshevApplies) {
 			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
 			double tmp = mu - (k * sigma);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math2
### Patch Diff Hash-SHA-256:

be4c141e469c15ae8600b868fb1d72b03563615ab5d4041ad04aa71cd663e72f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if ((java.lang.Double.isInfinite(p)) || (java.lang.Double.isNaN(p))) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math2
### Patch Diff Hash-SHA-256:

e9ffbb22b6131b06db733cc42b0f5ccae82966a0c35fa96034621d488ec89eb1

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (lower < lower) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math2
### Patch Diff Hash-SHA-256:

8f8626714b42d5f348e8b8a78731435e8b45d358b8b1d971c71f80fb86e37f8b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (p == 0.0) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math2
### Patch Diff Hash-SHA-256:

9ff91f8a28d3f448968d54a5c070b000416322315115c7c2f38f3ca497a94268

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (p > 1.0) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math2
### Patch Diff Hash-SHA-256:

fa7cfc8f45cfab44f81cb34aea706a5dbe3623a91f5698eb25228dd840c0c00e

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if ((java.lang.Double.isInfinite(tmp)) || (java.lang.Double.isNaN(tmp))) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math2
### Patch Diff Hash-SHA-256:

207fb2b3ef235ebe689e9c397b428cafbf972a1dcfa841701de5bcf47c524859

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -47,7 +47,7 @@
 			return upper;
 		}
 		final double mu = getNumericalMean();
-		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
+		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - mu) / mu));
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
 		if (chebyshevApplies) {
 			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math2
### Patch Diff Hash-SHA-256:

6b08c164b750f0c9c253b6bd8e28ca36cae6aa8b81c564271b7b008cddded477

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -58,7 +58,7 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+				upper = upper + ((upper - upper) / 2);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math2
### Patch Diff Hash-SHA-256:

2d8a864822c87ee5685c3259294dc19dfa88014c90773b5ac2bfd74340e7b8a5

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (((java.lang.Double.isInfinite(p)) || (java.lang.Double.isNaN(p))) || (java.lang.Double.isInfinite(p))) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math2
### Patch Diff Hash-SHA-256:

6c7019ae78898b89b45a5f15024a15858bcbea087c2fbb103e4b22b4ebe8a763

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (p < 0.0) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math2
### Patch Diff Hash-SHA-256:

ef5215315b4e1ec5feae681cc6f4b2b2df1144d20ece62071736891961b38671

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if ((lower + 1) < lower) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math2
### Patch Diff Hash-SHA-256:

2d834a26fef1703ed428fd37b52e14a12b66064a218435c8d1894778bde85fd4

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (lower > lower) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math2
### Patch Diff Hash-SHA-256:

e1b030d11f7ee10948b53257819314b6916cf8931f0651805d84bb59ded16a94

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if ((lower < lower) || (lower > lower)) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math2
### Patch Diff Hash-SHA-256:

e2c57cbaf5311c7007778d714bdf5d20408b2920b6d5939b61810bc656c78a10

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -47,7 +47,7 @@
 			return upper;
 		}
 		final double mu = getNumericalMean();
-		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
+		final double sigma = checkedCumulativeProbability(lower);
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
 		if (chebyshevApplies) {
 			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math2
### Patch Diff Hash-SHA-256:

aa8a64544e807190f61715405da19f9726414f0c4fe0559cf171af43befea84e

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -47,7 +47,7 @@
 			return upper;
 		}
 		final double mu = getNumericalMean();
-		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
+		final double sigma = probability(lower);
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
 		if (chebyshevApplies) {
 			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math2
### Patch Diff Hash-SHA-256:

c3563976b3c61ce474efb05bb8a1c38861920af327aa678581f21b27d3265960

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -47,7 +47,7 @@
 			return upper;
 		}
 		final double mu = getNumericalMean();
-		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
+		final double sigma = cumulativeProbability(lower);
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
 		if (chebyshevApplies) {
 			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math2
### Patch Diff Hash-SHA-256:

9373f9f00105903f53221d998d28b78a3a7e8cc722390ff7dcdba44ce829438d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -58,7 +58,7 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+				upper = upper - (upper - upper);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math2
### Patch Diff Hash-SHA-256:

5574eac67725bfefe1056a020d64b55926c8f5330d9813885a9291cb1cb3cd00

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (upper > upper) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math2
### Patch Diff Hash-SHA-256:

c7a37ddddb1fbeeef90a0e886b304e209fa95e11bd5d26fe1a22aad1d3ec6893

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if ((((java.lang.Double.isInfinite(p)) || (java.lang.Double.isNaN(p))) || (java.lang.Double.isInfinite(p))) || (java.lang.Double.isNaN(p))) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math2
### Patch Diff Hash-SHA-256:

484a6e4b79fd300288a8d97b4a38701d7435eb12e72e6e34c0a2ccdcf3900818

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (p < lower) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math2
### Patch Diff Hash-SHA-256:

9688f98bb370f722233af0a4bfaab27bbbb635c42c465e3dfaba2d420a061099

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (p == 1.0) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math2
### Patch Diff Hash-SHA-256:

0c47e3a17192729b0996c33a6bc661339b9cd9c280dde72ccde6c9fef117a646

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -58,7 +58,7 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+				upper = lower - (lower - upper);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math2
### Patch Diff Hash-SHA-256:

b20ab99f4b93d47c002c8fd7c5d1c43aca177003143e826053492cc59f3d9cd7

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (lower != lower) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math2
### Patch Diff Hash-SHA-256:

701961f5ecffbab697a9d841886fdde6944601d3284d7c3afae782fe6c718708

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (upper < upper) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math2
### Patch Diff Hash-SHA-256:

81098ab0194bc1ffd8e435359a589d080e62367c095d8eabc39e3eec5c4116b7

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,7 +57,7 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
+			if (tmp > lower) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---