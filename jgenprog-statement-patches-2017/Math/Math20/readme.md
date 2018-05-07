
# Patches of Math20 from Defects4J 
Total patches 5
## Patch 1 of bug id Math20
### Patch Diff Hash-SHA-256:

1aa02b21a75b80de3c374b55282d79b62aba3fd5d6b232f9cab9adda82ae1fe1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -586,7 +586,7 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
+						valueRange = 1.0;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 2 of bug id Math20
### Patch Diff Hash-SHA-256:

a9285df7dab28cabd461b4ecb352b545fe2be1c86cfe55ffade664837101afab

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -586,7 +586,7 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
+						isRepairMode = true;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 3 of bug id Math20
### Patch Diff Hash-SHA-256:

d66f763e14c6a4aa1dbcddbacc9e26d2e16ef497135e1ecc662f38377c22626d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -586,7 +586,6 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 4 of bug id Math20
### Patch Diff Hash-SHA-256:

b08a5a42691215b624be16ad66c131fd10ead83a9f56a35e5bd087e625b1af76

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				valueRange = 1.0;
 			}
 			return res;
 		}
```


---
## Patch 5 of bug id Math20
### Patch Diff Hash-SHA-256:

460078027c14af99b1207a95f99992bcba500931c5f54a54f1a41cffe5eb31fb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,10 +526,6 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
-				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
-			}
 			return res;
 		}
```


---