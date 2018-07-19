
# Patches of Math20 from Defects4J 
Total patches 67
## Patch 1 of bug id Math20
### Patch Diff Hash-SHA-256:

079eb8100738270a2418a48ace98d0d6e891a215ea5567dc174ed020517e834c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) > (valueRange); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math20
### Patch Diff Hash-SHA-256:

9dbaad8d1a0b2ea264ea204ec37daa565b552f8aff5925663cb1da9ac924625d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (x != null) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math20
### Patch Diff Hash-SHA-256:

a8e5fe7c58b16deebd3a0c4e146d3126910987946ccb0673cc11d754639732ef

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; res == null; i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math20
### Patch Diff Hash-SHA-256:

3a0a7017822beaf5dfba65426045a733a7d5102531638c65d837e61cf4edb95c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (((java.lang.Math.max(valueRange, valueRange)) - (java.lang.Math.min(valueRange, valueRange))) < (valueRange)) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math20
### Patch Diff Hash-SHA-256:

55610e19be52ff89ded511e877a95c1332dcff9179047d62968572da65577059

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (((java.lang.Math.max(valueRange, valueRange)) - (java.lang.Math.min(valueRange, valueRange))) == 0) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math20
### Patch Diff Hash-SHA-256:

adb0ab94a53a7bf63fb6fdb4e454c9e2be8efb91090630f5a5be9d47cf273a3f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if ((getConvergenceChecker()) != null) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math20
### Patch Diff Hash-SHA-256:

0e1606121d223294c929c003c6a74509c08306e2405a0417fc988f8b6951b7d7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -232,7 +232,7 @@
 				}
 			}
 			for (int i = 0; i < (dimension); i++) {
-				if (((sigma) * (sqrtDiagC[i])) > (stopTolUpX)) {
+				if ((diagonalOnly) >= ((dimension) - 1)) {
 					break generationLoop;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math20
### Patch Diff Hash-SHA-256:

106642e05f56efb9149efb86e8974876eb97d478ee5b6b6ffbb12fd0dd0794f8

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -224,7 +224,7 @@
 			double[] sqrtDiagC = org.apache.commons.math3.optimization.direct.CMAESOptimizer.sqrt(diagC).getColumn(0);
 			double[] pcCol = pc.getColumn(0);
 			for (int i = 0; i < (dimension); i++) {
-				if (((sigma) * (java.lang.Math.max(java.lang.Math.abs(pcCol[i]), sqrtDiagC[i]))) > (stopTolX)) {
+				if ((inputSigma) != null) {
 					break;
 				}
 				if (i >= ((dimension) - 1)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math20
### Patch Diff Hash-SHA-256:

d0239ab9b57a1ff2178a11f4de19cec181fded824a513cec81a8e3d147e307db

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) < (valueRange); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math20
### Patch Diff Hash-SHA-256:

2aec2b1d3cebd7aa39d271270d39e4b9dbe63bfcb8cf6a049378f5526a6e34c0

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if ((valueRange) < 15.0) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math20
### Patch Diff Hash-SHA-256:

bf2a4145857cb07090e84993c31a5a3447f8f7c93661149bed8069f732a6a472

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) < 0.0; i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math20
### Patch Diff Hash-SHA-256:

39fbe519d48f60533d115180d63183a04c99e9e1f717984ae9f506928b750922

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; org.apache.commons.math3.util.Precision.equals(valueRange, 0); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math20
### Patch Diff Hash-SHA-256:

0fb30126aede408684117dd60a222d274ea1ced073d7db07e216254b486449de

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if ((valueRange) > 0.0036) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math20
### Patch Diff Hash-SHA-256:

abb0cc4d8818c9b384c57b4728f55f05828ab4e922e83eb70c3de72634a85dc0

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; ((valueRange) < 0.0) || ((valueRange) > 1.0); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math20
### Patch Diff Hash-SHA-256:

c91554d1c68a9b2f6d4478d454de36a7a5a2ed0dd34f7b80c7e9fed7da93b731

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; ((valueRange) > ((valueRange) * ((valueRange) - (valueRange)))) && ((valueRange) < ((valueRange) * ((valueRange) - (valueRange)))); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math20
### Patch Diff Hash-SHA-256:

861ef9bd1a213b2b9046fcf0bed64a53c4c50986ca85e0ca5ddef0c5170606db

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (!(isRepairMode)) && ((valueRange) <= 0.0); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math20
### Patch Diff Hash-SHA-256:

8d6df3d5e16e13ce2e14a51c4d8976e7f906cbc73172492ccd9a28b6bb6cc50d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) <= 0; i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math20
### Patch Diff Hash-SHA-256:

7d8e1c2bffc4a898083e246710cbdcb03ee4872ea3412caad44595d6f6c37eb4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -232,7 +232,7 @@
 				}
 			}
 			for (int i = 0; i < (dimension); i++) {
-				if (((sigma) * (sqrtDiagC[i])) > (stopTolUpX)) {
+				if ((mu) < 3) {
 					break generationLoop;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math20
### Patch Diff Hash-SHA-256:

2dce27b439a3599657c221da9340a9aa3e2d2828f8b1c827ab095288ec5d2819

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (true) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math20
### Patch Diff Hash-SHA-256:

1b687d8702396a4d878a308342869589285701608fe9770632730ae54d3c2f08

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -238,7 +238,7 @@
 			}
 			double historyBest = org.apache.commons.math3.optimization.direct.CMAESOptimizer.min(fitnessHistory);
 			double historyWorst = org.apache.commons.math3.optimization.direct.CMAESOptimizer.max(fitnessHistory);
-			if (((iterations) > 2) && (((java.lang.Math.max(historyWorst, worstFitness)) - (java.lang.Math.min(historyBest, bestFitness))) < (stopTolFun))) {
+			if ((cc) > 0.5) {
 				break generationLoop;
 			}
 			if (((iterations) > (fitnessHistory.length)) && ((historyWorst - historyBest) < (stopTolHistFun))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math20
### Patch Diff Hash-SHA-256:

b19414d8e569a97a052c1c03b768e4423075009f4983803956b45dc242c39f39

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) < (-1.0); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math20
### Patch Diff Hash-SHA-256:

850ed97385ddc26aa5bf3f143298b47eb0237c7d10398ebe4b4fc8573d01985f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (1 <= (valueRange)) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math20
### Patch Diff Hash-SHA-256:

c61c35e66dc8ce0933e25c73402278c26b569a96ec8e4a907572447f79f3edd7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; x == null; i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math20
### Patch Diff Hash-SHA-256:

beae1b1def98037068e0dc6352befbb30516d877027f487c770864aee9aaf79f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) < (isRepairMode ? valueRange : -(valueRange)); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math20
### Patch Diff Hash-SHA-256:

8d92a522d003130635197035ff9e848d8b532306cf6dcbdc375a073eca3089a1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if ((((valueRange) + (valueRange)) + (valueRange)) > 0) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math20
### Patch Diff Hash-SHA-256:

b97a69bfa2be19ab686621ec3d785b7f34843bbd61817fbe3845b7939ac6c141

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -249,7 +249,7 @@
 			}
 			if ((getConvergenceChecker()) != null) {
 				org.apache.commons.math3.optimization.PointValuePair current = new org.apache.commons.math3.optimization.PointValuePair(bestArx.getColumn(0), (isMinimize ? bestFitness : -bestFitness));
-				if ((lastResult != null) && (getConvergenceChecker().converged(iterations, current, lastResult))) {
+				if ((inputSigma) == null) {
 					break generationLoop;
 				}
 				lastResult = current;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math20
### Patch Diff Hash-SHA-256:

817e6610f1c286c5a6fc8be668deb1fe2fa209ceee1d46a07a68baeafc20350c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (x == null) || (x == null); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math20
### Patch Diff Hash-SHA-256:

7a918f4963100a596df4d1a24902f1bf5a3e00af888c910f99a55e90bae7ed7b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; java.lang.Double.isInfinite(valueRange); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math20
### Patch Diff Hash-SHA-256:

d49bcd1f5a537c2e1907780786eff4b49f17b686c01835aa19aeccb412f4f77f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) < 0; i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math20
### Patch Diff Hash-SHA-256:

b24aba6fe71b3a3487996e622d58f5753d3a0213ee9b685c3b0799bf932ca096

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) == 0; i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math20
### Patch Diff Hash-SHA-256:

22cfdeda782dd22edc4d34b3bc52a8633f7b3c7e85840b9371b4bb430d21682b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) != (org.apache.commons.math3.util.FastMath.floor(valueRange)); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math20
### Patch Diff Hash-SHA-256:

5e322b7aba3b40eae22dd01e0f6d5ab857a3a80cf594b8c331bce70c62861a05

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (((valueRange) < 1.0E-4) || ((valueRange) > 0.9999)) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math20
### Patch Diff Hash-SHA-256:

e42d1c447d389ee26f0b47da435f6dbef361e763c41e9ab1370af0f6767bd4b2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) > ((org.apache.commons.math3.util.FastMath.PI) - 1.0E-10); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math20
### Patch Diff Hash-SHA-256:

098f6ce3ea3abdd92ccc3ab6bcbee2a4a7639136fa60c93a61c36deb04c03cfa

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -585,7 +585,7 @@
 				if ((x[i]) < 0) {
 					repaired[i] = 0;
 				}else
-					if ((x[i]) > 1.0) {
+					if ((x.length) < 2) {
 						repaired[i] = 1.0;
 					}else {
 						repaired[i] = x[i];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math20
### Patch Diff Hash-SHA-256:

c25a5df79cc1a6b126e13069d797c441092be2cc0fecc07d299803b3d586e4ca

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) > 1.633123935319537E16; i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math20
### Patch Diff Hash-SHA-256:

64f994ed8d2a67feb19b625714f05ed21c9934010bb967360ae33a556c4fd8f3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; !(isRepairMode); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math20
### Patch Diff Hash-SHA-256:

c501f2e9f7131e4a4cc415fd8e59e1d87b2eaa96efbd1a7a7e0a89c844fd1e15

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -448,7 +448,7 @@
 				C = C.add(org.apache.commons.math3.optimization.direct.CMAESOptimizer.eye(dimension, dimension).scalarMultiply(tfac));
 				diagD = diagD.add(org.apache.commons.math3.optimization.direct.CMAESOptimizer.ones(dimension, 1).scalarMultiply(tfac));
 			}
-			if ((org.apache.commons.math3.optimization.direct.CMAESOptimizer.max(diagD)) > (1.0E14 * (org.apache.commons.math3.optimization.direct.CMAESOptimizer.min(diagD)))) {
+			if ((inputSigma) == null) {
 				double tfac = ((org.apache.commons.math3.optimization.direct.CMAESOptimizer.max(diagD)) / 1.0E14) - (org.apache.commons.math3.optimization.direct.CMAESOptimizer.min(diagD));
 				C = C.add(org.apache.commons.math3.optimization.direct.CMAESOptimizer.eye(dimension, dimension).scalarMultiply(tfac));
 				diagD = diagD.add(org.apache.commons.math3.optimization.direct.CMAESOptimizer.ones(dimension, 1).scalarMultiply(tfac));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math20
### Patch Diff Hash-SHA-256:

00a09946c9627259768a3158990aa26b03b9bdab0d36c0ed8dddd6e2d0b8e1e3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (java.lang.Double.isNaN(valueRange)) || (java.lang.Double.isNaN(valueRange)); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math20
### Patch Diff Hash-SHA-256:

7127d8ac184b4d408aa7cf16645eb6a6d12040b2741a3590a9bba1e1c25a8cdd

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (isRepairMode = true) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math20
### Patch Diff Hash-SHA-256:

82869cbe0d3ae129582dc4fa85151a65887034afb3c412b433e794652e31d27b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (valueRange) > (org.apache.commons.math3.util.FastMath.pow(valueRange, ((valueRange) - 1))); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math20
### Patch Diff Hash-SHA-256:

5b4bd3affa6eb696f5938200ba579d2078a1cde25edb73feff2fdce6a4f02707

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; java.lang.Double.isInfinite(x[0]); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math20
### Patch Diff Hash-SHA-256:

b54f6d1e1ba81218eaf250cfbb4d07bfc6c0901cf2d349aa7e1c4cd658b0e1e4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,7 +526,7 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
+			for (int i = 0; (org.apache.commons.math3.util.FastMath.abs(((valueRange) - (valueRange)))) > ((org.apache.commons.math3.util.FastMath.max(org.apache.commons.math3.util.FastMath.abs(valueRange), org.apache.commons.math3.util.FastMath.abs(valueRange))) * (valueRange)); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math20
### Patch Diff Hash-SHA-256:

dabab46c7dc0b2dba2b890c3cde3c9e8da7d4e22ecdd831675d1d292a3c4181e

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -206,7 +206,7 @@
 			sigma *= java.lang.Math.exp(java.lang.Math.min(1.0, (((((normps) / (chiN)) - 1.0) * (cs)) / (damps))));
 			double bestFitness = fitness[arindex[0]];
 			double worstFitness = fitness[arindex[((arindex.length) - 1)]];
-			if (bestValue > bestFitness) {
+			if ((stopFitness) != 0) {
 				bestValue = bestFitness;
 				lastResult = optimum;
 				optimum = new org.apache.commons.math3.optimization.PointValuePair(fitfun.repairAndDecode(bestArx.getColumn(0)), (isMinimize ? bestFitness : -bestFitness));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math20
### Patch Diff Hash-SHA-256:

eedee831e1054eadad5c686860914ade652f63833c7be5561f7d297a89005e23

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if ((valueRange) != 0) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math20
### Patch Diff Hash-SHA-256:

c3a5e2ce06d73cb9b06d7ddf4e4d932b397e827044ae0367ca4b0c4cc331c85e

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (((valueRange) + (valueRange)) > 0) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math20
### Patch Diff Hash-SHA-256:

55a8a3b0c9688afe99d4326896e37e87fd1364de7aa6c3e03a9a884a8a36e0d2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -522,7 +522,7 @@
 		}
 
 		public double[] encode(final double[] x) {
-			if ((boundaries) == null) {
+			if (((valueRange) - (valueRange)) < (valueRange)) {
 				return x;
 			}
 			double[] res = new double[x.length];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math20
### Patch Diff Hash-SHA-256:

69b6fc5309b3efac63f3b212cccddb72661713f1508be4df163f07a0771ae411

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -232,7 +232,7 @@
 				}
 			}
 			for (int i = 0; i < (dimension); i++) {
-				if (((sigma) * (sqrtDiagC[i])) > (stopTolUpX)) {
+				if ((inputSigma) == null) {
 					break generationLoop;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math20
### Patch Diff Hash-SHA-256:

4dafa58c1347aeb0e570971c7feb0767f98e9d463d40920b4c4f6eaecb1d114b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -527,7 +527,7 @@
 			}
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
-				double diff = (boundaries[1][i]) - (boundaries[0][i]);
+				double diff = ((valueRange) - 1.0) - (boundaries[0][i]);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
 			return res;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math20
### Patch Diff Hash-SHA-256:

0bb4a09a924554a80a112321d6456b90a898f5b327f92285c87b7d6a4216b807

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -328,7 +328,7 @@
 			sigmaArray[i][0] = ((inputSigma) == null ? 0.3 : inputSigma[i]) / range;
 		}
 		org.apache.commons.math3.linear.RealMatrix insigma = new org.apache.commons.math3.linear.Array2DRowRealMatrix(sigmaArray, false);
-		sigma = org.apache.commons.math3.optimization.direct.CMAESOptimizer.max(insigma);
+		sigma = java.lang.Math.sqrt(dimension);
 		stopTolUpX = 1000.0 * (org.apache.commons.math3.optimization.direct.CMAESOptimizer.max(insigma));
 		stopTolX = 1.0E-11 * (org.apache.commons.math3.optimization.direct.CMAESOptimizer.max(insigma));
 		stopTolFun = 1.0E-12;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math20
### Patch Diff Hash-SHA-256:

e8921a9957ef41ebda369f03f74af500a70ee59a19f23ee020eda55160b99ade

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -527,7 +527,7 @@
 			}
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
-				double diff = (boundaries[1][i]) - (boundaries[0][i]);
+				double diff = (1.0 - (valueRange)) - (valueRange);
 				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
 			return res;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math20
### Patch Diff Hash-SHA-256:

c7d5d6f5684f23ea0bfa670c0aaa91240b89fbe2ab1354684bfdd344f511fd4f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = (java.lang.Math.sqrt((((valueRange) * (2.0 - (valueRange))) * (valueRange)))) / (valueRange);
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math20
### Patch Diff Hash-SHA-256:

8e9967ae113952bdb5ca5f707d556fb738b04a67c28d6e25a9f5e7c328735448

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -163,7 +163,7 @@
 		dimension = guess.length;
 		initializeCMA(guess);
 		iterations = 0;
-		double bestValue = fitfun.value(guess);
+		double bestValue = java.lang.Math.sqrt((((sigma) * (2.0 - (sigma))) * (sigma)));
 		org.apache.commons.math3.optimization.direct.CMAESOptimizer.push(fitnessHistory, bestValue);
 		org.apache.commons.math3.optimization.PointValuePair optimum = new org.apache.commons.math3.optimization.PointValuePair(getStartPoint(), (isMinimize ? bestValue : -bestValue));
 		org.apache.commons.math3.optimization.PointValuePair lastResult = null;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math20
### Patch Diff Hash-SHA-256:

1225a765ca2a711fb56fb9ea80c99402dfdcc7f69c98dbdcfce9ddcf77765097

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = (valueRange) * (2.0 - (valueRange));
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math20
### Patch Diff Hash-SHA-256:

224914d4bdc03f6bc61168496698abf90626251098963fd9419ff94a3958b7e3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = (valueRange) * (valueRange);
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math20
### Patch Diff Hash-SHA-256:

529830e3dd62b77f113ec2664607decd40ca4516eb193ad2ae38f40a7bdd8fcf

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -320,7 +320,7 @@
 
 	private void initializeCMA(double[] guess) {
 		if ((lambda) <= 0) {
-			lambda = 4 + ((int) (3.0 * (java.lang.Math.log(dimension))));
+			lambda = (getMaxEvaluations()) / (dimension);
 		}
 		double[][] sigmaArray = new double[guess.length][1];
 		for (int i = 0; i < (guess.length); i++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math20
### Patch Diff Hash-SHA-256:

8210d6e5394ec82755fcf0cf55d44ca066313c98dca6002b1573fe6d13f67bbf

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				x[0] = ((x[i]) - (boundaries[0][i])) / diff;
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math20
### Patch Diff Hash-SHA-256:

2b4f83c7ca7bb11dad537bd90c9c1e7ba794f794423802acd036bbf37943f91c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = ((valueRange) - (valueRange)) / diff;
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math20
### Patch Diff Hash-SHA-256:

d27eb6879cc97d713f39600451e70721f5f248690fa49284378e02de9ba9b7dd

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = ((valueRange) * (valueRange)) / diff;
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math20
### Patch Diff Hash-SHA-256:

606c495f598afcecb7b2357a8e9436b49b102ce0a43fcba3660f64ae7cb9e51c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -586,7 +586,7 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
+						x[0] = 1.0;
 					}else {
 						repaired[i] = x[i];
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math20
### Patch Diff Hash-SHA-256:

9def5b23072fc562afa853622afedbd35ed900748ef06689863ab0209a29239b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = (1.0 - (valueRange)) - (valueRange);
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math20
### Patch Diff Hash-SHA-256:

23fdd46e2030b2ce184a846ca4482df6a48463c14b4993a59468d2c571f32055

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = (valueRange) - 2.0;
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math20
### Patch Diff Hash-SHA-256:

61d9b86356292adbae19757112375f65a4e6cd3e618bb6fda690929c8a76442b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = 1.0 / (valueRange);
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math20
### Patch Diff Hash-SHA-256:

30ae91194497f1f8e5a5ab20c7110571c07b215d9035e56126861fe7df158d50

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -721,7 +721,7 @@
 	private static org.apache.commons.math3.linear.RealMatrix eye(int n, int m) {
 		double[][] d = new double[n][m];
 		for (int r = 0; r < n; r++) {
-			if (r < m) {
+			if (m > 2) {
 				d[r][r] = 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math20
### Patch Diff Hash-SHA-256:

e167c86941b10544a4116cbb7769cbafe517ad17883d12488e7f923bba4522ca

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -721,7 +721,7 @@
 	private static org.apache.commons.math3.linear.RealMatrix eye(int n, int m) {
 		double[][] d = new double[n][m];
 		for (int r = 0; r < n; r++) {
-			if (r < m) {
+			if (m < (m * m)) {
 				d[r][r] = 1;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math20
### Patch Diff Hash-SHA-256:

6c2ddfcb3f3a8e5e127e954886fc0bac107d847c9011f570ba623cbdebaa72f3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = 2.0 - (valueRange);
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math20
### Patch Diff Hash-SHA-256:

cdb3232387da10d1b1c22e8133d9170d653c219545e1312f45c28913418f0e4f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res[i] = (valueRange) - (valueRange);
 			}
 			return res;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math20
### Patch Diff Hash-SHA-256:

19716a67345013650f46f8bd4202e97996715dcfbeca396a388c22b7e0b99c2f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -244,7 +244,7 @@
 			if (((iterations) > (fitnessHistory.length)) && ((historyWorst - historyBest) < (stopTolHistFun))) {
 				break generationLoop;
 			}
-			if (((org.apache.commons.math3.optimization.direct.CMAESOptimizer.max(diagD)) / (org.apache.commons.math3.optimization.direct.CMAESOptimizer.min(diagD))) > 1.0E7) {
+			if ((((mueff) / (java.lang.Math.sqrt((1.0 - (java.lang.Math.pow((1.0 - (mueff)), (2.0 * (dimension)))))))) / (mueff)) < (1.4 + (2.0 / ((dimension) + 1.0)))) {
 				break generationLoop;
 			}
 			if ((getConvergenceChecker()) != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---