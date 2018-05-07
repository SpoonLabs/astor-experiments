
# Patches of Math50 from Defects4J 
Total patches 21
## Patch 1 of bug id Math50
### Patch Diff Hash-SHA-256:

0e36c4afa2725aed0c377f1c761e7c8ea90c7e2217956160050e9d120c811416

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,10 +77,9 @@
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

1839b7b93dca08afa17912996ef7e5ab743717da949e94518f6b4b8cdac4967f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1;
 						}
 						break;
 					default :
```


---
## Patch 3 of bug id Math50
### Patch Diff Hash-SHA-256:

235eff4d38de9ee26a6eb718fd54c4e09825e9f4279a2f2d627e9d6149da9f60

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f0 = computeObjectiveValue(x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 4 of bug id Math50
### Patch Diff Hash-SHA-256:

a21a14e9d89fb2611402a59b8fc982c1128e71e2bbc1068de284239e51e1f390

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f0 = f1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 5 of bug id Math50
### Patch Diff Hash-SHA-256:

a6dfb0319a393b5b7311e9ea361dd1f0303aef359c05243043a8f42d041befb2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							final double y = computeObjectiveValue(x);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 6 of bug id Math50
### Patch Diff Hash-SHA-256:

8242067c57ca7f370af44a57c6986c05abf6e571fd2687a2f9f56eece0c763fa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							inverted = !inverted;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 7 of bug id Math50
### Patch Diff Hash-SHA-256:

8d6f3c7f458c318ef6897634316750a9061fa0340b70ef585aef7335c2b74307

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f1 = fx;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 8 of bug id Math50
### Patch Diff Hash-SHA-256:

0aac1d53d21216b07193d88179bf1beb3a0fb85b110a2cd8e95f63efcc0202ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 9 of bug id Math50
### Patch Diff Hash-SHA-256:

4d153fbce4592fe8acb76b06e0e35990c377ee0b86f90383789d961f35aa43d8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							double y0 = computeObjectiveValue(x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 10 of bug id Math50
### Patch Diff Hash-SHA-256:

3c8b92a5a25e598b027e36be8e4bd25e99debf6005aca765a5085a574c1fe08f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							f0 = f1;
 						}
 						break;
 					default :
```


---
## Patch 11 of bug id Math50
### Patch Diff Hash-SHA-256:

5f59021bfdd27d7eea61558a7ccb77f66fdb0600f61d92690c2d2cec4442ceb3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							double y1 = computeObjectiveValue(x1);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 12 of bug id Math50
### Patch Diff Hash-SHA-256:

0f94c673d0e1599e0a0099b45d4ecbe4249658c95947cdd298786dc07c7061c0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							incrementEvaluationCount();
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 13 of bug id Math50
### Patch Diff Hash-SHA-256:

35644789c52bd3906348ecb13cdab05e9c71f955b3ca08863990ecb7e3b17dce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							f0 = computeObjectiveValue(x0);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 14 of bug id Math50
### Patch Diff Hash-SHA-256:

7658e2e34584088babde33cd83d8599ca4fdf14a4864bad86fe0d72f0f01fc67

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							final double y = computeObjectiveValue(x);
 						}
 						break;
 					default :
```


---
## Patch 15 of bug id Math50
### Patch Diff Hash-SHA-256:

a70cbcd9957596299d998f713b8d6b2db702d493375b5ac4bdcd234de33fccaf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							final double y = computeObjectiveValue(x);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 16 of bug id Math50
### Patch Diff Hash-SHA-256:

e2f2bbff5878acadd7c7201706a601fea11074c4d9a4b5dfda73f9625f8b4fdb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							incrementEvaluationCount();
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 17 of bug id Math50
### Patch Diff Hash-SHA-256:

b923587be4af317c2532f1d4774b7f8d9b034194083b0e9d9d6a515b58d54470

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							double y1 = computeObjectiveValue(x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 18 of bug id Math50
### Patch Diff Hash-SHA-256:

38ac2a0749b9d6cd1484ce513e991ba6b940e395b3725ca67fe6433d53321cb1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							double y1 = computeObjectiveValue(x1);
 						}
 						break;
 					default :
```


---
## Patch 19 of bug id Math50
### Patch Diff Hash-SHA-256:

ebaf53bd64407317e617b5fb61da46198d2c6b33cef68ada48347b709f490939

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							incrementEvaluationCount();
 						}
 						break;
 					default :
```


---
## Patch 20 of bug id Math50
### Patch Diff Hash-SHA-256:

33e35d8baf2e608aea49fe586558e4e0db2973f304f20f6db64832ffd3973c64

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(x0);
 						}
 						break;
 					default :
```


---
## Patch 21 of bug id Math50
### Patch Diff Hash-SHA-256:

c48236c4a7214d92a041b453f97b7d3ebc85c9641fb8a941c538f625fe2e31dc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							double y0 = computeObjectiveValue(x0);
 						}
 						break;
 					default :
```


---