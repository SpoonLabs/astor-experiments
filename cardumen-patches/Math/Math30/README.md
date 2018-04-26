
# Patches of Math30 from Defects4J 
Total patches 45
## Patch 1 of bug id Math30
### Patch Diff Hash-SHA-256:

012f2c6f04f7233f630fa1046391a6364de0db2804cbeb47e7f29b4d03add1ce

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(SQRT2PI)) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math30
### Patch Diff Hash-SHA-256:

52872fe84c20ee0c1c8ab33aa670dc575aa35c3fb32694fecdb47a88ffa5dea4

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (x != x) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math30
### Patch Diff Hash-SHA-256:

c6792120fa92d0ba5f57d8923a11725e73695bb214f4872b558481e04f682e6b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(mean)) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math30
### Patch Diff Hash-SHA-256:

78d3546ca8b6308fecc9eb87112bd08243519a7e10d46b54418e0219eab215bd

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(SQRT2PI)) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math30
### Patch Diff Hash-SHA-256:

9ca7d359202e1655e481d4ccdb902b23d4612dbb22b391604d0e44c775d0362d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (java.lang.Double.isNaN(dev)) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math30
### Patch Diff Hash-SHA-256:

8c82ed6dbe5e2bb15473849c8b2902c841c176622c0f2580647fec9a6d2fd7a4

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(solverAbsoluteAccuracy)) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math30
### Patch Diff Hash-SHA-256:

e85bd07a0d8698c9fc08512f7ee749258a1d7f97ac6d3cb70f3f15a8514aca06

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isInfinite(x)) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math30
### Patch Diff Hash-SHA-256:

de24cd7ed4ef106aaae02e65e744548a67fc38dff801c4663012b4415e3fa25a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (java.lang.Double.isNaN(x)) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math30
### Patch Diff Hash-SHA-256:

55766faab378749a068d092d09f72339c212cf9ffe3fc19861036a3c53ccd46d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(org.apache.commons.math3.distribution.AbstractRealDistribution.SOLVER_DEFAULT_ABSOLUTE_ACCURACY)) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math30
### Patch Diff Hash-SHA-256:

e61bbf7417a61045eeef4d8a8f169ba66afc162a237fe12d75b65583f98f280d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(DEFAULT_INVERSE_ABSOLUTE_ACCURACY)) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math30
### Patch Diff Hash-SHA-256:

a99d3d423329cf8f21df03d3981d178a2d88293b31dfd4d5a6d490c64e99b004

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(org.apache.commons.math3.distribution.AbstractRealDistribution.SOLVER_DEFAULT_ABSOLUTE_ACCURACY)) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math30
### Patch Diff Hash-SHA-256:

5dad5ab029483b0613abfc3f55b14a6c4c7199d6f507f9b92342f4a47eaff772

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math30
### Patch Diff Hash-SHA-256:

14a9a48b97af0aac0918a7255ca679fd5423bbab6a0621ad17a0c3b58a42391d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (dev != dev) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math30
### Patch Diff Hash-SHA-256:

699f9d606e48d689809d325d701ed6f005ace9767027c5d2b4b7ad5a03ad2848

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(org.apache.commons.math3.distribution.AbstractRealDistribution.SOLVER_DEFAULT_ABSOLUTE_ACCURACY))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math30
### Patch Diff Hash-SHA-256:

975c40b333c5238635376a08f8737c5cc7a6432cc3a269369899f16837ac0435

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isInfinite(dev)) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math30
### Patch Diff Hash-SHA-256:

8e34dfeb18b9d14636d0bf24c1a7472c0dee7b45bd18da5bc28da0060fbfb402

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(solverAbsoluteAccuracy))) || (java.lang.Double.isNaN(mean))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math30
### Patch Diff Hash-SHA-256:

840dc827a04e0abc51e78a039c3a7ae495d6a1fe7304190cde40a19d2b4481c8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(dev)) || (java.lang.Double.isInfinite(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math30
### Patch Diff Hash-SHA-256:

43d21f3afc5a1d54684b663a80cd28b891ad383de461bcef03cfc304bfd65b6f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isNaN(mean)) || (java.lang.Double.isNaN(solverAbsoluteAccuracy))) || (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math30
### Patch Diff Hash-SHA-256:

7b8749d2a31d980c0355d7d885f062d2ee6b3ffb250b1f90322c282a059d8f9b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math30
### Patch Diff Hash-SHA-256:

04c7ca48145feedc0023602ac38d90c4d97b92676654d3d65eb00908476555f8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(standardDeviation))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math30
### Patch Diff Hash-SHA-256:

c20bfc4eaf0f52419ded2afe14a88b358e0e2f2ba3058a8cf2c3b3b42a2f785f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(SQRT2))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math30
### Patch Diff Hash-SHA-256:

cdd780f250c293a9e92b29369062e2915de2f8c97abdbff074104afaf8019483

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(DEFAULT_INVERSE_ABSOLUTE_ACCURACY))) || (java.lang.Double.isNaN(standardDeviation))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math30
### Patch Diff Hash-SHA-256:

dcedcd0cdd3606c1ced439632ec0a6de366d7d5bfd1f77f56a8d03e3e9149b19

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(standardDeviation)) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math30
### Patch Diff Hash-SHA-256:

ae44768bf4989ff9cae22e05d8bb561b80a57fe8a4dd9e2097afd62f0b581318

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isNaN(SQRT2)) || (java.lang.Double.isNaN(dev))) || ((SQRT2) <= 0.0)) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math30
### Patch Diff Hash-SHA-256:

a9134d8f6e1850094db0479ae8ddd3229f8bb8a6dd498dfdee9e6e3618de9565

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) || (java.lang.Double.isInfinite(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math30
### Patch Diff Hash-SHA-256:

b3a4b76e9093c26da4cf9118501951eb2d8bf1ac26da91d2191b6bb397be98fc

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(solverAbsoluteAccuracy))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math30
### Patch Diff Hash-SHA-256:

6f828b58cd40624820299a1ed898c47053a185051c41d5077a173c213702f0d2

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(mean))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math30
### Patch Diff Hash-SHA-256:

d208e88ca0964af3d5f41f8d76cf3d769b161e9c8a311a4d9abd1b04a8e6959b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(dev))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math30
### Patch Diff Hash-SHA-256:

34468dfd047ba182dcaddb0c1d961c0cfc18bf4f44f07d81379aa6e1023fce2c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(SQRT2PI))) || (java.lang.Double.isNaN(solverAbsoluteAccuracy))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math30
### Patch Diff Hash-SHA-256:

00b745a92018ef99665034188a054c0ce8d116b583d5e6c1a7a37291525d337d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(DEFAULT_INVERSE_ABSOLUTE_ACCURACY))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math30
### Patch Diff Hash-SHA-256:

5f62215e194a76afb6562d2c4e78f272735d62be768c14846db25afb1fbc21f8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isInfinite(x)) || (java.lang.Double.isNaN(x))) || (java.lang.Double.isInfinite(org.apache.commons.math3.distribution.AbstractRealDistribution.SOLVER_DEFAULT_ABSOLUTE_ACCURACY))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math30
### Patch Diff Hash-SHA-256:

0c75d19b5c43f37fcc069bd3096c0372029da794aed317a26b326935f6e5781f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(dev)) || (java.lang.Double.isNaN(SQRT2PI))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math30
### Patch Diff Hash-SHA-256:

a5bd31f5b74a89b855af359f51614f8fcd99d219b7b90b703c277004592efe8d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math30
### Patch Diff Hash-SHA-256:

da61cc3c5599a4d8d89b607b0f3cfe8a71a3b4976eeecd4fd00d6aa2fe310374

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isInfinite(x)) || (java.lang.Double.isNaN(x))) || (java.lang.Double.isInfinite(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math30
### Patch Diff Hash-SHA-256:

1f314d0c9e6c752b94b2077ba61fb17e5a7b47aac85034a8556cb8e59a855162

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((org.apache.commons.math3.util.Precision.compareTo(x, 0.0, x)) > 0) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math30
### Patch Diff Hash-SHA-256:

23e8d0e9490c28fe7cbf8179263edde96a4ab65fca2f9d87dec2bff98df3d915

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(mean)) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math30
### Patch Diff Hash-SHA-256:

d6377dbd895a116310a432fef0a1a727a3b3a81080c01f36506b80707f47999b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(mean))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math30
### Patch Diff Hash-SHA-256:

248cafbbb205a90d07674eee0455297a9a4f1c71d735fd179ec69014d70e6785

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((x > x) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math30
### Patch Diff Hash-SHA-256:

9c348f15a4c450e5de02e354023e12c6ebbf7ef180bbc5d4188193ed240129a4

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((((java.lang.Double.isInfinite(x)) || (java.lang.Double.isNaN(x))) || (java.lang.Double.isInfinite(x))) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math30
### Patch Diff Hash-SHA-256:

15f835be0e1af9eb1f1a0aaa09cbac793156d4d4725ab2710337f324729f55e5

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((x < x) || (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math30
### Patch Diff Hash-SHA-256:

dc40654a721eceb3a09684293391aed68fb7bf3046c058495d08bbb1c9339dd9

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((x != x) || (x != x)) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math30
### Patch Diff Hash-SHA-256:

08d3a1704068b1d312fa6a7193d4d6eed577d6061a41ce61d836e335ad7c0bd6

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((x != x) || (x == (java.lang.Double.POSITIVE_INFINITY))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math30
### Patch Diff Hash-SHA-256:

803dfd9547456325c98890ce9d2a7021ff7cc1c58f7b27ec21a27b293f330dc2

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(x))) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math30
### Patch Diff Hash-SHA-256:

a7ae7d18317f723cd548c7aced1907caf509c50ec71abc22055a74d88e42f2d7

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isNaN(standardDeviation)) || (java.lang.Double.isNaN(x))) || ((standardDeviation) <= 0.0)) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math30
### Patch Diff Hash-SHA-256:

75afac36bfba8dbd940fa3d931c5ba01a49bf6e67068570edf686d3c659f1e66

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/NormalDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/NormalDistribution.java	
@@ -55,7 +55,7 @@
 
 	public double cumulativeProbability(double x) {
 		final double dev = x - (mean);
-		if ((org.apache.commons.math3.util.FastMath.abs(dev)) > (40 * (standardDeviation))) {
+		if (((java.lang.Double.isNaN(solverAbsoluteAccuracy)) || (java.lang.Double.isNaN(x))) || ((solverAbsoluteAccuracy) <= 0.0)) {
 			return dev < 0 ? 0.0 : 1.0;
 		}
 		return 0.5 * (1 + (org.apache.commons.math3.special.Erf.erf((dev / ((standardDeviation) * (org.apache.commons.math3.distribution.NormalDistribution.SQRT2))))));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---