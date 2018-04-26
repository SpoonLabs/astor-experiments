
# Patches of Math6 from Defects4J 
Total patches 2
## Patch 1 of bug id Math6
### Patch Diff Hash-SHA-256:

ebc2f457e06c5864ccbb621da69a7d4a183b6f058c5c3c622bebfe3a664a8cd7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optim/BaseOptimizer.java	
+++ /fixed/org/apache/commons/math3/optim/BaseOptimizer.java	
@@ -29,7 +29,7 @@
 	}
 
 	public int getIterations() {
-		return iterations.getCount();
+		return evaluations.getCount();
 	}
 
 	public org.apache.commons.math3.optim.ConvergenceChecker<PAIR> getConvergenceChecker() {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math6
### Patch Diff Hash-SHA-256:

3a62e9a3d40939dc9d15e321492f5faa1c35e732d7a3bd43b4d05fba260214d3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optim/BaseOptimizer.java	
+++ /fixed/org/apache/commons/math3/optim/BaseOptimizer.java	
@@ -29,7 +29,7 @@
 	}
 
 	public int getIterations() {
-		return iterations.getCount();
+		return evaluations.getMaximalCount();
 	}
 
 	public org.apache.commons.math3.optim.ConvergenceChecker<PAIR> getConvergenceChecker() {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---