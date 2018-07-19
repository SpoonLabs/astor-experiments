
# Patches of Math70 from Defects4J 
Total patches 8
## Patch 1 of bug id Math70
### Patch Diff Hash-SHA-256:

4a055e5967b90b6f15f06c9ab75302d424717bf970dbaed957449bdb52637d20

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math70
### Patch Diff Hash-SHA-256:

27b89a905417e40e7c536ebf5a1dc9911bcb79be8a340ddb8320c2458ad7dfb3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, defaultAbsoluteAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math70
### Patch Diff Hash-SHA-256:

a5b149b483db095c89ede64280b258a9f98fd9eae4d3139a0548d06ca191456f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, functionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math70
### Patch Diff Hash-SHA-256:

c56e3c4326e0376d39429e7c2fe7b049e46b6adce4e0b6ae34838c773f914afd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, defaultFunctionValueAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math70
### Patch Diff Hash-SHA-256:

6bd961416b2e8f166ac8d128592dc3d78a67916b539423456196ef09fd07580b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, absoluteAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math70
### Patch Diff Hash-SHA-256:

0acecaf0c558ed77fb39a7c86048144fabc55c885dbbb9ecf78965c63d6d7336

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, relativeAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math70
### Patch Diff Hash-SHA-256:

ca557125a8f8c00409444c49ee9e62039e80455dc7d904e16eb3c7c14ff13b15

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, defaultRelativeAccuracy, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math70
### Patch Diff Hash-SHA-256:

84237e6dc0bcc9350b34f559a6d849890f1e3dc578190bc2c8fdc892cd90ba49

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---