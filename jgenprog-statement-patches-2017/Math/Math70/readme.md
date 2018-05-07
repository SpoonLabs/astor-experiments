
# Patches of Math70 from Defects4J 
Total patches 2
## Patch 1 of bug id Math70
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


---
## Patch 2 of bug id Math70
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


---