
# Patches of Math73 from Defects4J 
Total patches 554
## Patch 1 of bug id Math73
### Patch Diff Hash-SHA-256:

eb941175eeac084de372c95d1400282e488a284f09103971fc75009a85e6f02b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math73
### Patch Diff Hash-SHA-256:

a304422d15ba8f6c2e0a805bf06f64f5ce6ea49dc5dc01d07e3674c162c980c7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math73
### Patch Diff Hash-SHA-256:

81a957816a8201bc2523a02d2785d6073eb6b2d6d8cdc1d16922e76743af32f8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math73
### Patch Diff Hash-SHA-256:

52b37e665c9f2a35d221a5e653762522e55e1c72d726caf8f86098b704a64e55

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math73
### Patch Diff Hash-SHA-256:

9b3af8521bc037c84fd061221f08f8721fefcfa516ccced5cef7ac13d1f8cf89

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math73
### Patch Diff Hash-SHA-256:

0dd8d44328c5a460d6b2ee3487d6a02fbe5e5955e6dd984db4fc86c7ecb6097f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math73
### Patch Diff Hash-SHA-256:

00fd227a38419a5bca4b3070f8dbdeeb0522be3dcd9aa411f185db5b1a99aaaa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(max, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math73
### Patch Diff Hash-SHA-256:

7b394b79e54fa0ac11e1a68f0c7b8a84b4a22fb79b401a0fe938612b2d01d618

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(min, min));
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math73
### Patch Diff Hash-SHA-256:

5982e4b20de9e620e43c458578492baaccb7f7a058f97e15ca11cc480da6f39f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(max, max));
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math73
### Patch Diff Hash-SHA-256:

3a1b2b35b0b090c269cfacd024fa196e47736be2f27f8668f5c8a8013e537692

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(max, min));
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math73
### Patch Diff Hash-SHA-256:

b98b0462afd84bbce916f2a99c25eda44633cd55917fdaa74db302601c2530c6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math73
### Patch Diff Hash-SHA-256:

80a5478ba469bfd499e6e419d17fb9c67e8d8a03b1a468a7f6306b7c7171cb48

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy, org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(min, functionValueAccuracy));
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math73
### Patch Diff Hash-SHA-256:

a2e984657dcae17230b5321ae550e8ee75d08e918a6a1e09670c4eb66e074930

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(min, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math73
### Patch Diff Hash-SHA-256:

d00600fd48f2f8d37647553b78fea80295ed0c360ed1a8e721a0e2951a03f101

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(defaultAbsoluteAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math73
### Patch Diff Hash-SHA-256:

fbb23a998e08fb810cf49f9381030901868ed73adfbc0cd313f86fb014b6cc93

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(yInitial, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math73
### Patch Diff Hash-SHA-256:

c4a98f4779894b6a75810a8d61ac5668e82d916de0fc224639673e3abe1092cd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy, org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(max, functionValueAccuracy));
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math73
### Patch Diff Hash-SHA-256:

35bcd79f1e5e772ca6aed724a53d02a6d55920370b43ddda55503ba3c98730b7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(defaultFunctionValueAccuracy, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math73
### Patch Diff Hash-SHA-256:

54a9c19959ae5feb20abb9851ece3f8394670a9a48725e3ccde8bac79c097b17

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy, org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(functionValueAccuracy, functionValueAccuracy));
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math73
### Patch Diff Hash-SHA-256:

5d2c680dd0092cc63ee16a4672f80ea23cfdbf73277914540901370ca8a26f56

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(absoluteAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math73
### Patch Diff Hash-SHA-256:

3ef6c129a53a736a1cd5c24b0412bf0a388d33445cc2fe4ff43470e882b3894b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(relativeAccuracy, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math73
### Patch Diff Hash-SHA-256:

f6c23c8c104589722ae991296a6c5c89878ff1dd7899669f30f8bbd9df672f10

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(functionValueAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math73
### Patch Diff Hash-SHA-256:

5865bfc26e0c69815548a112ba47e397e449f903e379b0268e8072ae8fa02dc8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(initial, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math73
### Patch Diff Hash-SHA-256:

a4d97ca160d8b078b08d12d5ef9bf93a1ec6f44e6c7a7312900883291a3f982d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(min, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math73
### Patch Diff Hash-SHA-256:

ef915b0539d44bf7c8df49489422ed6b134963e8b7244adcead55adb803f8217

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(yMax, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math73
### Patch Diff Hash-SHA-256:

68a11043d6939f659006566a552c0cd19b925c71c93787738965c585fbf46ade

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(defaultAbsoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math73
### Patch Diff Hash-SHA-256:

e8e0dcc724bd1db72e2e7b97aca3c7b077d7f629518f2abd40450fb7a748bd77

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(max, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math73
### Patch Diff Hash-SHA-256:

910c1453245ed499321fc1f653fceba7362eff460860bf2d937269e9ecc1d1fa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math73
### Patch Diff Hash-SHA-256:

c6285c8a10369c4e3cb5c9e6c5406e9d8822896cba0ad36f25d9885df235a451

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(defaultFunctionValueAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math73
### Patch Diff Hash-SHA-256:

a0bd667efb769c93ba98e073e3fa294f09bd200b63cbae7f96522bba18af60d3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(absoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math73
### Patch Diff Hash-SHA-256:

f887d2557d75283790a143225a740cf2adfff72fc4e401648ba687551608ee8f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(defaultFunctionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math73
### Patch Diff Hash-SHA-256:

777297beb194443316051660b9da423e988c7c677fa0d07a131a08e3bed54fef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(relativeAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math73
### Patch Diff Hash-SHA-256:

1b57a50d617b3bfb90bada50aa7600da5b10042157c5a34014b09eba81159cf4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(defaultRelativeAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math73
### Patch Diff Hash-SHA-256:

1b8ae0ac523ee248e7f3de16e85167f2a31cec0d8443f889829c6b5f900d4cb0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(max, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math73
### Patch Diff Hash-SHA-256:

ae64327f319415f9f5bee297273220a5893c9af980c8dad9e6e73656867017f7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(yInitial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math73
### Patch Diff Hash-SHA-256:

ae2e48f9d056bea75103a29aaa1696d3979504b49bd5e7186cb33766a6a75c1c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(functionValue, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math73
### Patch Diff Hash-SHA-256:

8a180f90c3b7263273c16dfbe3406e80d0c3f0059db7b7a4d5ff42a90da9c756

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(min, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math73
### Patch Diff Hash-SHA-256:

4e14bd28da431b412994f25ec7d0d5e606244a870666e4837cb8dd6d3982b30d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(min, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math73
### Patch Diff Hash-SHA-256:

91cd2c1026060e270bb79b79daa6b9b8fe098f476bdd05bb8bbcf39f4935282a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValueAccuracy, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math73
### Patch Diff Hash-SHA-256:

a7201df434c5421107cded87560a96140660db60887594a4a306e71f439a626f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(initial, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math73
### Patch Diff Hash-SHA-256:

df32472de186bea28526b7b6175c80f725267ce3d407a841128007a2f81a8c96

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(yMax, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math73
### Patch Diff Hash-SHA-256:

6d26250dbcdf5d387c20f7d3781acd350537715e8a35239a8ed1d82e2699ba5c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math73
### Patch Diff Hash-SHA-256:

295c30d78ea03c9bba26532b5a0df64686d57f5ced1a5bf960b633f7aadcef43

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math73
### Patch Diff Hash-SHA-256:

9679734eebe062e4b64497e345df3f7a04f08e4e0929fa341a0ddb1283dad301

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math73
### Patch Diff Hash-SHA-256:

2f23f8a79236b2aeb05b33db05a93908c5232d85f548af78ba8049e65df43c5a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math73
### Patch Diff Hash-SHA-256:

f5a4d5e4b6847c043db5359d3aa1ad2216432ccf5e5d55dc1a644b7660483d87

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math73
### Patch Diff Hash-SHA-256:

b30a839858db01efc9fa688dd0a959c897bdb3dcbab93a7a8609075323514e93

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math73
### Patch Diff Hash-SHA-256:

b7293283112e109097fce5da94fe7bcc08d2578b1073bcba52f230300923a44c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math73
### Patch Diff Hash-SHA-256:

0b3ed4d434f9ef2d7363c909698aa126244157e567869747de2c527a3b8d382a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math73
### Patch Diff Hash-SHA-256:

26b8bde6fbf8002ffa55f9f86953c519f981199de2368fa080319e90b477075d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math73
### Patch Diff Hash-SHA-256:

807d3154528ac0559c5410e495dc7f8fc237f0b5b742f5fdd093b6154248a955

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math73
### Patch Diff Hash-SHA-256:

4d7cf3664c4331a00ee307a6ae8cc7dcb914504ba9563a29392630723ecbed1c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math73
### Patch Diff Hash-SHA-256:

9cf67a6926eae3d00db321b071ffc1a2018a616c9eac6e31b22ae75d5ec26893

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math73
### Patch Diff Hash-SHA-256:

7d7941930f465fa09b11832fb5b0264303e9ef4d8b0a7aa16268fc1d752f7f65

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math73
### Patch Diff Hash-SHA-256:

6169208900ea8e481adc32c24cf95dc7119811bbcc84ef9f7d54fd018dbe71c2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math73
### Patch Diff Hash-SHA-256:

509187da945f2fb0240b91cf50ff331055f3dfe989cb3bec7f6cd338cb4cc0a6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math73
### Patch Diff Hash-SHA-256:

41f9a9825e729790c0b05b007f143add23a3189ad9ebd847b4c5f28bda4dae30

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math73
### Patch Diff Hash-SHA-256:

1e57ecf168d68ba1384b32a62d7aa21aec97d8a7b2245ff5115c37dd09ed63ef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math73
### Patch Diff Hash-SHA-256:

be03ce6fb61e671dbfb2ce3eace729e5b33a09da0ed19b28f0070374f95223d7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math73
### Patch Diff Hash-SHA-256:

572adb0d6db7ca05b2506993354333bc8c88bff0308c04a262a531c1c4f3a640

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math73
### Patch Diff Hash-SHA-256:

9760d8a5fc839cbbaaa135d036cc3051c641d8f4b5c7e916d999c2ff73153471

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math73
### Patch Diff Hash-SHA-256:

aa4d04b1557f9f14cadc8342319317a3bc65a51109fa653c0204a62bb5958737

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math73
### Patch Diff Hash-SHA-256:

7de5c0482314840aba98db55fa52e49eab795a6a3026a917b130ac98bc7145d9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math73
### Patch Diff Hash-SHA-256:

18c1a29ce440b2cd323082a65262a87fcac8e68a678b4cc62023eaa0f78e7455

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math73
### Patch Diff Hash-SHA-256:

60c5dcb92ff748aa3b9ce6b5c809f5bd59b18e5b54d4941e183c8906b3c57cf9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math73
### Patch Diff Hash-SHA-256:

7d7a91533656b5bf5ddc088f49a25cddcecb03755f22818d6f706bf0f7ec1013

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math73
### Patch Diff Hash-SHA-256:

aa313a34a67d265e082f7d30c07efeaac55c2100338ac9ffd18600b09ab14a95

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math73
### Patch Diff Hash-SHA-256:

8570dbf92bdf2b8691ae66605dfde2cd6c621de8493154b6be2b6d146738bc79

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math73
### Patch Diff Hash-SHA-256:

24731548a980a425a611db745554a9c5013eeb81e8ff8bfbdfb298ed3cee19bc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math73
### Patch Diff Hash-SHA-256:

e37be60da6924931da35db45bdbe49b6c1c3fd2d4c44918f211035a05d7d3395

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math73
### Patch Diff Hash-SHA-256:

793f2b57f64f9f360d90c455da1127b63de848cb9ebbd80c896df7e2f3d331e6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, initial, max);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math73
### Patch Diff Hash-SHA-256:

d2b1b430a2258cff7def55ff5d5c57bef469b4511d940d6a31fa6ed1d94cfb95

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math73
### Patch Diff Hash-SHA-256:

95262c0ca0dd7367305abe59c4a466d5a650d6fdee9e15f04266deb1f2b76b77

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math73
### Patch Diff Hash-SHA-256:

b447b631601cdeb6a467e6b3ad8dac653124cf774cd564e7f41a861e7b47ff65

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math73
### Patch Diff Hash-SHA-256:

1c21806f77cc0d733b8a4c1be61aff1e5492e57ed48434c5486b25e3fbc973ea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math73
### Patch Diff Hash-SHA-256:

4583ec64c6b29a4392d4b880b52134806654e674ff42757d03bbdd130157a2e7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(defaultAbsoluteAccuracy, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math73
### Patch Diff Hash-SHA-256:

2f3a4d7000b828eecd99e8e0d34647e0bab25662d71c4fe5eb26635ee3817ca3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math73
### Patch Diff Hash-SHA-256:

8b93e840248aff56340df9670baba5384adfcd9c71ffe47b16e965f7718ff8f8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math73
### Patch Diff Hash-SHA-256:

05141770effe64d58715e1ecebfd5167e1f7c1cdbbe719df4a9779b4bf2b33f5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(defaultFunctionValueAccuracy, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math73
### Patch Diff Hash-SHA-256:

2dcbb4fd1a45e752dca83b6b3db93eb9714619256b9dd6cc47bb3661b9a9482b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math73
### Patch Diff Hash-SHA-256:

35e7093260c3440addb830c14ce591779d7afa89e8186793bc6de2a26a64ba24

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math73
### Patch Diff Hash-SHA-256:

79956ff55b3674b7096f3b8ca95e23b59272c7b93552f538901a43c9f19aa3cc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math73
### Patch Diff Hash-SHA-256:

dcb93fc1df2137a3e62dc0a367a812ec5bfbc082e11e93e8d5e85cf3c58b2de0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math73
### Patch Diff Hash-SHA-256:

d89b19f2c1f2298d63dc9e89ec35d4e3e721b27e93cecbee4720c2bd09f5b208

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(absoluteAccuracy, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math73
### Patch Diff Hash-SHA-256:

fa29ceab762244304c881f538913817c54ffa33c3ab10259790a1a0777505b0b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math73
### Patch Diff Hash-SHA-256:

2370d00ad67d9e1af31cdaba8723cca4bfd354c04d2304554adb9122b50df853

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(relativeAccuracy, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math73
### Patch Diff Hash-SHA-256:

564e642ef8179cab862a4653fc5c390981cde755b835f46629659d6de48f3592

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math73
### Patch Diff Hash-SHA-256:

ac843b535f55a6fe12ceccf6ab25ae43fe183f15d4f01263ebd6a45a3dc34985

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math73
### Patch Diff Hash-SHA-256:

78ea0f2d2654acbb9acbb909ec3ad55ed641da473b8ae8ffaa91770ec8e6aff5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math73
### Patch Diff Hash-SHA-256:

a592172c036a94a2f33589ebf527054ab0f8977d0f5026f7a044c1e1eb218664

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math73
### Patch Diff Hash-SHA-256:

8f9da7b6191d7d131e642ccdbe9f7a0b85186b5f8a7f15829032ad7517c4c35b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math73
### Patch Diff Hash-SHA-256:

40469aad59020280660b82b60cd91198d47b4a3cd78d6780564bcd11984055e6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math73
### Patch Diff Hash-SHA-256:

a866c4c392bbb8dc6c68510b0fd67e0575f0f155cca25f13ba3a87ea4fc810c3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yMin, max);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math73
### Patch Diff Hash-SHA-256:

e88fe60b33c6a01b3be4a4f34eb1a3de99b5e580dd4ba6dc03046a3de7b2bd31

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yInitial, max);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math73
### Patch Diff Hash-SHA-256:

dfa68c59b51717055a4ddb187e36f2ab87ca102f72b6b282bf604c7850220892

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math73
### Patch Diff Hash-SHA-256:

1afdc27c96152113ff499cc75a4c5ed57e0bc7c2e245b995c01f13964667d814

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math73
### Patch Diff Hash-SHA-256:

c3c279ec89ec3e7cd45262cc1a3dfb309ae97419c74405c995123872550a9c74

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math73
### Patch Diff Hash-SHA-256:

e06c55890973c50f6d50fdae7f76b38c9e7342e16f9e981146574a62a70b63c4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math73
### Patch Diff Hash-SHA-256:

d39f8103243c5391aead85993372bbc3af42bba2a7b1ba76b9561d54caa3170c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math73
### Patch Diff Hash-SHA-256:

773b1cca70336742b46062994adb4ccaaaf82be5c941a7584d0b5e8be7ce21f7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math73
### Patch Diff Hash-SHA-256:

ec44611aaf7a82326a68f8632033cb5d22ef24fbc93650c4832e73e7ff2724fc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math73
### Patch Diff Hash-SHA-256:

73a984e8db5d0e9930b07516f978fc1f1d92e908bfb1f27763649c9e5a5a8e74

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math73
### Patch Diff Hash-SHA-256:

4942e7dbb08fa267e665be11ae8e8927a5099d36849bf5117fcf687aab992b6d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math73
### Patch Diff Hash-SHA-256:

35ae0aa332a74c6b7ed6539d64ed87857a8b735deaaea2c1638bbb8775884ca1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math73
### Patch Diff Hash-SHA-256:

f67265f7366d606ffc2387e7685563c00e1481b0be5f114c52bfc12be9298815

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math73
### Patch Diff Hash-SHA-256:

10e383c186ecdf1058361babaadbac86575e647854e563ca2711d99f5f86048b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math73
### Patch Diff Hash-SHA-256:

b2ac9cfc537db65613cf9d8991ada0771ab8d86d1aa563890d9b06743acc5f01

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math73
### Patch Diff Hash-SHA-256:

4918ac90b7f79b12abf2979225144089e78714ddc8a0137325fc49739a765f22

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math73
### Patch Diff Hash-SHA-256:

91043c908d5492eb2f3d0c3987c8edbd7982f48eb0194b743eb5c6823f41f678

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math73
### Patch Diff Hash-SHA-256:

820d967adfcc4d605e4d5c489c9f8ab04388a1e6ffbe2f09f5630a00f4c424eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Math73
### Patch Diff Hash-SHA-256:

46a5f46be5c40d122f2c3b3fa3c8163e31fc9920dccdfc7e75c882d6ac459134

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Math73
### Patch Diff Hash-SHA-256:

46aa4238ebbe5436eb1f7fb415c1c9b959e091fbe9b641181c2b054aff316b8a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Math73
### Patch Diff Hash-SHA-256:

147a1c919ca8ef280527163617a520e963e25f0e6e72d0456f5707c192952291

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Math73
### Patch Diff Hash-SHA-256:

b909aaab4df653b027a6eed0731b1864892e463a1eda12ccb8be82cc100be9d9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Math73
### Patch Diff Hash-SHA-256:

a4b6fed48ce5b00e95140e349379c05b188967e9e6d363106c44ff8b5b6c0885

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Math73
### Patch Diff Hash-SHA-256:

12d2349d34f0d4c28364d8b36d617ed228de2001fbf487f6ddd008aba99c0e85

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Math73
### Patch Diff Hash-SHA-256:

fbada6bff495055ac3216c850021278741fe5c97cc0d4e3c326f19c88165e532

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Math73
### Patch Diff Hash-SHA-256:

e286983f47f041d2e41c5f9947d16c0d53b883b6ecee37712c1ba1385ef432f9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValueAccuracy, min, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Math73
### Patch Diff Hash-SHA-256:

66dadee85408a2b9e133a10af33cb39e279358460587ebcfc7a66eb3a8b06b37

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValueAccuracy, defaultAbsoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Math73
### Patch Diff Hash-SHA-256:

1926a153b1573d5f9f1f18a65773a47545a71cedc320eb364c6942f618a03921

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValueAccuracy, absoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Math73
### Patch Diff Hash-SHA-256:

597f9c75c503f7daeb830fb431f07565b05a7fd3bf83f24089351eb5566399fe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValueAccuracy, relativeAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Math73
### Patch Diff Hash-SHA-256:

9f706aa24a19626a81791a9369fcbcd247704403e266991d765fffbf267ac08d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(defaultAbsoluteAccuracy, min, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Math73
### Patch Diff Hash-SHA-256:

025e7fa25650b1e135e88daa17dd2be951b5c7ba19b4717f6bb4e765c610b457

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Math73
### Patch Diff Hash-SHA-256:

ca9c7154808ad7fd899f15498a58c6b938ce15f2c046d074f000fa8d01632833

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(defaultFunctionValueAccuracy, min, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Math73
### Patch Diff Hash-SHA-256:

8052e7158458b1e3b0c47fe3746dd3841d3404f312624c1972569ecd811ffaf9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(defaultFunctionValueAccuracy, defaultAbsoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Math73
### Patch Diff Hash-SHA-256:

e93e1690960b2f611ae1c8c6bbd0bc7ad4a2f5d11cbacb12769ed8edd38d387a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(defaultFunctionValueAccuracy, absoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Math73
### Patch Diff Hash-SHA-256:

12e9011880bccd76ed1d61d9e3dc0f1e423a9d50340db9459f70f16ef9f86de9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(defaultFunctionValueAccuracy, relativeAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Math73
### Patch Diff Hash-SHA-256:

43cd4953db58a58aa32cd86a5b0b841d3122938ebffcb968c3cffc266d3a9009

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(absoluteAccuracy, min, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Math73
### Patch Diff Hash-SHA-256:

f748ef95cfdbff7ed9ff949c86e353122447298079bcfdbbafac42aa1cc7f234

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Math73
### Patch Diff Hash-SHA-256:

99294b0695fb1c42c0336a3d0b20b3a6478f2913556024a1ed179a4ed36d4b2f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Math73
### Patch Diff Hash-SHA-256:

0e9ed3d5d324ca5371f78c565bea5c8a1467eb81860ed05ca49ee11739f5b8b0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(relativeAccuracy, min, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Math73
### Patch Diff Hash-SHA-256:

79395c4a96bada570d35c65292220e482e0e0fde9dfa18f39fe28ac952eb85a6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Math73
### Patch Diff Hash-SHA-256:

7cf1780151911f340b5b064828557fbcfac8dbed8ad12ecc341a119caa4bc451

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Math73
### Patch Diff Hash-SHA-256:

f104f2b231b631a7fbb19028823c5f145877ed27acb0559ed443aaf405f8592c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(relativeAccuracy, defaultAbsoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Math73
### Patch Diff Hash-SHA-256:

ac92455003e66d6c3d2d0f273eecf6e1c362d939884c4e43423d5ede72899a5c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(relativeAccuracy, absoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Math73
### Patch Diff Hash-SHA-256:

4aedbbdd5c01a7734a65389627d5e5ece2e2f2ce36dac041fa0b09002197e410

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Math73
### Patch Diff Hash-SHA-256:

e1bfeb3b39df5d646270dc877c5f552007105ac8513b4538615e200f444bbf0c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Math73
### Patch Diff Hash-SHA-256:

93c1c09a5cb97dd75b026a4453a0b932530d69f14fb95944c087622166d56c24

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Math73
### Patch Diff Hash-SHA-256:

2462517d0ec09dff5e67beb6e5b6444a1943d935dba56e6580b64826a5746ca4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Math73
### Patch Diff Hash-SHA-256:

44b40123f4b6d3478f66cae33670cfc6612da925beb373f34c35543d40718588

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Math73
### Patch Diff Hash-SHA-256:

47666e0459bb5bfad36d1886507397dc47489aadcbc5c181d36e47e5933bd866

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Math73
### Patch Diff Hash-SHA-256:

9157e3234466a38eb0b15b25ff80a61b314d907bd423163706aaed55b20f848c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Math73
### Patch Diff Hash-SHA-256:

d65ac6c02709f03b6086b354918c8a2dccd59e096d56f4db88cc0b41a04ede3f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Math73
### Patch Diff Hash-SHA-256:

f35f16ce4157bb8a45ad721cfc1c6c475a4fd931694deeec76b7a32e981343b1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Math73
### Patch Diff Hash-SHA-256:

d30ab25e8c5d074d92f035d366c3adae430026701668bb236f99aeababe1b54f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Math73
### Patch Diff Hash-SHA-256:

68ea0daa263843e8b0df0f5b261cf70eedeff0dd3c78fd705b3de75f97ba0668

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Math73
### Patch Diff Hash-SHA-256:

cc1e931a95e877e144101e4379c2ade9992c9b33b44066717c84ea1103e49c06

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Math73
### Patch Diff Hash-SHA-256:

6ad88a544a0e08742e909e917bd85b62380e86acdcd1b4297023f1261135851a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Math73
### Patch Diff Hash-SHA-256:

d0a84a34ac820eca68195f116e335f0c2f659892a44efe1e53cd102249e41348

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Math73
### Patch Diff Hash-SHA-256:

723491b23317a961ba8463847b5d33ddfa3d6fb484df90a148c9dfe714ea0d19

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Math73
### Patch Diff Hash-SHA-256:

f0db5290cb4f20fb0e61d7544b157c7af7a3cd86f3f5af9bee84cdcd9548a464

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Math73
### Patch Diff Hash-SHA-256:

2d36d8364cad1aae5d34c7b3d4a9aa01a3b12ba4402e27b308b7b4e7519a7aa5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Math73
### Patch Diff Hash-SHA-256:

1a72db9abc4129177f6fc29a87e0fcd158e01dad7398810ff68412a0697ad066

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Math73
### Patch Diff Hash-SHA-256:

6860aab6482a8eccda8bc82074c964784aa7a8eb1bc41cf372eb3fc45b016283

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Math73
### Patch Diff Hash-SHA-256:

4cb5bf88422d6927d18a507de43b674756434eb7ade948be34003cd7474b3ab6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Math73
### Patch Diff Hash-SHA-256:

f51c2bdd05a497c425f01a6d03d09a1f9913fc3c8ce4de21cf519b2a5cb36ee8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultFunctionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Math73
### Patch Diff Hash-SHA-256:

49b9a316eec46b12b1fcc2a49a863735adf5868bdba0e969675eebb75220bc9e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Math73
### Patch Diff Hash-SHA-256:

8f936db7a69049562a282dee4fb60cf5cc5938f7b5347888bd48e680d73f4580

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Math73
### Patch Diff Hash-SHA-256:

462be20978ea1cf3871028a8be45971779372cee97b6173e5e0f005daf4c0bd4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Math73
### Patch Diff Hash-SHA-256:

345d5a45554601d9da1d46605cc7565e25d6c3caba94eb60817fed22ad3fd40b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Math73
### Patch Diff Hash-SHA-256:

9734ba8495f6adb68e44aee4fcbf51837546ff15741eff28479d7d4f817694a4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Math73
### Patch Diff Hash-SHA-256:

85588f7998e4e1a0a88a165f0b23e363cfde77d8953e477b6c50afa7b0724dbd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, max, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Math73
### Patch Diff Hash-SHA-256:

59a8051f68aa61b2068ba8232d7035199553cd6d71bc5dc4dbed41cbd3cb3143

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Math73
### Patch Diff Hash-SHA-256:

382691919fe2b006c65c562de64546c433fd7ec529ea737a7f0821e4d5537c3f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Math73
### Patch Diff Hash-SHA-256:

cbb806aa1e0f0b9a6d10c952f5abe9ac82455a4027fc327c6599fa8b9976b6d3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Math73
### Patch Diff Hash-SHA-256:

7ccd93a7ac44d792cef8890b45b48f36520ab37117d4913644048cef4b8d910a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Math73
### Patch Diff Hash-SHA-256:

635b007d1e284770d89d0590bd058e4505957edbd0280ddf8fdb639b233b01ea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Math73
### Patch Diff Hash-SHA-256:

0d88c233fff50f2160380afc717b2ba2437ebeed3a49549da6c245945e5703a5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Math73
### Patch Diff Hash-SHA-256:

f1275c240b25a18e3257a56987e9c1082604595539882bc61c78e281640e8aeb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Math73
### Patch Diff Hash-SHA-256:

119a9e86426e8b7765644321a22eac5e4fab69dc85b04368e04849100f67d6ef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Math73
### Patch Diff Hash-SHA-256:

9979c6e6d8326e7c05cbf5995012194a18abea0dfab0119fe738a7421987b2b3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Math73
### Patch Diff Hash-SHA-256:

37d7f3ccad18ddeb44bd2609a987a259f870547d719fccb67bee11252ca41a2e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Math73
### Patch Diff Hash-SHA-256:

757b5dbea254120d94b8b9934bfd4564ef5be73c0825ea403cfd5ff1aabfcad6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, initial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Math73
### Patch Diff Hash-SHA-256:

07ed441a5c2db814ff09642f48d4065e538dd71788a3d643319b906c4ca10458

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Math73
### Patch Diff Hash-SHA-256:

e09ad73df6574dd97258683eb0ce17c35b0e347abdc42f41ceb0e475a310ad7b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Math73
### Patch Diff Hash-SHA-256:

0ce61749c7b349db8be12ea4f7e5bfe92f2a3a55dd5d6bb16224b9bcd3a3d0ca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Math73
### Patch Diff Hash-SHA-256:

ecaa42c5773f58ef94484a57222b42f7bdfd82dc172fc4de32cf3fe80ce8d668

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Math73
### Patch Diff Hash-SHA-256:

bcc86885c536d78987da5c40f3c6f74e7fcb09da243300739c224d24514e4ffe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Math73
### Patch Diff Hash-SHA-256:

dd780e1e5e2513e41fa4598131ca0de9e53945fffd301bc43780094cc10207e4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Math73
### Patch Diff Hash-SHA-256:

6a7da457e9a85a110ed3438ed66e55854f5b8af72835d080471538b06afddf7b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Math73
### Patch Diff Hash-SHA-256:

aac7809ba8db6299f9763670fd9b435d28483ba1f5feff1e32cc89566d72bb0c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Math73
### Patch Diff Hash-SHA-256:

6e3dc6dd3eabdb8c8c0f302ae55e88cffac2f2ea13968fdecdd1dcfb4489f0d3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Math73
### Patch Diff Hash-SHA-256:

fa54ced151040949d5aca46741e257edc5f210c09f58c22e20e12b6cbfc61a6a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Math73
### Patch Diff Hash-SHA-256:

8536ad0867e51e1008ea1555df8ca525a3aafed59b7936640f1ab6563422b6b5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Math73
### Patch Diff Hash-SHA-256:

28c54dd2d218ffeed925756550cbbc1e2439a618115acba05612d2b4cfe05522

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Math73
### Patch Diff Hash-SHA-256:

e619a18737d31581d51c01dc1cdb5af8e68826aee6667022c138ce0f6857517a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Math73
### Patch Diff Hash-SHA-256:

fa45256f23715d90cf9cd35f1d5c405819b1ca6e213366bd64aa0ddfe98b3f30

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Math73
### Patch Diff Hash-SHA-256:

ebb814ae3ae7a4670c85da80710a7f7c5b9a53688898983819f7f1222d3a43f1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Math73
### Patch Diff Hash-SHA-256:

8e68113d34f1f113d1481f7aaed84565f4ffe8c06c5c146f3752ccd781b80137

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Math73
### Patch Diff Hash-SHA-256:

9cebe5f8d3f626fdd9c3edaf73cdbc78b70c4fbd6f50c39a8fe8486339774b2a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Math73
### Patch Diff Hash-SHA-256:

e9312f757814dd79241fc7bc0ff030b2c6e51cdebebaef4520bf4545c61af457

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, min, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Math73
### Patch Diff Hash-SHA-256:

2ee273729bc0f8c130ef21be7d53682f1223e9960b1b260bfca7096e0df98713

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Math73
### Patch Diff Hash-SHA-256:

d2f56754826e968297f3e6a87322051f52879d13cbb3b9404e9dbec2b2be2cf0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Math73
### Patch Diff Hash-SHA-256:

544e26afcef62dd4b2cedaa52360c2bdf3766199667b0b9e0e1cf9b23e7d1f7c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Math73
### Patch Diff Hash-SHA-256:

43226b03e87a64fe621155f837414b8105be069ad72aa1bb8e92060741aadaf9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Math73
### Patch Diff Hash-SHA-256:

904ed35f171c701406691256b75c66d5e28d177181349b3b478f952f37e2567b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Math73
### Patch Diff Hash-SHA-256:

8dbc5953e7383573168edeac9da52c6d4f2bc20caeef10dd5b425c86c84b10eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Math73
### Patch Diff Hash-SHA-256:

b0b3f78669e2864c186e8c6aa5c9c642263df2eb30076096c925c7171fc0a847

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Math73
### Patch Diff Hash-SHA-256:

216d281667e84ea0f36f177998649902a916cf1452d1c4ad3979445f43f9c44b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Math73
### Patch Diff Hash-SHA-256:

49534c3bbbd6eb9606b3eada59ad1f6ff343811d7f927931e34adcb69299c5a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Math73
### Patch Diff Hash-SHA-256:

350a5e58860fea5fa2c3373df94c2ec482019ff1fa69ddbace7d69131ff3d32f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Math73
### Patch Diff Hash-SHA-256:

dc156d0f57f391e0532f47303169d803c2dd6c971e35a1ceb75b44aad0bcbce7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Math73
### Patch Diff Hash-SHA-256:

54147d3fd49848a01f5a0c0a773318bc8081781a1ca2d12f405d953e46aa455d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Math73
### Patch Diff Hash-SHA-256:

63a1265748bf8a9d9c87240e54010fa37c64fa11cae18231ee85afa9f28c9618

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Math73
### Patch Diff Hash-SHA-256:

0266725f0aa61129183334127bd303b206100d01eec9e75a8a39b44f1e5e4ee3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, max, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Math73
### Patch Diff Hash-SHA-256:

861b074c6a24c059d377e0411535628d2ab9c697da2182fde160ed41dfa89c83

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Math73
### Patch Diff Hash-SHA-256:

67a4f1c4b50326041683af6b0908e10479f1d5ffff84d4637232796d433e845b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Math73
### Patch Diff Hash-SHA-256:

15fa676d1797eac142c4b64365dd41b21f7580bd3603b6c2da82b8a19deb627a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, relativeAccuracy, initial);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Math73
### Patch Diff Hash-SHA-256:

4dc6f19821f7de6213c632d671fafe01eb60d10eb8e261bf90b934bb54719aeb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, defaultRelativeAccuracy, initial);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Math73
### Patch Diff Hash-SHA-256:

9552d1045a31d1fb22fb8382da3870ba4de631c5eeb044935313e0324061b1af

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Math73
### Patch Diff Hash-SHA-256:

1c068bae525513cfefbde516a2677eeac64071282e4b3d8fc24b00a5d3b31013

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Math73
### Patch Diff Hash-SHA-256:

2aae50a77e36b5c6cfd93a8d8aaa86ed76d4233c4a83a6e4e9e41e482ab56ba0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Math73
### Patch Diff Hash-SHA-256:

9dae5334e00c585cb1e81b3faae3534a9d8365abf79b4cdd32d828dc1ea760cb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultFunctionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Math73
### Patch Diff Hash-SHA-256:

65658b54c900857345b10abb34aaf5c7cf34e982515dc18e3cd4dbf6d3d9b2ba

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, max, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Math73
### Patch Diff Hash-SHA-256:

0563f607474e1c49afbd8b1b6ee6249fb2733ac63ca80ab79b5f1177015e0baa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Math73
### Patch Diff Hash-SHA-256:

9e548f67e3530b8fe59349387f201c7523da419ca3b3c0ee09306822a807d0e0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Math73
### Patch Diff Hash-SHA-256:

9f0ea8a28909d4aaaf76cddc01eac83afd2c985abb6a9af6e9527b222205beba

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Math73
### Patch Diff Hash-SHA-256:

f0c964bc613fd4f0be6098e5387de7cfd178d0cfbcab35965128ee21d220c6ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Math73
### Patch Diff Hash-SHA-256:

2994e16dbef028a105cfb3af54a0be26b6785502a9784c12a27cc46bf54bab50

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Math73
### Patch Diff Hash-SHA-256:

d541cd23512b4b4f1f758792ad3c9eef0d7bee1fd1dea11615fff436b2d19663

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Math73
### Patch Diff Hash-SHA-256:

ef56f4b43f8900232f43a54f990caca144a9e17a84efaaa2ff0536b339ce2da2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Math73
### Patch Diff Hash-SHA-256:

2c2742e228167e488fa7266abb214ee1f6a12bd14bd624d99181d1cafbe174b6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValue, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Math73
### Patch Diff Hash-SHA-256:

b1248c8406db4ccc67a76760c19224dd5fd1a00f77ef3331956db671f8c71f82

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Math73
### Patch Diff Hash-SHA-256:

ebd6feab87a70a828a850285600c26bdee536d842def0ca4cac5a7f77735b18c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Math73
### Patch Diff Hash-SHA-256:

765c129f17a782c08eb9b4677c764c182e105b3894e2f3ab01c7740cb68d6f47

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Math73
### Patch Diff Hash-SHA-256:

69d9f2a023733d304f0f535c085882dfd8edc73f6af6188d45123bad09d41a70

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Math73
### Patch Diff Hash-SHA-256:

9b89138c494ab0cc9a5b8c04cd344335abe6e08395c396db8845cb9b45a22082

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Math73
### Patch Diff Hash-SHA-256:

0fed2e14569bcbff7d3eac309592ef6927f8270ee760357b71fccfc57434afaa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Math73
### Patch Diff Hash-SHA-256:

188aef939b8f553f3f439379ac64088d22f3fe2c2000f9361865d7a1e0484a29

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Math73
### Patch Diff Hash-SHA-256:

0761e6e5dad57737b0b788176087df0931b014a484ec6ae6ff5dc3e1a0afc2c9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Math73
### Patch Diff Hash-SHA-256:

c0c410408abb8b9f0b9f8044a56aba6bc2e9913927ae6948051be07592e41e8e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Math73
### Patch Diff Hash-SHA-256:

c34c09529af7c5a211805b1fbecad09b28fb7407442d485c2b82213300ed5d7b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Math73
### Patch Diff Hash-SHA-256:

984a6a803fdba55d404cb11558d0b7c8781df2614c8efb1c19a11063aa76defd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Math73
### Patch Diff Hash-SHA-256:

e280ee0cfe7dbab1a311c3d016c7186e6dc0c8f3fcb0f3ba411204cb0bf05c2f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Math73
### Patch Diff Hash-SHA-256:

3b7d0fa38c6afe21148bf35009ac7118a6045ed5172c05828ad4dc1a99d0d4ca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Math73
### Patch Diff Hash-SHA-256:

9ddd22a6df6457d5e5c55896d9440e97500e566fb65dd6f694e8841102811fe2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Math73
### Patch Diff Hash-SHA-256:

fe90451da82e7b59a690f270bc666409a5901927b34a6baff9e917f2cad6126b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Math73
### Patch Diff Hash-SHA-256:

b4a79952b27b404116975ba8482d9a891360127f04ec69a5699bfbe9a9bdf3ca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Math73
### Patch Diff Hash-SHA-256:

190d11ee1ca59eb7c2a1ba17b769c72ee47d5c5bcc9facdcbc3f1a3d9f9256ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Math73
### Patch Diff Hash-SHA-256:

708a8224a74408dd923a6345e14ec5c527432468c5b883bd9a32b344ecf84061

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Math73
### Patch Diff Hash-SHA-256:

72302d9c558ced64228a0090700faf3fb9300b5a01c245b0cd357746c5142d5d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Math73
### Patch Diff Hash-SHA-256:

4090ee18e308a064c4cda0ad9deb0b056ec2c9cb20f07ff02433fe95f0607ad7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Math73
### Patch Diff Hash-SHA-256:

a8456cb9b4b8f7b37fccb6129720c08ec3a2679ce185fa0eb8996a3a3e66ecf2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Math73
### Patch Diff Hash-SHA-256:

ccd27ec0d475fbb006e5217eb2caa347145cf782344905b9a92c16f84209ec5c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Math73
### Patch Diff Hash-SHA-256:

af64e5e594daade9c2655b41255b3f404fe0c77a8e9ae1afdd59f09175dc01de

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Math73
### Patch Diff Hash-SHA-256:

8e925f944a02253cc6bb127b8df63f5737418402346a117fb9e85774c55e21c7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Math73
### Patch Diff Hash-SHA-256:

376f1e4f6ddf20edc73c25f144ef57ce9ee7416a87e42db9fde055ffe337f43b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Math73
### Patch Diff Hash-SHA-256:

4d68bfbcbb6f0eb035387a73a3f83ebaae28dd6f283eb0ab6f8313f4d0fbdf41

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Math73
### Patch Diff Hash-SHA-256:

8182817ddfc352faaafb9dc109946a46804573832daed1b85ab6b0fa149f3fbe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Math73
### Patch Diff Hash-SHA-256:

dd60a978ac36bee754a7b4082413585194bd0a3320a3f548f86e82b5d054d6d3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Math73
### Patch Diff Hash-SHA-256:

e71fbf014dbfa40fb0a39ed00f1bd9571d320a1effaa09ab9ef467a9e25283bb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Math73
### Patch Diff Hash-SHA-256:

398c1d59d0eb3aa2a14d13311951df5cbf7101cd9f65bd206c0128cc911809a9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Math73
### Patch Diff Hash-SHA-256:

606ec1a3a33f09a8239e6e0404abaa58b088d92ee73ae6c093e119fb003adf6b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Math73
### Patch Diff Hash-SHA-256:

6e0ece006f586dfb33b86bbf81a42a90737db498764eebd3c5ff742aa8350783

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Math73
### Patch Diff Hash-SHA-256:

9edea1f16b0c70a0fdef8d83a98d76105d7e8f0623e900d7823e6f8ed3f145b1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Math73
### Patch Diff Hash-SHA-256:

e3d1b99ea40ca8986d512c91b99f5f601863441f4879fff75803aca806076c0a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Math73
### Patch Diff Hash-SHA-256:

a66a3b41d1c5fd8e42453cfef1c6250b1be18f81f0294712d08247a3d6376608

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Math73
### Patch Diff Hash-SHA-256:

486959a1ac1d67ca9b6215d36a3bf3c0744bb511c0c9bfc393ab1444cc72d871

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Math73
### Patch Diff Hash-SHA-256:

e6fc5a56eac0d776c3e342f3271b1d5006078eddb1029da57ab48846582d47c0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Math73
### Patch Diff Hash-SHA-256:

15fb6ea57118968a701b86d1899b5368974616a20953a46549f81112936cd753

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Math73
### Patch Diff Hash-SHA-256:

aab3e0f083cfbfd43fa91bd6206db72d12e20a40af7a50a1eae05c63bce77be7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Math73
### Patch Diff Hash-SHA-256:

d8adc2e56895494c4dad8a424bc1e41745dba96b6bdf1c6a1fda8e6a5c7f8440

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Math73
### Patch Diff Hash-SHA-256:

c62e7237c6e5269126e025a3e5208b7a1082a271acbb1da4f6dce369c47ab9e6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Math73
### Patch Diff Hash-SHA-256:

886c3aa5e06b614f86fb4ba9ef27728477d3b99f3f0588f3e98ac10dcff2348c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Math73
### Patch Diff Hash-SHA-256:

6d1c14f90dd5f7ac7feae97185dd07a4a5ed6241e191bf7412667eb7bba7b681

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Math73
### Patch Diff Hash-SHA-256:

e701f6800b1ea34baf79e697ca5064a5c0c107645cd8ad91c06ca5d795c8e394

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Math73
### Patch Diff Hash-SHA-256:

04efc2120e6b627f002b5d09c4c01a8a3abd59313151638ad2e756bcf39144d4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Math73
### Patch Diff Hash-SHA-256:

70572ab37fe121217fd2ee0910c69ab7f262c5bc0d1033c66925405f2dc066de

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Math73
### Patch Diff Hash-SHA-256:

fcb64e4033fad1ff333dfcdc20e46eb19b0508ba5d29607562d72b5f8f71d912

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Math73
### Patch Diff Hash-SHA-256:

c94a046e75eb2fdeb492f86cfd0e37ddb5263500c1220a79b8648dddae410ee3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValueAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Math73
### Patch Diff Hash-SHA-256:

ba0f4cb43171c05961ddcb1d8b13275741c2010d3fc605a1514dbfb97bb58616

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValueAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Math73
### Patch Diff Hash-SHA-256:

71c47ad6ac62ec59536be7d07ef733594de835cff616844a6ea8119fa6ebe183

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Math73
### Patch Diff Hash-SHA-256:

fc64093d5adbeefb3fb1dfe0c69f1ba2ce4c6651ae2bf343a4b302cc222604b8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Math73
### Patch Diff Hash-SHA-256:

52ecd67cc1cff2311c8f034d1c00f8574a9467ce3a9113c2765295e5e1ebfd65

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Math73
### Patch Diff Hash-SHA-256:

d6febedb52645eb4d12bf372f6fd7ac7a3d2b9e5f94df6f92bcd3e6833c3df5f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Math73
### Patch Diff Hash-SHA-256:

4e6f0def946f7290556b6380654137941c72ee3c30c4f067ac3c2c4e4783e3d7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Math73
### Patch Diff Hash-SHA-256:

907bf5fdd149509ebc77debbc90d46d8617eb50bc5916f92fdd33f327f524a76

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Math73
### Patch Diff Hash-SHA-256:

04a96b8aabd81c1ab8f3d03f6266ee296f303fd4178d60e0ac600fd509cd48c0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Math73
### Patch Diff Hash-SHA-256:

4a1494847ef62fc9a32f51bf7c02b67bb36e9eed832f1da5cba829b7ba242d9b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Math73
### Patch Diff Hash-SHA-256:

946eee276e198dbd265547ddabd8b387d7542c4bc673c95453b1aa8acc977954

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, yMin, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Math73
### Patch Diff Hash-SHA-256:

a2f612471e48b0fc7a7aedf13811065303aade2af01dbaaf5472802bf82ab8fd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Math73
### Patch Diff Hash-SHA-256:

e9109a969a2091f0d5b68140f5dddef0f6dca0122e10976eccfea6a2814027ee

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Math73
### Patch Diff Hash-SHA-256:

515f658867d8268f5788a8894593a360340ea2d1693e5e132df095903e1020ca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Math73
### Patch Diff Hash-SHA-256:

c25790d21f31ab2790602fb07171e487edccdc25b096e8386a76b8e0afa5c3c8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, initial, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Math73
### Patch Diff Hash-SHA-256:

4bb371576f19994634a0d2a94ce3d551b935821728bfbacf42b12d707bcf5245

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, initial, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Math73
### Patch Diff Hash-SHA-256:

d392c534c31ac2578e0659897aaee4d3ca8a02ee8480e4db70ba6b2091891027

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Math73
### Patch Diff Hash-SHA-256:

dca734781ce5b43235bf2ce71623cbe7ca2027e6d55b6189ba2871573ad7ef8b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValueAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Math73
### Patch Diff Hash-SHA-256:

af0e329329f50d64d338df33f9cfc87798677f6ec3a2c8b3be14a6ee688508cf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValueAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Math73
### Patch Diff Hash-SHA-256:

24fbf0de67fe87eb78e899c6201e4f7701430a7cc41aac28d7866424dc1b76f6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Math73
### Patch Diff Hash-SHA-256:

a7f733cd0c5e5a1cb1b26841b45804b2ad3ad554fdd408a56301caf2dff671c6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Math73
### Patch Diff Hash-SHA-256:

bc70de52dc063ccc260519b73ae2190d813a81f0b2de50bf0631a821bd676458

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValueAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Math73
### Patch Diff Hash-SHA-256:

046a9949dbcb3ef8c16feaaba8759bbfa66da9436437252d7e1e98a7be331751

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValueAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Math73
### Patch Diff Hash-SHA-256:

9d1c0e724eb0039da186015db2674b0939ae70d06ab9017ce21d9facbc642b1d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Math73
### Patch Diff Hash-SHA-256:

920d77d0488217e74563c3c37be9315b33d3dc836cbe8716244db98aa153931c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Math73
### Patch Diff Hash-SHA-256:

32cfcabc507803a8515ef75fce07b271d6cae34487a748f41052e8c1b5abef1c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Math73
### Patch Diff Hash-SHA-256:

5a56a3bf93a3ba5085cf21761be9dbfac71c90140ad8ba999747b56bb7723d9f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Math73
### Patch Diff Hash-SHA-256:

a51bf7b535e5fd869a67d9c10d30f1c6dc35e1650e7cdd072b267a332cfe3f2c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Math73
### Patch Diff Hash-SHA-256:

e06cb68225ff0d04362c830b11daa268c1e8cb94dc9326cf65a1c9795cf99149

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Math73
### Patch Diff Hash-SHA-256:

86977df15f6b75bace419b2330261086da684b6781ef985002e24518b1a5871f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yMin, defaultAbsoluteAccuracy);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Math73
### Patch Diff Hash-SHA-256:

a7094217e925d8259ee255ed9adc01c85f9bc5a19b0c8b769b3bee21c6083bae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, yInitial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Math73
### Patch Diff Hash-SHA-256:

c192bd8839909ef6ff1c4c7c35e66971dc9782499b8960af0dc10b3d916f923d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Math73
### Patch Diff Hash-SHA-256:

57df8d59af07c36cef727299d9c81c00444637d30809a5f456e036ae1c09c422

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Math73
### Patch Diff Hash-SHA-256:

c181b87cca477b459e819a8ab176684f72a34e282d763bef998497fe462cd6b2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultFunctionValueAccuracy, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Math73
### Patch Diff Hash-SHA-256:

cf657695d5a385272c7087c80a161128df7cb67159e3a527c11347a58408698f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Math73
### Patch Diff Hash-SHA-256:

b671c8f1b32a4c9133da53cc9820956df252fd26e722fba581d748254a89ca3a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Math73
### Patch Diff Hash-SHA-256:

2766386c0cf8c660e62c959f50361c9a952141f2883bce65e5fa325077a4aff6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, defaultFunctionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Math73
### Patch Diff Hash-SHA-256:

59905aa183aad7553bd877151418117de4c46d2bb69f7fc1c9fc75b4b0b09e89

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Math73
### Patch Diff Hash-SHA-256:

fdcbcecd6078e7263d9bd03e61f927aa58688525333283b4a940ee7707c61e94

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Math73
### Patch Diff Hash-SHA-256:

0e53b409091e8d945b8587ac6f1a15dfe255c56d3a6909f328a5993167284d22

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Math73
### Patch Diff Hash-SHA-256:

651ba532d91ce6ac962aed2c72c3835d1c1f67f4afe4eceaa364e51f57c20632

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Math73
### Patch Diff Hash-SHA-256:

fc623359ee12bda5eef092c036cc71b8f65ea1e92770475e2cea24372554124c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Math73
### Patch Diff Hash-SHA-256:

911ed52608603ea8a4030f08253238756a43e2ddf84d22bdbedb313819377bcf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Math73
### Patch Diff Hash-SHA-256:

aa7301b767c1a967b575eb0af05c6c8f6cf5eb8250ecb652155443e20074e17e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Math73
### Patch Diff Hash-SHA-256:

db521583da8a643cb9d809aac4852a2590d3073fec1003efddafb7ec8aac386f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Math73
### Patch Diff Hash-SHA-256:

b0c9902d069b23af05f6116ba961fa3d4ad4a98f7da3cee4cc6e3a1dea9bb54e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Math73
### Patch Diff Hash-SHA-256:

e2aca4798346997ce1393fc5e3f7877d6e970ff2d5c628593f13d958b667185e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Math73
### Patch Diff Hash-SHA-256:

e522c2af2d09a84d8310ca6262d58d76016555e09ce6c39b6c4e6078f98dbcb2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Math73
### Patch Diff Hash-SHA-256:

75892c30b45bdd7a3244f2590fe5ec0999b9c084346e6d96ba2e57bd5fbda839

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Math73
### Patch Diff Hash-SHA-256:

b99eae9ed969dd7a0b48341f30ff180ef307065852b6100a6b06a3e0e4fc4783

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Math73
### Patch Diff Hash-SHA-256:

b2dc0e5e4a8ec20399344ad4b0f231b33a55a3847ca04238361943faa414d4f6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Math73
### Patch Diff Hash-SHA-256:

db7d9c22d006335ee77807bd5aec6933b700dee6f37d93831d5beacb25f5a2bc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Math73
### Patch Diff Hash-SHA-256:

3af11c441218e0e6e428ed4e00b1f4c2e18a4a26b4f6024b72f79bea612f6778

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, defaultRelativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Math73
### Patch Diff Hash-SHA-256:

e0b53aefe1cea031a81741ff8ff246a5ef5a3cfb9fe2a9af6c514c5a9e7e02e4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Math73
### Patch Diff Hash-SHA-256:

38efc814eac017fcef9f76e4d52d66033c6eff02749df2a58e882ec9781fa110

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Math73
### Patch Diff Hash-SHA-256:

bd5af819eec234007405b784de2e89bce835a087a10002534119959dcd7de969

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Math73
### Patch Diff Hash-SHA-256:

4c1ae170f24df7046f7c4fba7a2fb0cac1abd9e8ddd3230bee4a12679ca87630

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yInitial, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Math73
### Patch Diff Hash-SHA-256:

ecbabc71c3d3e48ff1fc5bdac2996ba9af5334b800c687900ba845c6a9f08bd6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultFunctionValueAccuracy, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Math73
### Patch Diff Hash-SHA-256:

66b1ea4dad84afa82a7aaf27993b0bc1564106541e56f2d5b82633c66c4abc2c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Math73
### Patch Diff Hash-SHA-256:

e52e9ea2e99b7b33541bae27049354f9145a734575e2039a77f2d93c04de708e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Math73
### Patch Diff Hash-SHA-256:

84d313586263f72b3c2e0892fb2d9ba19043ba31c03dc594dcf81724b6916b7e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultRelativeAccuracy, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Math73
### Patch Diff Hash-SHA-256:

f085d31534b4ad23c80e07e3f50c8bfe5f5111fdb4f8eeaa9e557f50f14e5e8c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValue, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Math73
### Patch Diff Hash-SHA-256:

a75d333aa1a2f381aee3d92ec74916afac2520062de3fbabf90a23b1ff75b83b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yMin, absoluteAccuracy);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Math73
### Patch Diff Hash-SHA-256:

10aaa6e7807972a114a59a47460e811be331d15c02596643616bacd246f17b27

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yMin, relativeAccuracy);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Math73
### Patch Diff Hash-SHA-256:

f929a3c4a415609a0c5a1bcadfe995867507cc915ba613e5e21d6361bec76260

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yInitial, relativeAccuracy);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Math73
### Patch Diff Hash-SHA-256:

4c58eee5cabf185beb63eff14238afd86aa9a8840cc921abc94999b42ad8c1a1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yMin, defaultRelativeAccuracy);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Math73
### Patch Diff Hash-SHA-256:

8b74a57d714239f5a2738bd481a95aae73cd5fdcfef782b75977420b7e490c57

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,7 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
-		double yMax = f.value(max);
+		double yMax = solve(f, yInitial, defaultRelativeAccuracy);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Math73
### Patch Diff Hash-SHA-256:

e70895f364e5c8141d80b9ef282a0edf29099ad2e43911547dcc350c627e3971

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValue, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Math73
### Patch Diff Hash-SHA-256:

a5c39336b8a6c6cc27ac9327991ab53dc355ef18cb330d35a3bb170771f9f65d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Math73
### Patch Diff Hash-SHA-256:

8942accd60fa79b4b44c1018ed77fde6f0ef98f0e3e93cb9e6fbf75e68a33f71

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMax, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Math73
### Patch Diff Hash-SHA-256:

0ee503f300e22ccdf9f384c9defac09626b34fc2171fe6883e09d37e9a845738

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Math73
### Patch Diff Hash-SHA-256:

67973fd225e097808996902ad59fae3e63bbbc2500f94a4f1091370cf2afe05c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValue, min, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Math73
### Patch Diff Hash-SHA-256:

5eb4035ef28ad2d7444e5b50f8e6c8ac84c23cc0889c142c872eeb319df41f3b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Math73
### Patch Diff Hash-SHA-256:

430861f4861dc109cc30cd16fb1f79125f76c58a53ec5cd6f6c43bc986f0be5d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Math73
### Patch Diff Hash-SHA-256:

9c4317207b88dd3c6173d73e4410dec2cd6d8e3d9d6dd532e37f2207b2d7b5f9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMax, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Math73
### Patch Diff Hash-SHA-256:

2ff12c3edadbdcc38383beade3bef91b82c59254b87b1528107abbb2327c5483

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValue, absoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Math73
### Patch Diff Hash-SHA-256:

65345b489e8aaf124236852c20658a85f8a9928ddf70d77a8394b6afdd0fa073

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Math73
### Patch Diff Hash-SHA-256:

e4d49768e6b98ca09c815d26e2794fcdf8719452d4f53ca0ba0c1a6115b420fe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValue, functionValueAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Math73
### Patch Diff Hash-SHA-256:

f22d22cfdbd1d18e087de219fcdc1300e0347cb622509de441b3e4fa2d6b6f83

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Math73
### Patch Diff Hash-SHA-256:

1b7acd381de3b8f04fb2a7abee261e738a5ddefc07cab197b7871ff5f5852ca5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Math73
### Patch Diff Hash-SHA-256:

26121f354e30f51add0918ca77adf66f9d847fa63e7e14dfbdc6374871f07e0c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMax, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Math73
### Patch Diff Hash-SHA-256:

e68ec15c4bcde1d814675f17eb8a9707a5b328b4bf3575d178c8d4cdf59baf4e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMax, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Math73
### Patch Diff Hash-SHA-256:

5a728264fcf7a5a1aee487b0f3d45eac41134592707e85defcc9506aadcf1c5e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValue, relativeAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Math73
### Patch Diff Hash-SHA-256:

e80d42b71b0ff599b89660f2f72190119a5a6356cd6880900e3748c0db6c5b54

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMax, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Math73
### Patch Diff Hash-SHA-256:

64a50fb6b9eaaaaa8814fa5ad00f53cad9a802d3521008b00c0c211e23710208

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Math73
### Patch Diff Hash-SHA-256:

2b42d0aa7aa9135d0504c363034f8e6da7f007b4c15190cc65dcd18785555c01

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValue, defaultAbsoluteAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Math73
### Patch Diff Hash-SHA-256:

5d735ad71365b53729b2a22bcd756edff0f47b29f8aeeabcd44597fc4bef2e0e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -28,7 +28,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(functionValue, defaultFunctionValueAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Math73
### Patch Diff Hash-SHA-256:

eec9640b8baf09fa321f6ec0e1c274fed956fe4b47c0149260090ea317397504

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, max, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Math73
### Patch Diff Hash-SHA-256:

62e2a0b2ad3bdc61724bf347a42814bba59673d552a3cc63bb87b205eff12925

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, max, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Math73
### Patch Diff Hash-SHA-256:

e9e12be6a2dd4d99f283c4bcfa8e107405c01e0d5d3920cb75e6e8a4110a8ff3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Math73
### Patch Diff Hash-SHA-256:

7cddb7a9dd68c40dc771a808a67216f2328761c61363efbc3be955a439e1c462

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Math73
### Patch Diff Hash-SHA-256:

1edef06cd0b8c397c7c27e051ba17477a94deafee959528990a3b13d67ade924

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, min, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Math73
### Patch Diff Hash-SHA-256:

c5545e43d722c4f60ffc11658dd1680280b00b88131c563431a15b3aa925a2e7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Math73
### Patch Diff Hash-SHA-256:

995dd84dc29ffb8f285a707660cbf9ec280b1a2745237fcb54f35c7d7923730e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Math73
### Patch Diff Hash-SHA-256:

f86a178c5a15b111cc2446daadd478850b8d49a67d18b2ddaf496a1ad5234c27

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Math73
### Patch Diff Hash-SHA-256:

eb09487f0258de6b1783c3af9d25b1979ae8e99c21d8e19ecf18c9e0b81dbf95

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Math73
### Patch Diff Hash-SHA-256:

33afbb923c0b8a8fa63134dbe70db59f5ce29b42fc155f43fa171c446fbe733b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Math73
### Patch Diff Hash-SHA-256:

5cc2f5adaa0b3885b34b80ee1e8a4e56d97d420ac6616430ab3ecf79a62b9e38

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMax, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Math73
### Patch Diff Hash-SHA-256:

8569054ae8ca098e05c9630c975207da84852b9b74ac9c13ab3f443cfef39924

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMax, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Math73
### Patch Diff Hash-SHA-256:

0740c194790cb9381b2d28b0c6bf65181b6b55ee42d060062503b77d353a2d27

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMax, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Math73
### Patch Diff Hash-SHA-256:

9ead2beaf500c98ca7825f8dd20caa27428606f4f7ca2aa810072b17acbb98e7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMax, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Math73
### Patch Diff Hash-SHA-256:

e1d590ee56008e32fe30bca1eea5652edc9f90625f2b647704f3fbec80984901

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMax, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Math73
### Patch Diff Hash-SHA-256:

b64503bae649b60cfc6caf711801505fedea88f510be4b551022065f733f9ac3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Math73
### Patch Diff Hash-SHA-256:

bac9620ffa416176927f796993c6240c5ef08a3c7009bc236f085820702d7eaa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMax, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Math73
### Patch Diff Hash-SHA-256:

d6b0d5a896bdc23e8fecc701abca3c4b0ece6ec0e7ebc2458680f856a59579ba

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMax, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Math73
### Patch Diff Hash-SHA-256:

ee3e4f755cc362adb01607977671acd4bf71f9d6249cd4f78b7935c83b4cc14c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Math73
### Patch Diff Hash-SHA-256:

61304c3ef7ae9c9c53630479fb6d9e80690ba62dabe1c96e66c1c09b5890ff2f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMax, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Math73
### Patch Diff Hash-SHA-256:

c1b1872c0d7f83638021053440ce1b55a6e113dac8a78e4d5501f8bb31178f9e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMax, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Math73
### Patch Diff Hash-SHA-256:

46a5d6176511172e79707fc49959531e5336f9da88ce1b368f87008d7f5f9cd4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Math73
### Patch Diff Hash-SHA-256:

f3f8c94ed48cf01c8903bbe5dfa3ca2c0c2fe6ae6de0bdbca6fc3b0aa9a710ff

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMax, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Math73
### Patch Diff Hash-SHA-256:

037bb89014c058441b0b321089e26bf705ce63b69cfe3f751cd26a6efd6c84da

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMax, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Math73
### Patch Diff Hash-SHA-256:

cc8be6896b462e56d9b7e4b0746adec10c069af61fbd6c86dc1c648e28a2ba7b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Math73
### Patch Diff Hash-SHA-256:

8e4c51efa1a256b1f68ad84d189604bbe07a667421249504e2253fbe629035dc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, min, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Math73
### Patch Diff Hash-SHA-256:

76d4b4315769a3de6e3c5866b880d2eabaaaa9ed7f3878fd7e6ea0a17e896a33

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Math73
### Patch Diff Hash-SHA-256:

a9a7f093d7ea7112dae35a2e8f7756fad872c3919fc09f6e9240ff1cb3ee49dc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, initial, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Math73
### Patch Diff Hash-SHA-256:

3c628754fbd8ba27392911acfaaa5b0aff257c80364df6b33a670e709533d6ad

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Math73
### Patch Diff Hash-SHA-256:

41c715aff1042383a2efddc5c35eb4416299f52f8d141f7c169bec1b6325e690

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMin, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Math73
### Patch Diff Hash-SHA-256:

54f45298793eeb6d26f5a119f1dabe7a90684163da1d6b4eaecff120cbad4f60

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Math73
### Patch Diff Hash-SHA-256:

ae4946876de65b8edd94b3edbc32b798a09aeb282379a38e79d1e1193f41db46

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Math73
### Patch Diff Hash-SHA-256:

924b9f9ce3e5e0f12bc1eda3e387398f76264e5d0cefa99186f140e5cc865563

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Math73
### Patch Diff Hash-SHA-256:

c76e288ac33879080911e34f81521c59b9ced4e82daa120cfe5fbb820709a5c4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Math73
### Patch Diff Hash-SHA-256:

df102296625b05d8f2a90910e21cf935582e296da09e870ecf5c1595d2f096b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMax, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Math73
### Patch Diff Hash-SHA-256:

f49cca0a11ef6ec162afd14e0b11a76a17e94696d7b84243e9f8ef3c3e9fd495

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Math73
### Patch Diff Hash-SHA-256:

eae20bc4c49d0a702132ff51b29f75956e8d04b0d968a48dc938525f07f41da6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Math73
### Patch Diff Hash-SHA-256:

bb4526a9fe0ef70000ac19b56c0e9df945b91f2b7dbc40bb5dd9201ff9639c32

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMax, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Math73
### Patch Diff Hash-SHA-256:

c1044369789a76ab560a1e912a049b5157837dc9388d847c6332578856928986

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMax, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Math73
### Patch Diff Hash-SHA-256:

d3c50a305e44ba6812f451dc8e5fc55f855b69bfe5ee44c973f96a3007a7cedd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, initial, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Math73
### Patch Diff Hash-SHA-256:

fe7f1184a74a8f99aac668cbf01a2a21e62e5442948cce197a31c4c8ad423ccb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMax, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Math73
### Patch Diff Hash-SHA-256:

be7bc769f3592e4fea347ff72080fdc9cf537c0f4b77a0c4649f1b66edc15ed0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Math73
### Patch Diff Hash-SHA-256:

73f742e31937b9df69429050c54750702ce50cf184d55097b5827a88a4b1aecf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Math73
### Patch Diff Hash-SHA-256:

933c7cacff6e6cbdc492436af5efe42d049b11b5eda9f830676c8dc343693ec3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Math73
### Patch Diff Hash-SHA-256:

6512a972c404ee557133e095502f7fe0572c1d3d813cafab6cf9f27d92b29709

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Math73
### Patch Diff Hash-SHA-256:

26d4333ccf07849c7e191b740b08ea852b7c0634c86662e0a7555ea596dc0356

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Math73
### Patch Diff Hash-SHA-256:

b5208bf44988cda4510da0f00ac523fd94d8862e5e89f9ded796c7d89660f12d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Math73
### Patch Diff Hash-SHA-256:

4403b3eac2ca591c1246f85c39372ddbd9058199e2ebe4c60bbe5bbfd5a5cac4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Math73
### Patch Diff Hash-SHA-256:

918940768d7c9d55b56598197e6ee3491974f3b1ad5bda86494fe691190bb912

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Math73
### Patch Diff Hash-SHA-256:

80d05a74122bdbf672a65c35fd56659087f9037c66f98581461699164e8059c9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Math73
### Patch Diff Hash-SHA-256:

cad0528285b44870f517b9fdaa1c75bf9a28d5f0498b9701c9e85a92a8d7d7b1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Math73
### Patch Diff Hash-SHA-256:

abf7d780009996d3b38b965d59e4ab4154ff4ffb4ecfdc8d3898761ef3c4711e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Math73
### Patch Diff Hash-SHA-256:

d4b64c2c4ce8063a353cfc64ad66c77d7e59aea56a0379779ac19e9662028b10

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, result, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Math73
### Patch Diff Hash-SHA-256:

3b06572a399d87cf626ea756d437e3f802dea3d8b15ae4848517e5f3b59e4271

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Math73
### Patch Diff Hash-SHA-256:

31d4b61890dc999541f3935a06e8704010e2a5258befdea66d99700f8d22bbe2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Math73
### Patch Diff Hash-SHA-256:

626e8441f540196c60910ce76d10f24ecdf569c4692e70060b0b884d7101a3a6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Math73
### Patch Diff Hash-SHA-256:

943dc0a6e616052b5e8fbd3a4660455b9c2bf7bcc0cb9d6a052ac88ffe10505e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Math73
### Patch Diff Hash-SHA-256:

c1cc7ac8ee39ac67de6f58e0403750687bf16bb6740c9b14afa4abf892b0dd9c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Math73
### Patch Diff Hash-SHA-256:

a6a859099b40cc732000815fbdef1a340ab6dd028d5023cd45aa695281995ce5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Math73
### Patch Diff Hash-SHA-256:

2f5b4d18f68a404d13e89cedca606d657eec6f6081a7591084bd9f4d1bc6a20d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Math73
### Patch Diff Hash-SHA-256:

330f16c9a30aea0fd0479ded2b60c0543363a9786140c9bac64d8358e24c7158

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Math73
### Patch Diff Hash-SHA-256:

b7c857d59c129149c5675b5e35edaa78b6a694c5e5d4b6f5e37ad9225882532b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Math73
### Patch Diff Hash-SHA-256:

c3996cf3ddcdcdacdd4a3beea90afa95a93f101715d75dffdfdc66f1adbcfc8c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, max, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Math73
### Patch Diff Hash-SHA-256:

74f42c67f529ae6bd638872172234b06826854bf40d945966c9ef23f9228d5be

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Math73
### Patch Diff Hash-SHA-256:

4658429b4b0facd68068eb8a3290d394a86d72c9104ae8e4a61fa408ff522be6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Math73
### Patch Diff Hash-SHA-256:

d7887092198e71468d01fb8522ccca6b3e6014491c6cb89483c1b470994e3666

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Math73
### Patch Diff Hash-SHA-256:

b1bab4f54f879083a7671d89be3299a494963fa775bec070faa6bdbb698bb065

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Math73
### Patch Diff Hash-SHA-256:

9a0710b1b0cb0d7f06499112357d77ee04121ad25f43ec669230209547d529a2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Math73
### Patch Diff Hash-SHA-256:

b93c7d20c6dc38868c7252d08897661c80ad770dffe9cc2ccd3bcfc17d96b54f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Math73
### Patch Diff Hash-SHA-256:

c3161d4b4d9fad67c00fb7274f61b937ea80bec20a6b8e4a035166220b60804a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Math73
### Patch Diff Hash-SHA-256:

fbafc7975fe13a052a4b2c3f90ae36162a5a368bd41db3283aaf18e64d2958ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Math73
### Patch Diff Hash-SHA-256:

4d34bf53427117624de477c14d66586d726c8f6ec0a421f47a6a405bd97f6975

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Math73
### Patch Diff Hash-SHA-256:

1c24872576303d364bcaf2df76bd5dbe796c71427163eee44299277c22a5a528

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, min, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Math73
### Patch Diff Hash-SHA-256:

a2fef6cb90c7addf760083904cf138eac3303b46b4a20772ab42e0b2c7df9aca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Math73
### Patch Diff Hash-SHA-256:

4c55f5700b377f10ba2b758e4b1db60e515ed92d1cdbf95e1f7368877d7402bd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Math73
### Patch Diff Hash-SHA-256:

fa4f1f04d1898628338a2665f83f1ec25e3c70bf5b737f4d5334a04ab4f6e3d5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Math73
### Patch Diff Hash-SHA-256:

92af64ab98bf5df25c01ad71dd505947c0ae6e29b4b63c49804d979a8fcfe50f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Math73
### Patch Diff Hash-SHA-256:

b254ef113f8ba3a8d0f0ff80ed0203e7e350d5bb57668d55a7e7747c2ad30863

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Math73
### Patch Diff Hash-SHA-256:

a155c15b09d2f5806b4385a7c9e36b3d04c02dae3a53662bb4274edc134243b6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Math73
### Patch Diff Hash-SHA-256:

3fb76cf79552c0750c0d1fb644026bb700052a403b7fd19deb1b9de8ffd568f8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Math73
### Patch Diff Hash-SHA-256:

d6bd3d6d9f630716d4eebb9d216f7940536ba3fcea6bc6e7ecb5798c991e6353

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Math73
### Patch Diff Hash-SHA-256:

2cbc8e50e98e527a4a2bcfe17409e5c15902bdafc20181337115e78bf1495778

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Math73
### Patch Diff Hash-SHA-256:

9545cc14d22026de8c73692d93047bf69807f728f2ac1d35446a544686640692

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, initial, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Math73
### Patch Diff Hash-SHA-256:

0dc12580d0d70854f6c5ce59ac8a7a81e5fe2317cfa5fbd2c0143fe3b5bf402c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Math73
### Patch Diff Hash-SHA-256:

d629d3277fa69a59599063d4c883355cc198da06a1b72254b8af61f36aeab237

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Math73
### Patch Diff Hash-SHA-256:

e6b53791c2fff61a717809335b4dbf8c183a74bdcb7eb6d99a7c4d390257bbce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Math73
### Patch Diff Hash-SHA-256:

f9c4463843a8da1b08b3f6502a466f62987ae3431197f0d9dc615c3a00d95a1f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Math73
### Patch Diff Hash-SHA-256:

bc21d5857f75ab8c758c45839c7951d73ce7a60bf31b7ea8884f517cdfb99e5f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Math73
### Patch Diff Hash-SHA-256:

900f51aeddad728b2498dc51086e3214b985ab2bda07b81b36458b6640bb47bb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Math73
### Patch Diff Hash-SHA-256:

a1809b60ac02adc45fb08f3830be6b0ba4a86e7641efe22196f7cdd97f79a783

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Math73
### Patch Diff Hash-SHA-256:

dce9b8b9c3b1b30ded20c512d7322b092de89296ae96bc4976e975c774867806

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Math73
### Patch Diff Hash-SHA-256:

367f4ab33bdda587e3df8916fb2ed496de39374e934f0c81b149c7e15077230e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Math73
### Patch Diff Hash-SHA-256:

7f43e9675a075512e24b2cae40f68d995c9742d541dfdf7b9e45d8be2f0d0247

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, absoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Math73
### Patch Diff Hash-SHA-256:

4a3a39094ab3dc691cdd84985734b1f67e1791954a36a1ceb4777dfd406739cb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Math73
### Patch Diff Hash-SHA-256:

db759b44f3fab23825dddeba636cbd36583717c08a88843b814fec8597b0416a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Math73
### Patch Diff Hash-SHA-256:

e47ca494a55e7bc3e05159ab6cb143b3e1d4d9f40a8c66477e914f5bb5615f30

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Math73
### Patch Diff Hash-SHA-256:

891e7cfa317ed1b6e00210a8d4adb80268e14dd074adbc92a953ce19b48c6a23

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Math73
### Patch Diff Hash-SHA-256:

004a8529c27d91a841bb20142ca713b94aa0fa5099c04087f63ecfa1b700ac1b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Math73
### Patch Diff Hash-SHA-256:

fe862e0ea9f85f7c00576b6006ba2c1b9b087e5b4289f92c1f5d18680b8d4620

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 455 of bug id Math73
### Patch Diff Hash-SHA-256:

c75abd034baecb855f87155721b242e69b0839197023683e740508a330972d57

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 456 of bug id Math73
### Patch Diff Hash-SHA-256:

e5f66c06a57814ec319f898ba76b99911614d9336d3645fc2735d8da9228d7b2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 457 of bug id Math73
### Patch Diff Hash-SHA-256:

9b9fca9f3851fd81782e0c9dc49b6ea08844cec1fe1fe11c67b4b977a545389d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 458 of bug id Math73
### Patch Diff Hash-SHA-256:

4584e5bd9feecfe388efec543470997f63ee4d9bfc1949d9cb80033cd9bc8774

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, functionValueAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 459 of bug id Math73
### Patch Diff Hash-SHA-256:

1a108e9ec0c7875429360c05c173e4998e7b761d98b7d608db643ca7231e4ca8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 460 of bug id Math73
### Patch Diff Hash-SHA-256:

ef08eb66270cb528a44f8aa6fc30d89d7f6d317073de7543dac3f05b1fe56db6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 461 of bug id Math73
### Patch Diff Hash-SHA-256:

49d2973857ef55fc0b0a4a2dd23850abc0d82c5ff4bdde84aa20e50f4af028b7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 462 of bug id Math73
### Patch Diff Hash-SHA-256:

1de798200b5e3b1676716ebc54b747482e25038dc3998595c6918eafe8b01cfd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 463 of bug id Math73
### Patch Diff Hash-SHA-256:

c5ac36224bda1bec2751999800c2aa8d47874b60c61b33e2437126ae8b16668e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 464 of bug id Math73
### Patch Diff Hash-SHA-256:

28226c1dd2d25c136ca84f80cb0a96c79433af3337dd3a7010fc7d8ce4804750

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 465 of bug id Math73
### Patch Diff Hash-SHA-256:

899d4f9f80d9e4a322c237d21bfc98107285b070d9affaad05dbd37f5ca43033

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 466 of bug id Math73
### Patch Diff Hash-SHA-256:

5c33abc1807b1e9dfeeca2c4d03a5b131678334b81e38ee1e0061eaf4877b47c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 467 of bug id Math73
### Patch Diff Hash-SHA-256:

6ef3b998bf383f35fed233127c89d616cca6193b25e51426343dc43ca0acc2a5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 468 of bug id Math73
### Patch Diff Hash-SHA-256:

e251db5c45a50d874e53ab04ea899f03e795194765d95d816c2d8ae4a716a2d5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, relativeAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 469 of bug id Math73
### Patch Diff Hash-SHA-256:

19bcde9782c29dcef1ce95dfb69b0e662651795f74ef7b39a3acabd4ae1b5191

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 470 of bug id Math73
### Patch Diff Hash-SHA-256:

7a0bfdaed25ba843ebb5c45a015dca57d3f451fb5b26462dc299d5ed5d2f7de7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 471 of bug id Math73
### Patch Diff Hash-SHA-256:

9431d087dde8e2f4153bd86b0f1fc9e647cb512606315f58bf5b0f5df9500cac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 472 of bug id Math73
### Patch Diff Hash-SHA-256:

c760f16a1b493e977131d6b2661b3b857565c8c1797485b25c3b2cbe5c849663

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 473 of bug id Math73
### Patch Diff Hash-SHA-256:

0b490934c632a5962f1b2eaece1b2dde1e62b344eeb9369b0466c47e9b180776

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 474 of bug id Math73
### Patch Diff Hash-SHA-256:

4ba8d05c9746884fd8a29eba8140df4839aae63c973fdf0f2937518e5cfe394c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 475 of bug id Math73
### Patch Diff Hash-SHA-256:

08573b9698f0ad21979605af5bfcd9a8ddb8f6c864369f7b440fc4c60b96094b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 476 of bug id Math73
### Patch Diff Hash-SHA-256:

c61132738c706bde8561f7d5c9c7654ed002d2f89c402d3efadb914cfb67689b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 477 of bug id Math73
### Patch Diff Hash-SHA-256:

9e3b3f60ecd42644cf8ecdbdb19ad76a7c9c71a574bd3c1da472dd23b29c23c1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 478 of bug id Math73
### Patch Diff Hash-SHA-256:

5f781416d3b0d1f2cbd59eef4717119b7d1f54d5742f2fd788502bf4a9f11c9c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, yMin, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 479 of bug id Math73
### Patch Diff Hash-SHA-256:

f8d98c170a8b8197bb47c0c163c9e15edd5d5dc231950288637686235cdb2848

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 480 of bug id Math73
### Patch Diff Hash-SHA-256:

916a5f36630e962f744f6226d20e1971e7b0cc592266851413595b998aa0829a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 481 of bug id Math73
### Patch Diff Hash-SHA-256:

978c14711a8999797d60d5dc9b11b4e4a795e11ad2b1f50b46419a604cab25c7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 482 of bug id Math73
### Patch Diff Hash-SHA-256:

c71c0318b4e4a385a0f06515edfd84bd3e25f310a427e65358d700b9979b15b4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 483 of bug id Math73
### Patch Diff Hash-SHA-256:

3cc1a84886a7de900b663561260900ad3477a8a53eff8a69dabe7826033d7599

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 484 of bug id Math73
### Patch Diff Hash-SHA-256:

bc26483a175bbac2be6512127b3c10ef78493bdf4751ff7d649261786150d5ee

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 485 of bug id Math73
### Patch Diff Hash-SHA-256:

4a84669b22ec1a9b29e62fabfe8323e3b89ce9bcb3040ac4ae0e3a850e596c7a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 486 of bug id Math73
### Patch Diff Hash-SHA-256:

8edbb737a6455414c0cbdbae0df18f91fc6cad085da763bb20fa678f1498725a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 487 of bug id Math73
### Patch Diff Hash-SHA-256:

0369a9d2a8dd9aa9ea34d3b461adc704f301c52a90003def8328d6b2304253d9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 488 of bug id Math73
### Patch Diff Hash-SHA-256:

26334269a5f089deded65734c5ea58252430a32b7bec47cb52dab68c11ff7402

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, yMax, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 489 of bug id Math73
### Patch Diff Hash-SHA-256:

f759aa1d6c3af8e7fbd08484a98082cd25bd9e017269cfe6edcb0495c2cc3b73

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 490 of bug id Math73
### Patch Diff Hash-SHA-256:

c8e2607b01ed502dc0fbf1d853a6839046d3e24fa638d19a92721dcc7f48987b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, max, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 491 of bug id Math73
### Patch Diff Hash-SHA-256:

ddb9a1020e3c8b438900cb026db96a5c9d8338ebfa796ea54809c2ac414a4fa2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 492 of bug id Math73
### Patch Diff Hash-SHA-256:

456c102123a3c10fa767260fd7974b9041e9bedc43b4ad721d4b26c8732e5823

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 493 of bug id Math73
### Patch Diff Hash-SHA-256:

e7a8475269a9169cbe5cdc296d4ac71e0b431bb6b1a7c31a494e440a94b4e436

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, absoluteAccuracy, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 494 of bug id Math73
### Patch Diff Hash-SHA-256:

6b0f5618a1ff1597b1a542e5be97da6e743716358d444a2d1847b76cae73270d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, functionValueAccuracy, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 495 of bug id Math73
### Patch Diff Hash-SHA-256:

1dab9453ce6917cdee1a5ddae7bb00da1f7ed7976b031bebfeee37056edea91f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, relativeAccuracy, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 496 of bug id Math73
### Patch Diff Hash-SHA-256:

2d43db75ce2aaf34dd9bf844e0887cdb01b218efd2aeddab080ff4ddf6064869

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMin, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 497 of bug id Math73
### Patch Diff Hash-SHA-256:

631c6ecf17df6dfe00b2b3d5be610a4838a97ff789d3d2dfd7fefea9107b7f62

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, yMax, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 498 of bug id Math73
### Patch Diff Hash-SHA-256:

d07327d78fd58c9d9a48a74a7c1b6625bd09e86f0d167e928699218c75057384

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, defaultAbsoluteAccuracy, defaultAbsoluteAccuracy, result);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 499 of bug id Math73
### Patch Diff Hash-SHA-256:

9ab3cab5a8eaf815981bb34524fffc865310059f57e44810e90f015055db0045

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 500 of bug id Math73
### Patch Diff Hash-SHA-256:

37c15c4127671aa9269c118bea1f8d1a1f3c63b6bc2aea7ff898ffc4bedc62b7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, min, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 501 of bug id Math73
### Patch Diff Hash-SHA-256:

6a5c1aa997f1eb624623697a3556e8f18f6b15cf5279eb63885163ee399f6aee

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, max, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 502 of bug id Math73
### Patch Diff Hash-SHA-256:

731153d84626ef02ac5809a724e23e5c2bc0e9cc350ce25f2dd79c59e46831b7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 503 of bug id Math73
### Patch Diff Hash-SHA-256:

fa6ec20781a4d3103336d74ea10a1bf68d0794d4d35fb561541dcf8c533e38fd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 504 of bug id Math73
### Patch Diff Hash-SHA-256:

a771be47ed1ee433391bbd36241d6f9b6c0a26f66f9d809880ed18488d1f1c2d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 505 of bug id Math73
### Patch Diff Hash-SHA-256:

24e19c8afda2986830aaa91081287729e910405213bc21a6a5984d42d5023f61

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 506 of bug id Math73
### Patch Diff Hash-SHA-256:

c92a04f3d765f0aa52d1995597bc4fffea19ae9b04f4f175fbfa4ab4087a918e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 507 of bug id Math73
### Patch Diff Hash-SHA-256:

fdb8e3492229f03eb2c4bc50c7ad442b83b9a6519c045401acd7901f12c5ad2b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMin, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 508 of bug id Math73
### Patch Diff Hash-SHA-256:

697afa8b8eb4a0e714bda97674a7b30cb4091a265d0b13778e0910aabbc44b70

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMax, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 509 of bug id Math73
### Patch Diff Hash-SHA-256:

7f6441efa38cf3a2663df2c57d912d89f1d403d07e777e60a086e37beecd7e1b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 510 of bug id Math73
### Patch Diff Hash-SHA-256:

b96fbbd31754b79ee45c6d6fe8a5e5816ed412e4d4614ab7792efacd399bc931

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 511 of bug id Math73
### Patch Diff Hash-SHA-256:

a43dedc6de5ca357698bb03ffd46d2c01f80f9b9bb8540a1ebdc3ff53cc6ff1b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, min, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 512 of bug id Math73
### Patch Diff Hash-SHA-256:

f7f041c72bef51e7a7e859f7c0213fe1f88e53661d9826e85a4b7e6e8fdfd0ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 513 of bug id Math73
### Patch Diff Hash-SHA-256:

f87577b55d898a78bf6f1077be7d52a80c66322956c0372412345b0fbebde775

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 514 of bug id Math73
### Patch Diff Hash-SHA-256:

aa159a34817a86e7da8c22153658692b61ed554589e90b39b599ec66af998e3c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 515 of bug id Math73
### Patch Diff Hash-SHA-256:

7c7f2543dcb6c0dfaba7e42fa46289e9a70dc335d692789fcb06f894896d12d8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMin, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 516 of bug id Math73
### Patch Diff Hash-SHA-256:

72d99af4650e73c31ce6cb6f89fe961a3c291559bcb3929b26807303d258e059

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMax, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 517 of bug id Math73
### Patch Diff Hash-SHA-256:

7f2c3f9116f254edfa71816d7e5cd2e06b078af2881911daded6bb00e6c8e094

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, min);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 518 of bug id Math73
### Patch Diff Hash-SHA-256:

84a9a4b31736a7f133eca269d6214164439bf621cf7965a080cbd0bd4acfb2ff

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 519 of bug id Math73
### Patch Diff Hash-SHA-256:

ca631c8dff63c3e9d471a6d81f324b3474203c670456e448966b10f479d4a095

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 520 of bug id Math73
### Patch Diff Hash-SHA-256:

b49640527643b175da07a76c4f5d32fce897a94c2c9e4b4fb6a0af536951df38

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, initial, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 521 of bug id Math73
### Patch Diff Hash-SHA-256:

b068c1e04f9704de38b8c9c5436bc1739781cd84df656730ee2e0a5e77e8794c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 522 of bug id Math73
### Patch Diff Hash-SHA-256:

a8fef175e8587aca9b491c367d3cbeb4791eb37797a7a181ca0a1daddea43aea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 523 of bug id Math73
### Patch Diff Hash-SHA-256:

397d0ba1bc4405f2e3a3a4c22336df67de675298b54ec6fd8a8779e9dd88ab57

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 524 of bug id Math73
### Patch Diff Hash-SHA-256:

6fe9265edbbb35dd7ebdc6bfd2d4b59cd420cc63a2c82f2802a6f89303dd2d3f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMin, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 525 of bug id Math73
### Patch Diff Hash-SHA-256:

7a721856bf2285e7867df262255eac3c6e69614537b2a0fb6d29f7df468e65df

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMax, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 526 of bug id Math73
### Patch Diff Hash-SHA-256:

51ba4a110525e5f7a0e415f046fd43e49bcd31347e0d3589d55529e48a659bc0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 527 of bug id Math73
### Patch Diff Hash-SHA-256:

20007f09ad973bca8543d0986d0079c851ec8242e4d71463f5046ecefd25e60b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 528 of bug id Math73
### Patch Diff Hash-SHA-256:

7714e673548718127c1b3c61d636c496c2afb24330e2b21022e95c24075b6a29

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 529 of bug id Math73
### Patch Diff Hash-SHA-256:

7a5edccdd90591439b37a4d96db93da18464659cb676f5ab38b4d19d7d992b4e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 530 of bug id Math73
### Patch Diff Hash-SHA-256:

918304f1d3993c13d1592ec83b58adc43ff0fcfd2280abef81629d2c3b9979b1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 531 of bug id Math73
### Patch Diff Hash-SHA-256:

db245b0f0d8ef4d42f835c36536e2a3fbae7ca9311f57668a1bc6c0a5ceab1c8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 532 of bug id Math73
### Patch Diff Hash-SHA-256:

c47faba394f1952f4f96888b068319b26921c80a0db10a3c2960c26d82d151c9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 533 of bug id Math73
### Patch Diff Hash-SHA-256:

2c864c7feb8277a25cf836cc9f7e1bcb6e5a7694f696f0b843bcfdd966f5340a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, functionValueAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 534 of bug id Math73
### Patch Diff Hash-SHA-256:

1ad1e97501dca0512172002c60a833036fb53d040767aee4d69579a411aa95d6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 535 of bug id Math73
### Patch Diff Hash-SHA-256:

08fb948d0824d04f94eb09a7b45adae98a5633b3170ed4b58421f564c5f5a742

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 536 of bug id Math73
### Patch Diff Hash-SHA-256:

ebc12a5f5412f6c322c032769ab5375fe2321fbbdb3ce89d35d994e24cd51ccb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, relativeAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 537 of bug id Math73
### Patch Diff Hash-SHA-256:

5e55e669584315c7418dac67d6269d021d5deb095667d7636fc1153bd3d4e0e4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 538 of bug id Math73
### Patch Diff Hash-SHA-256:

46a4b6044c0b0342980ae3d1c384d38b9b538a9cc1c2b213b0bf084b11b9f368

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 539 of bug id Math73
### Patch Diff Hash-SHA-256:

1e95b574859b7a1792ca5b1f55b646f69ac4cb727bb8a18e8b95ad309bcf7663

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 540 of bug id Math73
### Patch Diff Hash-SHA-256:

bf61b01412b54924e53a81a010df4306b9670316a99385e73e58ca92c724bc91

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 541 of bug id Math73
### Patch Diff Hash-SHA-256:

ecb538d8cc90e9af56b8e7d710b458c4bd41f3d2643eae940074b07b7b42fa2d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMin, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 542 of bug id Math73
### Patch Diff Hash-SHA-256:

32d905e53948dbcf4e7e2dc6f6dee031b82c98c420d8cfc86f9339953f01d76a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, yMin);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 543 of bug id Math73
### Patch Diff Hash-SHA-256:

9fb21df7ff99bbf93d185107fd929bf7b977b3cce15fbe881044edf7d755b5af

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 544 of bug id Math73
### Patch Diff Hash-SHA-256:

be4e142e98add8597eb30ac56a2308157ec23b9b20bdeac681155bfe633c55be

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 545 of bug id Math73
### Patch Diff Hash-SHA-256:

32bf703a8e95bf87c33a1470927816809a768b5aff0740e0ccb294ce3524b740

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 546 of bug id Math73
### Patch Diff Hash-SHA-256:

4e210241ec22edc7c403079883a205a30c28dbadc8d8ab020d9fcc85ad6f92ee

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 547 of bug id Math73
### Patch Diff Hash-SHA-256:

6bc20184f7a2e4700513dc7eb3698a193e3fd3c94ce204287d605b6681f8a63b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMin, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 548 of bug id Math73
### Patch Diff Hash-SHA-256:

2615afd044f7e8d6b4ce4a685a60c5b4863728b01d896602623380dd14726df8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, yMax, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 549 of bug id Math73
### Patch Diff Hash-SHA-256:

8fd3330341cb3575377ae267bffa209905aae545eab9b7c6dcced408ba36b7ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 550 of bug id Math73
### Patch Diff Hash-SHA-256:

b8d9d947a2532be9430328b9c0dd9d62a5ed7ae716a306fc33403ea9b290f0dc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, result, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 551 of bug id Math73
### Patch Diff Hash-SHA-256:

361e7a1f0b71b3bb16de31c4a67762636f76a950d875f2ed2cf7c39390b2f863

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, absoluteAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 552 of bug id Math73
### Patch Diff Hash-SHA-256:

69036197679daf7358288370321e6a983c90d17b3178238caee1c01658171c78

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, functionValueAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 553 of bug id Math73
### Patch Diff Hash-SHA-256:

6b2dcdbe10f6c8e2490265612b935ee4ec9ca5b758eb2a9f216b573421c8f7e7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, relativeAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 554 of bug id Math73
### Patch Diff Hash-SHA-256:

fe2ab248fac0ecbd826f829f2b512ff18be6c5880e55ce1bc2c3711072a3abea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, result, defaultAbsoluteAccuracy, defaultAbsoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---