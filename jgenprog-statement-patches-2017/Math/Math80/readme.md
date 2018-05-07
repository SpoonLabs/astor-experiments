
# Patches of Math80 from Defects4J 
Total patches 14
## Patch 1 of bug id Math80
### Patch Diff Hash-SHA-256:

f7fd691ed8a5f28b01abbbc4965cf6cc5b88550660bf69713a9ddedc18528b61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,14 +675,6 @@
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
## Patch 2 of bug id Math80
### Patch Diff Hash-SHA-256:

6d19107d8952a93b879f252c91aae4f926497135b1d70231ecdc2dcb78fa5cfa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		computeGershgorinCircles();
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 3 of bug id Math80
### Patch Diff Hash-SHA-256:

cc823888e33a6f4f47b668e50841bf47cad3399079fc0834b004d5c259611c54

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.util.Arrays.sort(realEigenvalues);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 4 of bug id Math80
### Patch Diff Hash-SHA-256:

c67dda0966d287f5ff411e53e1d7215e2e6260c4e2f42cbd1e7acf94854d99f4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					tType = -6;
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 5 of bug id Math80
### Patch Diff Hash-SHA-256:

ce2e7d8a91da07b69523c58b11716ae1cefdbd8507d0b37b301bb7a75670f1cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,6 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 6 of bug id Math80
### Patch Diff Hash-SHA-256:

f104c914d6933c19d6f0b522638711bf3be8abc18e6265d40c391c1591fc4291

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,6 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 7 of bug id Math80
### Patch Diff Hash-SHA-256:

5c222e09fd8e36abe5b45d5a029b2d3fbcdc14d1a6c2e06a15e4aad499845d16

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,14 +675,9 @@
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
## Patch 8 of bug id Math80
### Patch Diff Hash-SHA-256:

5dd480a64c61709ba3645717b9a4bbcbc0c43bd904c8138fd7a5e61981921abe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,18 +673,6 @@
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
## Patch 9 of bug id Math80
### Patch Diff Hash-SHA-256:

6809ec87e9dd886ba8f1a9a0bce1062b0bfd74689318abb80c2e1948f140e97f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -724,6 +724,7 @@
 			if ((range < absoluteTolerance) || (range < (relativeTolerance * (java.lang.Math.max(java.lang.Math.abs(left), java.lang.Math.abs(right)))))) {
 				break;
 			}
+			pingPong = 1 - (pingPong);
 			final double middle = 0.5 * (left + right);
 			if ((countEigenValues(middle, index, n)) >= n) {
 				right = middle;
```


---
## Patch 10 of bug id Math80
### Patch Diff Hash-SHA-256:

d7d8b14fb8b8ca2705464dd71ccf756f4d062840223942024b290dc6ff07749c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					tau = -(dMin);
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 11 of bug id Math80
### Patch Diff Hash-SHA-256:

6356e805517704d8a401608d47e9e1eabd39e69a5fea3d1f1d5d6b0f5c16b207

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -471,6 +471,7 @@
 
 	private void processGeneralBlock(final int n) throws org.apache.commons.math.linear.InvalidMatrixException {
 		double sumOffDiag = 0;
+		pingPong = 1 - (pingPong);
 		for (int i = 0; i < (n - 1); ++i) {
 			final int fourI = 4 * i;
 			final double ei = work[(fourI + 2)];
```


---
## Patch 12 of bug id Math80
### Patch Diff Hash-SHA-256:

13995790ea607ff3de352d96b101018bac7eba6bc6a82c9b32eb2fab35339ccc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -717,6 +717,7 @@
 			}
 		}
 		lower = java.lang.Math.max(lower, (left - ((100 * (org.apache.commons.math.util.MathUtils.EPSILON)) * (java.lang.Math.abs(left)))));
+		pingPong = 1 - (pingPong);
 		left = lower - margin;
 		right = upper + margin;
 		for (int i = 0; i < maxIter; ++i) {
```


---
## Patch 13 of bug id Math80
### Patch Diff Hash-SHA-256:

3f0797eb48f29a15106c1caad9eb3374822b80bcbd37ba46b2078f0bcfbbb8d6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					cachedV = org.apache.commons.math.linear.MatrixUtils.createRealMatrix(n, n);
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 14 of bug id Math80
### Patch Diff Hash-SHA-256:

3c3c3168fecdcdc8b4818c6c548429fef1ab8124609969870115edaa0a8f740a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					dMin1 = 0;
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---