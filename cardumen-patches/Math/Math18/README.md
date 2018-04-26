
# Patches of Math18 from Defects4J 
Total patches 4
## Patch 1 of bug id Math18
### Patch Diff Hash-SHA-256:

863f0fd36277e87d9bad8079dc3bd7eb2828613b72464622e67a05eb74e8d5b9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -167,7 +167,7 @@
 		org.apache.commons.math3.optimization.direct.CMAESOptimizer.push(fitnessHistory, bestValue);
 		org.apache.commons.math3.optimization.PointValuePair optimum = new org.apache.commons.math3.optimization.PointValuePair(getStartPoint(), (isMinimize ? bestValue : -bestValue));
 		org.apache.commons.math3.optimization.PointValuePair lastResult = null;
-		generationLoop : for (iterations = 1; (iterations) <= (maxIterations); (iterations)++) {
+		generationLoop : for (iterations = 1; (inputSigma) != null; (iterations)++) {
 			org.apache.commons.math3.linear.RealMatrix arz = randn1(dimension, lambda);
 			org.apache.commons.math3.linear.RealMatrix arx = org.apache.commons.math3.optimization.direct.CMAESOptimizer.zeros(dimension, lambda);
 			double[] fitness = new double[lambda];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math18
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
## Patch 3 of bug id Math18
### Patch Diff Hash-SHA-256:

9f8254ec316523c6d5aabd24791257342ce10caeafe36c6aeee1dfbcff0c0e0a

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -329,7 +329,7 @@
 
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
## Patch 4 of bug id Math18
### Patch Diff Hash-SHA-256:

551d7bbff4a1ebe5ccf41fd818b802ce562df1f5b47b23ff896ce7a24969d9c1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -167,7 +167,7 @@
 		org.apache.commons.math3.optimization.direct.CMAESOptimizer.push(fitnessHistory, bestValue);
 		org.apache.commons.math3.optimization.PointValuePair optimum = new org.apache.commons.math3.optimization.PointValuePair(getStartPoint(), (isMinimize ? bestValue : -bestValue));
 		org.apache.commons.math3.optimization.PointValuePair lastResult = null;
-		generationLoop : for (iterations = 1; (iterations) <= (maxIterations); (iterations)++) {
+		generationLoop : for (iterations = 1; (dimension) > 2; (iterations)++) {
 			org.apache.commons.math3.linear.RealMatrix arz = randn1(dimension, lambda);
 			org.apache.commons.math3.linear.RealMatrix arx = org.apache.commons.math3.optimization.direct.CMAESOptimizer.zeros(dimension, lambda);
 			double[] fitness = new double[lambda];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---