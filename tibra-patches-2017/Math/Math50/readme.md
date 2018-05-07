
# Patches of Math50 from Defects4J 
Total patches 7
## Patch 1 of bug id Math50
### Patch Diff Hash-SHA-256:

5a0ab0ae89347985e62225e4616b3a8c512fdf98c24dab0376499b3170b8f366

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,10 +78,9 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+						if (x == x1)
 							f0 = computeObjectiveValue(x0);
-						}
+
 						break;
 					default :
 						throw new org.apache.commons.math.exception.MathInternalError();
```


---
## Patch 2 of bug id Math50
### Patch Diff Hash-SHA-256:

c6c3ed541f2a4491f9ceb32eb418ca87eb352ca38bea028a4d22c4bd8a683681

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							incrementEvaluationCount();
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 3 of bug id Math50
### Patch Diff Hash-SHA-256:

e86fb5c217e3fa3dcc912105426f727e3e5087fdf65b295c4f2b743573a432f7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = 0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 4 of bug id Math50
### Patch Diff Hash-SHA-256:

88787cdb3caa1e0cba475c273001e6b136069617f7b74123732ddf6e753de781

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f1 = ftol / fx;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 5 of bug id Math50
### Patch Diff Hash-SHA-256:

fa3641b1a23c28917175f38ba5cffd54ab04c678da47b74ef41b5a42b529c71d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							double ym = computeObjectiveValue(f0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 6 of bug id Math50
### Patch Diff Hash-SHA-256:

e93acea9fe2b2a49692f830ccbab73ee94eef396bf8c95b9799470955d2c2d40

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							double y1 = computeObjectiveValue(x1);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 7 of bug id Math50
### Patch Diff Hash-SHA-256:

0dbfc0f06d4613ab1a09548acfc57679ddeb9cd2f8c1a20328bfcaaae17dae1f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f1 = f1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---