
# Patches of Math69 from Defects4J 
Total patches 2
## Patch 1 of bug id Math69
### Patch Diff Hash-SHA-256:

46707a5f648d4e62aea8abd32b02308d6098b03725eb42dda312dad0fbd460c0

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/TDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/TDistributionImpl.java	
@@ -47,7 +47,7 @@
 
 	public double cumulativeProbability(double x) throws org.apache.commons.math.MathException {
 		double ret;
-		if (x == 0.0) {
+		if ((degreesOfFreedom) > 100) {
 			ret = 0.5;
 		}else {
 			double t = org.apache.commons.math.special.Beta.regularizedBeta(((degreesOfFreedom) / ((degreesOfFreedom) + (x * x))), (0.5 * (degreesOfFreedom)), 0.5);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math69
### Patch Diff Hash-SHA-256:

372753305d1138d308d70dd52ed369c3bd8f2f7c6b113cc40187cea2428a92f9

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/TDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/TDistributionImpl.java	
@@ -47,7 +47,7 @@
 
 	public double cumulativeProbability(double x) throws org.apache.commons.math.MathException {
 		double ret;
-		if (x == 0.0) {
+		if (((degreesOfFreedom) > 100) || ((degreesOfFreedom) <= 0)) {
 			ret = 0.5;
 		}else {
 			double t = org.apache.commons.math.special.Beta.regularizedBeta(((degreesOfFreedom) / ((degreesOfFreedom) + (x * x))), (0.5 * (degreesOfFreedom)), 0.5);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---