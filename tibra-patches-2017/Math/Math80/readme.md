
# Patches of Math80 from Defects4J 
Total patches 12
## Patch 1 of bug id Math80
### Patch Diff Hash-SHA-256:

ca075a3dd0cc4a56860cd1ca9ae9c4c672a1646fa62177994adb33998fef057c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -326,7 +326,7 @@
 			lowerSpectra = java.lang.Math.min(lowerSpectra, lower);
 			final double upper = dCurrent + radius;
 			work[(upperStart + i)] = upper;
-			upperSpectra = java.lang.Math.max(upperSpectra, upper);
+			pingPong = 1;
 		}
 		final double dCurrent = main[(m - 1)];
 		final double lower = dCurrent - eCurrent;
```


---
## Patch 2 of bug id Math80
### Patch Diff Hash-SHA-256:

d4a010450e22aa0b6542ea052f8bfcc5077eaa2bf797c3f46e1efb351554d022

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,14 +673,9 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
-				}
+			for (int i = 0; i < j; i += 4)
 				j -= 4;
-			}
+
 			return true;
 		}
 		return false;
```


---
## Patch 3 of bug id Math80
### Patch Diff Hash-SHA-256:

e90580f0ef88f594b84fd234f03e75de4a8477643e69de0039f0ed97755a154f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,6 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 4 of bug id Math80
### Patch Diff Hash-SHA-256:

a4e1e7fc3ee0dde157640b940cdf626cafd897fcdfb80e1506c9ac4f54623454

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					cachedVt = cachedVt;
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 5 of bug id Math80
### Patch Diff Hash-SHA-256:

c808c05d203f08d982bf7b2d962f56ff25828f127a87a34f7818b8ff0fc8a1e0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -477,7 +477,6 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 6 of bug id Math80
### Patch Diff Hash-SHA-256:

ca941d1a58291ddcf1fd2dab3e6405c7353deb5f7e0b674ddf19f392bb670003

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,14 +673,6 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
-				}
-				j -= 4;
-			}
 			return true;
 		}
 		return false;
```


---
## Patch 7 of bug id Math80
### Patch Diff Hash-SHA-256:

4175903a5d35d0047a72ce8a1546f6d6a71e025a9cfee2cd3de6411d62594dc4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					tau = java.lang.Math.max(tau, (tmp - ((100 * (org.apache.commons.math.util.MathUtils.EPSILON)) * (java.lang.Math.abs(tmp)))));
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 8 of bug id Math80
### Patch Diff Hash-SHA-256:

fdc2ef6f7b1f83e5bc2eb59e948f4dd7c8b52ce8219b7272228139a72c941473

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,10 +674,9 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
+				for (int q = step; j < step; ++j) {
+					work[pingPong] = (main[pingPong]) - (cachedD.getEntry(tType, j));
+					++(pingPong);
 				}
 				j -= 4;
 			}
```


---
## Patch 9 of bug id Math80
### Patch Diff Hash-SHA-256:

492fa1710244a6660839a231268e81eaca2055922f2d794c97332ce017a60fc3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,13 +673,8 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
-				}
-				j -= 4;
+			for (int i = 0; j < n; j++) {
+				realEigenvalues[j] = (work[j]) / (dMin);
 			}
 			return true;
 		}
```


---
## Patch 10 of bug id Math80
### Patch Diff Hash-SHA-256:

f059c4f030acc3a63e40e9f06d89618287459e3ff63b1228aa2334e8fcfa1a49

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					realEigenvalues[tType] = java.lang.Math.pow(imagEigenvalues[tType], dN2);
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 11 of bug id Math80
### Patch Diff Hash-SHA-256:

2d487a6cb536d950d76bd43746cfd1df5dbc826c8970cfda8316a946741a9588

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -671,18 +671,6 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
-				}
-				j -= 4;
-			}
-			return true;
-		}
 		return false;
 	}
```


---
## Patch 12 of bug id Math80
### Patch Diff Hash-SHA-256:

8b8ea490698c453ac69c34fddb9d03a87d8dbc4f783edd3c75447245ce66a73f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					imagEigenvalues = new double[n];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---