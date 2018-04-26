
# Patches of Math80 from Defects4J 
Total patches 585
## Patch 1 of bug id Math80
### Patch Diff Hash-SHA-256:

3e68e348bb90766d3dab6dcec255efd73847764976cc526fa0dd845e20f65d73

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(n + 2)])) < (work[(n - 3)])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(n - 3)])) < (work[(n + 2)])); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math80
### Patch Diff Hash-SHA-256:

7670102a8a8c6ee87d1bd0a61b55431eccef5a0deed5a1eac3c1ab7c23aa01a0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j == ((pingPong) - 2); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math80
### Patch Diff Hash-SHA-256:

1f564097121a173d9d182392191b3c2195eb1355d22506ca7d0c9686724c8faf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN) != 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math80
### Patch Diff Hash-SHA-256:

6debedad8c0b721d7323cd2847c09801d3d6441aefd6c356e2e387b2624e4db2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * j) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) && ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math80
### Patch Diff Hash-SHA-256:

7267fe146b5b76316a1f5d2f56ef4eb54ea89df35f43e184e174c545372eddeb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) > 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math80
### Patch Diff Hash-SHA-256:

6f46a0f00b55cefb2011a32bd82a94751d98f3566750de4cf6af26379cbabb2a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j < step; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math80
### Patch Diff Hash-SHA-256:

3d5613701ebd33bc7172317034116cb2934002a46fc70ab66bc4df47ac9c551b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n < n; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math80
### Patch Diff Hash-SHA-256:

d93c44c887a99e24ab28ca63678dbbf5f435164437f08fd4fb285010ec44da9f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) < (tType); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math80
### Patch Diff Hash-SHA-256:

ba140ddd17ee695e952b2a6ac2554f6e0db69eda157a8fd752da6d12121da0a7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n < (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math80
### Patch Diff Hash-SHA-256:

5eae4bba25bd1a9d5beff70eab1635259a069a99dd4fe4e7ae2cd2b000657ec0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work[(step + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (g)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math80
### Patch Diff Hash-SHA-256:

55d6e1049773efef620336642cd92dc322b32aa7048c6246024142cca09aeba0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin1) > 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math80
### Patch Diff Hash-SHA-256:

75ca9a4368607977b5773fdbd99cb3dcaca72915bb66ef90edd77b13da6ced24

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (realEigenvalues[0]) > 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math80
### Patch Diff Hash-SHA-256:

725aa5097039022e8e5470cd47f4cb5839a99766e8c1f3be8d3e376efbde7cd9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < (tType); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math80
### Patch Diff Hash-SHA-256:

3153f03941baf2c52cfc37966a2fe65953a3cb9eee94e31a03f4455dba91e575

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (lowerSpectra) > 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math80
### Patch Diff Hash-SHA-256:

a4aa4941e3257944d41204ef8477b3d0bac228c656a3cf778e1e9fb0438c2fcf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(n + 1)])) < (work[(n - 2)]); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math80
### Patch Diff Hash-SHA-256:

57cd3793e8d4e6338682bfa1221d948c69f361f3a04de3a7aef45dc8d6827aa2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step < step; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math80
### Patch Diff Hash-SHA-256:

3662e5f226b8134fc376e24bcb3c550842338c92172f4aed41be6cd2e6675f99

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step < (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math80
### Patch Diff Hash-SHA-256:

590a9a32f87d26d122d7e5ccd54f5a6803563dafeb26179273de5ab3cb1284e9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(dMin);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math80
### Patch Diff Hash-SHA-256:

edf74294a7f791cf56b06aac506ff9cf468519ddbccf47e67f4e7d3607f1e673

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((splitTolerance) > 0.0) && ((splitTolerance) > (tau)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math80
### Patch Diff Hash-SHA-256:

8c00425dd1b627bcd566077cb68243d39fa99663372c78bafecfa6f191d030c2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(dN2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math80
### Patch Diff Hash-SHA-256:

e9e4c1ebcbc20dacd3c9466ef048f19615a91ff50531326138327fd3a2c028a0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j == 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math80
### Patch Diff Hash-SHA-256:

321a315f79214944c262a2109a28677cf22a605daedf737801928a6349f20414

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) != (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math80
### Patch Diff Hash-SHA-256:

ef3c0e37611e450228626cf7de81eaa7f01ba8c4f4c860edfce6471cfca3b3e2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(dN1);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math80
### Patch Diff Hash-SHA-256:

bdab74b08aa8d11dc5559e48895ac2e26a5b935ce292abcb3f0eb344392e4b5c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j < (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math80
### Patch Diff Hash-SHA-256:

b15462c4330707f5fd91d7873d273e22af2fa397a063ab266d62ca378ef1a46d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (TOLERANCE) < (sigma); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math80
### Patch Diff Hash-SHA-256:

3bf0ffb586a57335426a053ba1e720a20eedac4cffcc2fb02708c81202ab77a6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.abs(((splitTolerance) - (splitTolerance)))) > ((java.lang.Math.max(java.lang.Math.abs(splitTolerance), java.lang.Math.abs(splitTolerance))) * (TOLERANCE_2)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math80
### Patch Diff Hash-SHA-256:

e5b486d5618bc4563466c52f7669997640348daf259d5189108744e8ba28f881

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) < (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math80
### Patch Diff Hash-SHA-256:

4021536bad29a5898f23c82e69309ea0ffbcfe96c0b0989d7ff6642a551bf472

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (work[(((4 * n) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math80
### Patch Diff Hash-SHA-256:

dd2331addcf17839c9fa4257bb8769298533216944ecc3fabbcf7420bc5e10a7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math80
### Patch Diff Hash-SHA-256:

985edc3027155f0280c8f1ba2b3e7ddf1c18e1d681fe4dfa71fda57a730a165a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (g) < (dN1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math80
### Patch Diff Hash-SHA-256:

22b0d88da0aae74891c7e51554d64fe110a9a0cd21a5b1b7acdc226a0c552361

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(tau);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math80
### Patch Diff Hash-SHA-256:

8fbf91955d7668495a8ec7ab02cf3dc085313f18d3f0d53f3d0d48f721a5a274

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((((pingPong) == 0) && (((pingPong) - (pingPong)) > 3)) && ((work[((4 * (pingPong)) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (TOLERANCE_2)))) && ((work[((4 * (pingPong)) - 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math80
### Patch Diff Hash-SHA-256:

9573ff7893bea52fe741ad98a106511c527bd796a90f80f702bbd6dee58796ec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((sigma) > 0.0) && ((sigma) > (splitTolerance)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math80
### Patch Diff Hash-SHA-256:

2a588236b74fdc6393664a809e12fe525f80434477314e1a79aa8c0520be2ffb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((dMin) >= 0) && ((dMin1) > 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math80
### Patch Diff Hash-SHA-256:

56c3af991aa01210c813f75426eeedcd924d80c48203cc2b0790614b66535b3c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) < (-22); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math80
### Patch Diff Hash-SHA-256:

29b292a6c4fa2f84eaa5e6952d9fdfe2d12c1c0aaf26e5f8d776dbe7a1b7488c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j == 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math80
### Patch Diff Hash-SHA-256:

2fb8b3ee7c181b9b11430917fac94412c4e76ea6c697e152ed4bf2fdca3ce9bd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(splitTolerance);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math80
### Patch Diff Hash-SHA-256:

456c9ef93517768c366998fdf7007aa98ce1e5a48da147812a86ff2877d1778b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math80
### Patch Diff Hash-SHA-256:

88f99f10eea6c32544cb4477a96e4896eff1c54613c55bcb6f02bff662ed794b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work[(j - 4)]) > (qMax); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math80
### Patch Diff Hash-SHA-256:

1abbdffb4774623663865ea4d832928b52406fb5fc1f34bcd07ef87cc0d082de

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * n) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) && ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma)))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math80
### Patch Diff Hash-SHA-256:

b7fb9e700933f3087f3002545e632c571a76cfa234bfdb3d2d0713c4ae07811e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) > 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math80
### Patch Diff Hash-SHA-256:

6b3e89e6b4eab5b1ee94c69fdffcc25259cdc5109124628bfbbf56986dcf7aab

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j < n; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math80
### Patch Diff Hash-SHA-256:

227beecf82e6205df53419a7bfb56aaed2130499463891b72254b0f42abf462b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (eMin) > (g); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math80
### Patch Diff Hash-SHA-256:

7041172167d90f70925936b51418ddb939af7f4d76724257acf73daa9651402a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(minPivot);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math80
### Patch Diff Hash-SHA-256:

c2c2e04cdf61f70f7ca221661aee1a54d405432ab17364e4d0f69eedabbb95e8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work[step]) > (work[(step - 2)]); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math80
### Patch Diff Hash-SHA-256:

e9d0c2b50cf73ddb8bdc031291c69d4ed6a00e2fe36346fab88239dafb840ef8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.abs(qMax)) > (dMin1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math80
### Patch Diff Hash-SHA-256:

d41620c9eb898699a8619769713c456a887fcc1bd2dff86f20ce257428d3a9eb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((org.apache.commons.math.util.MathUtils.sign(dMin)) + (org.apache.commons.math.util.MathUtils.sign(minPivot))) == 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math80
### Patch Diff Hash-SHA-256:

8cacebf9faf807962a7090e4a8372db517afcb99c2e23a86d56c84e855bdd815

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < step; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math80
### Patch Diff Hash-SHA-256:

c0f09b07c531d4e7487f7cef63b7640356fa750f245aa62d887c5feec7318ac4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n < (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math80
### Patch Diff Hash-SHA-256:

1fefbc527e194d1d84101bc0a329b69843c69b4c53f82016b68a967867556841

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((TOLERANCE_2) > 0) && ((qMax) < 0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math80
### Patch Diff Hash-SHA-256:

03beea5b1b031e0329f63400e8883c03a1a9ac0a00891dc68e88e2ccaeacda2f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin2) >= 1; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math80
### Patch Diff Hash-SHA-256:

bf19bfc0f4efcd65dc7bd5be7bc24a77d786834481014014ba8c6fcff5da1945

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(sigma);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math80
### Patch Diff Hash-SHA-256:

579d22cb6bae7e31190344f21232888f52b3f8b5a2f842edecaaa07bec6178b5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN1) > 1.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math80
### Patch Diff Hash-SHA-256:

786d72dfdec76a34b2d0b8296c291b841a8d0600ab577bf614a27f30fd903404

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (upperSpectra) < 1.0001; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math80
### Patch Diff Hash-SHA-256:

2a72b299e841e75ca6aa878e768ea7cf99e1de74f1c4ba33d70e52be199f607f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (lowerSpectra) > 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math80
### Patch Diff Hash-SHA-256:

807eb3c103d5f256db1a4b5ef39e050054167661af27700777ea03d8da3306f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) == step; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math80
### Patch Diff Hash-SHA-256:

c8175dab2218feb8aac38d0302d49bc8439b01191da47bb4e07365e4e04508c9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((minPivot) >= 1.0E-4) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math80
### Patch Diff Hash-SHA-256:

9a153908a5d1c25838e475af27b58a44ff39ea72d84376fed5e64cb790673161

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step == 1; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math80
### Patch Diff Hash-SHA-256:

8e32a424f37f01c8fdc81e91b259cbfa21ec8fd7bdab63f19569d1700565995e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (upperSpectra) == 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math80
### Patch Diff Hash-SHA-256:

df600ea4b81017cf41da8a73af4069f5f212eaeec50cb3b582c8621cd4d507d9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (cachedV) instanceof java.lang.Number; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math80
### Patch Diff Hash-SHA-256:

a33654d3e7043b3082f85f09492858521a4835faa05b88cae6098fac92299995

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin2) < (tType); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math80
### Patch Diff Hash-SHA-256:

8da754dd8fda40cc09c5dcfff206a4132a481338b9d38f4aabe41d7c6ef4c1a6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math80
### Patch Diff Hash-SHA-256:

faa16f091e9c0b23980d3a5506f14a1ffd884e9215a2954efded6e9c2aadd1bb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (secondary) == null; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math80
### Patch Diff Hash-SHA-256:

d55a79ff85b22120e7475eedaa96456cf615d7822bb9f68fe0eed276198e6bb8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((squaredSecondary) == null) || ((imagEigenvalues) == null)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math80
### Patch Diff Hash-SHA-256:

59c186722e0177ddb96c68ebfdcaf799ef9054fe3b32b53c26580a78156dba61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step <= 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math80
### Patch Diff Hash-SHA-256:

f42278d4ff2f48050758ccae4029b724578545f6fa09e2fc40902722db585cb8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) < (java.lang.Math.min(tType, pingPong)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math80
### Patch Diff Hash-SHA-256:

730edc93dc2ccfe83fec5fb5e60ea45c8b0ac42c05339b5a9df169bd5d690b4d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step > step; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math80
### Patch Diff Hash-SHA-256:

d06e15cafd9a70da35fa68f0bdd823b504587319c0c8ba0908e3ff726fa584cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (sigmaLow) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math80
### Patch Diff Hash-SHA-256:

b4150df7ff743b2315a7b0035df44194a0167244e5d94bc461370d147eb94c5a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j <= 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math80
### Patch Diff Hash-SHA-256:

efaaf50d534901b7965440e842bfa0351d33c9a100a60dd35083825346152968

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(((lowerSpectra) - (TOLERANCE)))) < (0.1 * ((lowerSpectra) + (TOLERANCE))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math80
### Patch Diff Hash-SHA-256:

be77d93195fe3918f9ce1a73098c590b86a0491c9d18c5fb33a1e9d6b3de9f7b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Double.isNaN(dMin1)) || (java.lang.Double.isNaN(sigmaLow)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math80
### Patch Diff Hash-SHA-256:

a096f942e489e920d6c99e19b62f01c0cd7f7724560fef8ff71884fd5ab6f2eb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(dMin1);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math80
### Patch Diff Hash-SHA-256:

e7803242cdca98b80912c17c9c005205846e42e2accc30adc02f0e553038006f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (splitTolerance) == 1.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math80
### Patch Diff Hash-SHA-256:

ec5aa78e77cd21f831376201170146c9c9c8195cf441c1f9c3b10132568518be

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) == 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math80
### Patch Diff Hash-SHA-256:

240ffb492cea37a24965ede8fefc6c357e71d3be2693b36a4d9579ed080a0ef3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((java.lang.Math.abs(TOLERANCE)) < (java.lang.Math.abs(((0.5 * (TOLERANCE)) * (TOLERANCE_2))))) && ((TOLERANCE) < ((TOLERANCE) * ((TOLERANCE) - (TOLERANCE))))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math80
### Patch Diff Hash-SHA-256:

134c34dac7e17880b57d036b32d91239bb0cb1dc8b0dee809f4e95fd95147db7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) < ((pingPong) - 1)) && (((main[((pingPong) + 1)]) - (main[pingPong])) < ((main[pingPong]) - (main[pingPong]))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math80
### Patch Diff Hash-SHA-256:

d896635fd005b7cb9ab36aff80d9a52e531ce514687d3218ebc37d02372339a1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((dMin) > 0) && ((dMin1) < 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math80
### Patch Diff Hash-SHA-256:

1d9342116d39cbbfa885aa858ce7e60d44fa3bd93ff5966064553d347a339d3f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (splitTolerance) == 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math80
### Patch Diff Hash-SHA-256:

268db2b1991c9ca13313aa0b5b97dabfcd217606d9eebe375a2b39bd7dd1bac0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(sigmaLow)) > (dMin1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math80
### Patch Diff Hash-SHA-256:

3a474a24a975e914d76b9b6cda5c0a09ead7f04238961aebf58a2cb9836736c5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (false) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math80
### Patch Diff Hash-SHA-256:

3248125a6076545b848aac1e839299541009ee8ab08c922f22373af5fd950d0a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (sigma) != 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math80
### Patch Diff Hash-SHA-256:

dbeffdd111a622d2aa178c6bb23d79d154263fd3b33efa8709716fc40cdb582e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math80
### Patch Diff Hash-SHA-256:

86de917bb24625d267da7dd6155dbd8dd8c1319e08883744eea8cfd1eb9fca12

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((java.lang.Double.isInfinite(dN2)) || (java.lang.Double.isNaN(dN2))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math80
### Patch Diff Hash-SHA-256:

6465c20a91e65fa70e5c783a55c113178fcab5663c4d5f26fc1c4a00c4d4fd15

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tau) == 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math80
### Patch Diff Hash-SHA-256:

fff93e721139ceb217d0dec8c558ea41c14efe840470a43e6e1b95b2604c6a6d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isInfinite(main[tType]); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math80
### Patch Diff Hash-SHA-256:

7e9240c0390964e92c792133cbc639ea5746c70c1f65000f2f1b9c404f993120

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (java.lang.Double.isInfinite(main[step])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math80
### Patch Diff Hash-SHA-256:

96a2486f7425d5577039505ebcc67540cfb9b46c7d069764f8ee30d46e8fe081

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(g)) > (dMin1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math80
### Patch Diff Hash-SHA-256:

7876ba0212feb6502a429164ed22410a93c30edaad6cb3a743344c5802cd5e1f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((dN2) < 0.0) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math80
### Patch Diff Hash-SHA-256:

aa2b321dfa4f8b51b385aa1d8559cf2e89a00b94d117c4b7ce53aa13d03cd192

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) < (tType); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math80
### Patch Diff Hash-SHA-256:

73997961e89bdb89d73813fb29a74cbe02225ab9158aa04fceada13d3f28e023

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isNaN(sigmaLow); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math80
### Patch Diff Hash-SHA-256:

5af081e86166bad86ea42835002ebbf7e1a3d027df731d2a2db1260aacfd1a3d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (cachedD) instanceof org.apache.commons.math.linear.FieldMatrix; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math80
### Patch Diff Hash-SHA-256:

1ab7e1af32d21d4715b3d5861858827e0f279c59b77d5502baa443a023bcf4b0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isInfinite(minPivot); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math80
### Patch Diff Hash-SHA-256:

05bc945c86568924ba50253dcf428226fd24bdf28e2394eb91ed484ad35981fe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (step >= (pingPong)) && ((pingPong) > 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math80
### Patch Diff Hash-SHA-256:

d02afb4b31daa52aca4a369f35eb55de417cd2967bcb5d72c723ff30da9dcddd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isNaN(eMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math80
### Patch Diff Hash-SHA-256:

2b6d7945b3c0422f5b70b76b722b35f687a03824ac8efbc807bbbafb371960c1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (cachedVt) instanceof org.apache.commons.math.linear.SparseFieldVector; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math80
### Patch Diff Hash-SHA-256:

ae3e656abf7cd7eeefc08eb062f73f29f0360b2ee3942fd1101fa15f041e5d8f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isNaN(minPivot); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math80
### Patch Diff Hash-SHA-256:

7953aee125c72706eae2bd864911778e77a444211ffd40290e40aef8eb21eb75

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n <= step; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math80
### Patch Diff Hash-SHA-256:

50322bd7ca1f18a4987086f7698f4dd37c16317046a2789389caa0edf1cfc08a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (secondary[tType]) > 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math80
### Patch Diff Hash-SHA-256:

6019971efd16e33d26f361c5626cd338867744d7e7d140a5e17fd108979ef358

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (upperSpectra) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math80
### Patch Diff Hash-SHA-256:

2a71ce8841fece313ad56212bafa18e389f086e46d2e4d523b0bcb4b2d2671fb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (splitTolerance) == 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math80
### Patch Diff Hash-SHA-256:

a68116228edd98b965e8456aba6db67babbeebeda566b77eb039bbe4b8df7cfb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((splitTolerance) * (qMax)) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math80
### Patch Diff Hash-SHA-256:

7ab6aafc62a0c6c9a3123ecc094215f4a53d18d329e3a0131b0d856be1e9309a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((splitTolerance) < 0) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math80
### Patch Diff Hash-SHA-256:

cc07df048960df107391d950e74b3b79e7d2ecd4e30da4b7fd083a9b08132848

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(dN1);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math80
### Patch Diff Hash-SHA-256:

a5129acde7a7fb41308b3b98f38c0130c925f4fce3d54398db4ba97d7fb9e626

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n <= (tType); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math80
### Patch Diff Hash-SHA-256:

68450f08cae31ebebacec88773e87e2cc6a091cb566501a8eb3de08ecac6c065

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) > 2; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math80
### Patch Diff Hash-SHA-256:

17ef1e3fc14b93867c731d47986721ff9a764789ff4f0912dd053bf53f67e63a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) > 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math80
### Patch Diff Hash-SHA-256:

dadb8ad26ecea3a3fd8dcd98b1099b36d13fcee03fce26e70e082de510900f16

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((((((java.lang.Double.isNaN(TOLERANCE)) || (java.lang.Double.isNaN(splitTolerance))) || (java.lang.Double.isNaN(TOLERANCE_2))) || ((TOLERANCE) < 0)) || ((TOLERANCE) > 1)) || ((splitTolerance) <= 0.0)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math80
### Patch Diff Hash-SHA-256:

9e0af5f129d45dbab1baa7fda43ce0bfa8dc716b28d5f5c473d3756c3683a797

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (splitTolerance) > 1.0E15; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math80
### Patch Diff Hash-SHA-256:

dd90f365d248cb54e18dda95222eea7865425a878eaaa35ee71d86602a60d28d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((java.lang.Double.isNaN(eMin)) || (java.lang.Double.isNaN(TOLERANCE_2))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Math80
### Patch Diff Hash-SHA-256:

f274f8e18736a8a5e96a311f1dbe8a4c373a1bbed7bd7a3d8b88b4bb4da01580

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) > 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Math80
### Patch Diff Hash-SHA-256:

958f27632c759a97ea1aab6ad305b4f29325e58654f13bbfb4e6dfe7e8bdb2d0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.abs(sigma)) < (java.lang.Math.abs(((0.5 * (minPivot)) * (sigmaLow)))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Math80
### Patch Diff Hash-SHA-256:

4e7f4cf1fa5ad4d7fffda62991c3b2c32679b251f5d41f8bc2911be3e47c0559

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((tType) > 0) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Math80
### Patch Diff Hash-SHA-256:

ceea57b80d655dba77e094a3f8d0763e0ecab31a7d4187e1b345cc83f95fec3c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((tau) * ((minPivot) - (tau))) >= 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Math80
### Patch Diff Hash-SHA-256:

9d54fdf6e59a751071ddcaa222c1d15ae48031adffe4a2f5eff40455759fcdd1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isNaN(main[pingPong]); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Math80
### Patch Diff Hash-SHA-256:

9b9550b0d4b3565c6bffb881d57ca3d4f7b33ea69ef221bf11855ef7de662853

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(sumOffDiag);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Math80
### Patch Diff Hash-SHA-256:

993b1faef98c2f475b11f08ea37a00410ac7b3c7d77405c0451f548e04914648

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((cachedVt) instanceof org.apache.commons.math.stat.descriptive.AbstractStorelessUnivariateStatistic) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Math80
### Patch Diff Hash-SHA-256:

85dfb7e1155c7b198c35088fb71ee2f35a87de9571883cfaf890a7d43d0837c6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n < (n - 1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Math80
### Patch Diff Hash-SHA-256:

6bc8bbc84baa07dcd3cf7c58d5c16d989ea41bf1c9667bbbe29f6232a406b4f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (splitTolerance) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Math80
### Patch Diff Hash-SHA-256:

8753b659fb73445f2b1a92bfba99ac34947987e235e2b40c7f0d0b09b32b4f8d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (TOLERANCE) < ((((splitTolerance) * (TOLERANCE_2)) - (org.apache.commons.math.util.MathUtils.factorialLog(((int) ((splitTolerance) + (TOLERANCE)))))) + (TOLERANCE_2)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Math80
### Patch Diff Hash-SHA-256:

12fb330121dfb44140cbb62557889a3d9980f662a6aa254c69788d48e55851ea

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (eMin) > (dN2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Math80
### Patch Diff Hash-SHA-256:

e9dfccfdf15bb243f38f0fe6d3b1a531995cff8cbb4ca8084f7ee77281f2b3e1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(dN2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Math80
### Patch Diff Hash-SHA-256:

840753c191d4313c1f606d449ac0982b58721fd615a408e9cb765099314e60ec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (cachedD) instanceof org.apache.commons.math.fraction.BigFraction; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Math80
### Patch Diff Hash-SHA-256:

d9d457ab0c2c1f939948b68eab9376f3e8be1ab6f0df65086f8d005c892530c3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step >= n; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Math80
### Patch Diff Hash-SHA-256:

d1831639b943e2fcc5322315d8930a7e1f79d305ccf69503f10c61f0ea822f06

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n == 0) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Math80
### Patch Diff Hash-SHA-256:

69fefa62489eabe543adbf224054045412bc7c8781f72b203292af8d148e5d58

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (sigmaLow) >= 1.0E-4; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Math80
### Patch Diff Hash-SHA-256:

f008c7318ba90b51c18bd2f5be2a7d38ba1ebbe971cf8314f0f05eb57bcdd39c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((main[tType]) - (main[tType])) > ((main[pingPong]) - (main[tType])); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Math80
### Patch Diff Hash-SHA-256:

d4c062189ecf1d1d22abac6b458451833b06352155991a45e16d16a912f13f3c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.floor(dMin2)) < (dMin2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Math80
### Patch Diff Hash-SHA-256:

70df7968489c5abd9a9768307749f5440ce86b0b9cd517de4e785877f7353b13

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) < (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Math80
### Patch Diff Hash-SHA-256:

f4eb10f3a4f80562485d382184aca943bc6e2e27878f94a128fed90970791d35

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(qMax);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Math80
### Patch Diff Hash-SHA-256:

5bc08728ce156d9becd85b5e4c1cf5d4b60df291f15b07215d855927af93406d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isInfinite(dN); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Math80
### Patch Diff Hash-SHA-256:

0628d54fc4b3a6956cb058135f539b45de987e9ec099e0c969f5a01a9765ec82

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((dN1) < 0) || ((dN1) > 1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Math80
### Patch Diff Hash-SHA-256:

921e686fd2dc287e57801d41680cee185e70714fbdf42d445df3e94e95a258c2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) > (tType); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Math80
### Patch Diff Hash-SHA-256:

b62ed6026b30e7c95f265998dc30b04aa617efee7ab3e27e34f10073a0c938d4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Math80
### Patch Diff Hash-SHA-256:

498e667da6d76090a93bb643024f814445ec5e8f0f67fa892431d296dfdca041

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (lowerSpectra) > (((splitTolerance) + 1.0) / (((splitTolerance) + (lowerSpectra)) + 2.0)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Math80
### Patch Diff Hash-SHA-256:

605159a9c101d0c1a273ee807e532c3d635aed5fc979a29e4e8a87f1565aedbb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((upperSpectra) <= (TOLERANCE_2)) || ((upperSpectra) == (TOLERANCE)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Math80
### Patch Diff Hash-SHA-256:

648877c0166086b5634f0b031235048625f5b2617e06b020a7ba9715b8ada96e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) >= step; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Math80
### Patch Diff Hash-SHA-256:

bf41509411bedc3a4266891c3c147539b9b395138366de279b0718354e9f8e33

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(dMin);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Math80
### Patch Diff Hash-SHA-256:

d7d8c5910a202298acdf7c790eabffb31bbe7f511c74ad8e6e1546c98b1aba94

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) == (-1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Math80
### Patch Diff Hash-SHA-256:

4bf061aa7bcec6c24b5f4d7fbd42532c37ea7bd24c8275dab77a3fc8de8a6699

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isNaN(eMin); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Math80
### Patch Diff Hash-SHA-256:

8edffa564ceb84c207870ac0b15999a4ab77653f373beeec8135647d9855b04d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n == 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Math80
### Patch Diff Hash-SHA-256:

35f3b437aeb54b844a37f2a9023f9677e9089702af22b46cdb178bbeca6b7ac4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (cachedD) instanceof java.lang.Number; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Math80
### Patch Diff Hash-SHA-256:

99e05e1f9038c8c0774eb8150eb43bb4e4fc096f621752064e76c19d8ec632f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (qMax) > (dN2); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Math80
### Patch Diff Hash-SHA-256:

3dc7f1645f017c61962314a0fa608b549fdb93afaca2190e4053f9089dfe428c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; super.equals(cachedV); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Math80
### Patch Diff Hash-SHA-256:

d0806b37bc4c0d0d8b7a4c13df2a381bbb5f22ebd656d7e3539ffed496123743

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (splitTolerance) < ((lowerSpectra) * ((TOLERANCE_2) - (TOLERANCE_2))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Math80
### Patch Diff Hash-SHA-256:

c6076ef81a058bd003a84caddd048abff57e1fb46b4216ccbcccc43f854f3cae

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(lowerSpectra);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Math80
### Patch Diff Hash-SHA-256:

8d35f899b980dcbd3ea4c8f4de5902c6a245196abba6c96239c3ee76840ac98c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (squaredSecondary) == null; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Math80
### Patch Diff Hash-SHA-256:

d6ab628d5465c4ea46115a959cceb4a4cc6f5bdfaa5ef10792228db5a9f60044

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isInfinite(upperSpectra); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Math80
### Patch Diff Hash-SHA-256:

04042ef831302e233dfba3db8ecb845adbe29fcb7eb70377fbd270afc323a49c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (main) == null; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Math80
### Patch Diff Hash-SHA-256:

00bb82694f6bc70d8f19ab7d3b0fe0586b7b38f316109573d0bfd1d5b5ace27b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isNaN(TOLERANCE); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Math80
### Patch Diff Hash-SHA-256:

b8e2be3103d9c3fa36aa28fbfd06bc4df1e3a2fd81b085b59888d722f86b9c7a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((((lowerSpectra) == 0) || ((splitTolerance) == 0)) || ((TOLERANCE_2) == 0)) || ((TOLERANCE) == 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Math80
### Patch Diff Hash-SHA-256:

4023a4c8afa56391a22a70fdaa64fa55218a45eca26f37c60766020366f530f1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN1) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Math80
### Patch Diff Hash-SHA-256:

3f96835495ab11e4f01cb620b3192760d573dbea48febb47c2f399c4eec862a9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) > 1; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Math80
### Patch Diff Hash-SHA-256:

1de84de2982ba12e9e0b6e85f4505b62b4b95ffae6e01fbc62d26fa05676fba4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (n < n) && ((lowerSpectra) > (TOLERANCE_2)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Math80
### Patch Diff Hash-SHA-256:

973700ab3c6dcec79a72185e605daf5bea515e1a6ac5d3b3a310101ca9f21959

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((java.lang.Double.isNaN(lowerSpectra)) || (java.lang.Double.isNaN(minPivot))) || (java.lang.Double.isNaN(tau)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Math80
### Patch Diff Hash-SHA-256:

cc68109a7437c6d74e3918e3d8b06d41f6f368528ae8319ed75e41225daf5ebf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Math80
### Patch Diff Hash-SHA-256:

74c1ccbfe083b22fbd63f638d91cc74504e4018b867ece79a5129d143f43b223

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (java.lang.Double.isNaN(splitTolerance)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Math80
### Patch Diff Hash-SHA-256:

23dc53816cb4f826e3dbcb603478de6e9ae90a8a21bb25aefbe5d81cf07acf33

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN1) >= (minPivot); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Math80
### Patch Diff Hash-SHA-256:

c1f43ae4025b11b4407097910b6d4bc2eb2fb2532d85c17c5da5ec3997495cfb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j == 31; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Math80
### Patch Diff Hash-SHA-256:

84e06dedcc852f8cb106ef39c70b5955fc4a2be090d265e8bed75918dde56e05

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (step < 1) || (step < 1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Math80
### Patch Diff Hash-SHA-256:

d04cc4e04715997d1018cb89859fb56cd6e24f31c4dcc4b46261087a8481e98b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step != step; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Math80
### Patch Diff Hash-SHA-256:

65361397a42d7130d2a77ef593f3f754378386deb8f100c7a7b9b2e0b3e449bb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) > j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Math80
### Patch Diff Hash-SHA-256:

ec200db95edafa3f6f59c991a0ecc83537b374fe4193e7ab845f84eecc18eb28

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isNaN(dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Math80
### Patch Diff Hash-SHA-256:

acf8a65a48b1ca256cd4c1ed58b11cfa74f1fd8941561b7bff7097f092b7ae53

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) == j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Math80
### Patch Diff Hash-SHA-256:

7a36ed72ae79dd404b1de9c9f7b6ce471891933ef689a9523e6dd1c78502567f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin1) > (tau); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Math80
### Patch Diff Hash-SHA-256:

d89114b2a10de1c0909dd3c6972b87186b98a02b1f9459916779188d28542e14

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n <= 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Math80
### Patch Diff Hash-SHA-256:

c65ce09377b72505ab4a654f09534ae40092252a5c2109092be4794a65b32414

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n < step; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Math80
### Patch Diff Hash-SHA-256:

b0fe2aa4fff1fcc16362ac9b2eaffc74693b436d37bc2ac6842b07e9b30f6ee4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isNaN(minPivot); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Math80
### Patch Diff Hash-SHA-256:

7cb2379ea66f78e1ade03606e2332bcaebc0a394bb3d225242f690df4168c773

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) != (step - 2); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Math80
### Patch Diff Hash-SHA-256:

b1ef27e84b085f1f0903a22819a622f21a1f973b7e9f8a87f0f4d5eac3527ea3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(TOLERANCE_2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Math80
### Patch Diff Hash-SHA-256:

0e26eeb4c8d52c495c9b7440df9024c4536e1933c9bc13a9f4320006729f6196

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) <= (step - n); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Math80
### Patch Diff Hash-SHA-256:

8380ac4b0c7c237acc6317d9223d3af8b69162df9b9a88d35aa65d1ee684589c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n < 2; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Math80
### Patch Diff Hash-SHA-256:

683358f8f4212323ecb9b7e1216a2630229cb371852b9b871843a077e2a366e8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isNaN(dMin); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Math80
### Patch Diff Hash-SHA-256:

e6833a0a45b0a01016641875228a5821ac31e4eba6eaff028b28805d61f0d7f7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isNaN(TOLERANCE_2); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Math80
### Patch Diff Hash-SHA-256:

e34cfe9c3acbafc1e95188edac1c09efa47e745a5fd569e0323323fddf53c2cf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (minPivot) < (lowerSpectra); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Math80
### Patch Diff Hash-SHA-256:

340c88e3b2d40e1bc26014536bd10dacc6581feb52342031fb1021ef396368b3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Math80
### Patch Diff Hash-SHA-256:

fb89b0730922a603f9bf92d7d5ca31aa589d35c7bd79f88eee2b28d8ece9cd39

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((cachedVt) instanceof org.apache.commons.math.stat.Frequency) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Math80
### Patch Diff Hash-SHA-256:

1889194c0484e260aab010ebacac26b36c90cd02ac3e6b450ae1388acc2690ae

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.floor(eMin)) < (eMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Math80
### Patch Diff Hash-SHA-256:

6ce8491d3cb96d11b6e26645d64161a763751467b8307fd8d7ae9039fa661140

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) > 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Math80
### Patch Diff Hash-SHA-256:

234869bb93c5170c97ff0c6603e986fd3c96a56736f848b3117756100530296f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((java.lang.Double.isNaN(TOLERANCE_2)) || (java.lang.Double.isNaN(tau))) || (java.lang.Double.isNaN(TOLERANCE_2)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Math80
### Patch Diff Hash-SHA-256:

dac5aac8059fcda039352d69fc9fc71db7ee91525582ec2662e4ac67d8d9b97b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Math80
### Patch Diff Hash-SHA-256:

98ee23ea2eaf8a761028b749dd1830ac12159c2dda7e4d58c0fa5c68c4fe8f69

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN1) >= 1; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Math80
### Patch Diff Hash-SHA-256:

0957e043770da52c73b581fc6628fd11653595c51b4e0d746cb10b91b159f4e0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((work) == null) || ((realEigenvalues) == null); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Math80
### Patch Diff Hash-SHA-256:

dc0787bcc99f4c957bd963c639c6c483b6da320b0b5d4d4650f20106fdd5aab3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Double.isInfinite(upperSpectra)) || (java.lang.Double.isNaN(upperSpectra)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Math80
### Patch Diff Hash-SHA-256:

924e0bcabd2ec92851e13fe88e59aa7bad30cbc7a79a1479fe3fc4801fb1d07c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step == 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Math80
### Patch Diff Hash-SHA-256:

1a87a4c47b21880d56d002615f69314c5b3afb20b853346f7c1a370aa548a9fc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j < (tType); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Math80
### Patch Diff Hash-SHA-256:

5b2e130fbce4d6fc58bad8980c4e958722026918217e6ba8eeadada166aafa4f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n != n; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Math80
### Patch Diff Hash-SHA-256:

b4656e44a8ff8c040bfd637df447e3021f3e7ae49ec3f2a8970d6be63b19936e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step < (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Math80
### Patch Diff Hash-SHA-256:

ff927916df9af814d2c33ce6b89615a1b3a46f2d3969584b70ff2edd00bfb9ba

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((secondary[tType]) - (secondary[pingPong])) > ((secondary[pingPong]) - (secondary[tType])); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Math80
### Patch Diff Hash-SHA-256:

80834176e0839b391e2e0db923d5aa7edfe0277ee6e28a4478fae49b2404678f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) > 2; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Math80
### Patch Diff Hash-SHA-256:

e7d3d5201eba4acd526cabc80f4daf0eb15162623f397a77429868d7dd95dba8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((java.lang.Double.isNaN(splitTolerance)) && (java.lang.Double.isNaN(lowerSpectra))) || ((splitTolerance) == (lowerSpectra)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Math80
### Patch Diff Hash-SHA-256:

0f388433915550d4d71dc6253e797f47c27fae4f90be2348c24c4c09ed4d889e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (g) < 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Math80
### Patch Diff Hash-SHA-256:

2fad8b420e715b330c36e261b14201d0982943f737339042e264ba5b6cfd7358

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((TOLERANCE_2) > (upperSpectra)) || ((TOLERANCE_2) < (-(upperSpectra)))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Math80
### Patch Diff Hash-SHA-256:

a4f03b981af2db036c7b003c3e4d489365bfc0b4348f3f90852ee5b533c23504

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isInfinite(dN); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Math80
### Patch Diff Hash-SHA-256:

b73c72ae7adc2505d5b05596ae1da28329fc6e77c305e9687537afd570b3bba6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (TOLERANCE_2) < (dMin1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Math80
### Patch Diff Hash-SHA-256:

5b13a0aed676166cc19c976419545aa928c3f8437393e8568089950f3fe0a361

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) > 1; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Math80
### Patch Diff Hash-SHA-256:

f075e10bf5cf9d432e018d8c2560d5d1b5636e28c0888240ce9ca0cf915388f0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) == step; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Math80
### Patch Diff Hash-SHA-256:

99e97075f5db1a32a6375274ae463ff2a1db8fc4883e665079bbb4e605b640b6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((tType) >= 1) && ((squaredSecondary[((tType) - 1)]) >= (squaredSecondary[tType])); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Math80
### Patch Diff Hash-SHA-256:

2555f325e5ea1da6eee51ccfdc9c19ff4909b173a59ba18ef80b59169c787632

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Math80
### Patch Diff Hash-SHA-256:

354de8b325461348db04b6587fc8a215979cb6df3ee00700e23ac5c0579c0a24

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (g) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Math80
### Patch Diff Hash-SHA-256:

1bbbb4e4d8d9e984b426a26fc2ac82fbc9338c167ce083d997d15f41bb7b4145

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) > 1.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Math80
### Patch Diff Hash-SHA-256:

b66b3276916d8790aba4eaa2bde8f8dfe70612c2590dee68d0af6b85c0d532d6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((sigmaLow) < 0) && ((dN1) > 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Math80
### Patch Diff Hash-SHA-256:

8bb2fa60e22ed69ba7659e3d58363b906c14085b466004c2561b264d285c9b70

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN) >= (4 * (TOLERANCE_2)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Math80
### Patch Diff Hash-SHA-256:

fd13666ccdc0d09c118cb2c33dc64e69c4a4c521a4afdd81d083842fd58911ad

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (lowerSpectra) > (sigmaLow); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Math80
### Patch Diff Hash-SHA-256:

427e1c2093c7ac5352bd14a1391a643448e64a6e92b97809b64b275ebd752695

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((pingPong) + (tType)) > (tType); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Math80
### Patch Diff Hash-SHA-256:

d1483cd07ade65f5a846244f8ed7b6ad906af1cc8e0b83b40bdfc73bc15bb078

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (cachedV) instanceof org.apache.commons.math.stat.descriptive.moment.VectorialCovariance; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Math80
### Patch Diff Hash-SHA-256:

a5b9b1955d86a20aff02e933ae96a4bfb022043da02e8d526e2c98adb21ad68f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Math80
### Patch Diff Hash-SHA-256:

d01c34daafe1d7877804bf72171c3d10927ae444bac228623d466aa20681fe8e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN) > (TOLERANCE); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Math80
### Patch Diff Hash-SHA-256:

0919ef023de59c643ae71b9ffd56afd9b552e4f150b5cce87580975c278e67ee

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (cachedD) instanceof java.io.BufferedReader; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Math80
### Patch Diff Hash-SHA-256:

185f751f03665cd66b09f1f4d0c2ba4d7cc1937d452a7d7279e5180a33e8ac52

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n == 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Math80
### Patch Diff Hash-SHA-256:

512b16236f6f954ebb830b60f5d17996e8b70974ddfe8151ac6bf39ac185cb92

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < ((4 * n) - 2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Math80
### Patch Diff Hash-SHA-256:

d70e200f53717ae765088578a9649afe9f0031dc22e6ceab9822955fa99b84da

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(dMin2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Math80
### Patch Diff Hash-SHA-256:

fffab846778648bd50b594df7255d8074e258c1da9b749895c56684e8c199d93

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((pingPong) == (pingPong)) && ((pingPong) > 1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Math80
### Patch Diff Hash-SHA-256:

0b94ecd9ec48e6d379a0058908ce659984d7663305948f36ca1832c52b3adbe5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) > 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Math80
### Patch Diff Hash-SHA-256:

723f0cf2562f0c961f16e6ac872a1126ce0d8a896382d77ef302761e961e6f41

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j < j; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Math80
### Patch Diff Hash-SHA-256:

25ac1edf4bec56de7ff32be7e1d235fcd5efef0281aef13bcdbef08cf2c62280

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j != j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Math80
### Patch Diff Hash-SHA-256:

f2458a85b6f085d321e980a7b4597d4239897ddb9b5c7d8b39906c5c3849d400

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(eMin);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Math80
### Patch Diff Hash-SHA-256:

ea8dc14e474615cc1fdf751ef40f3166c0b2d4a238106f7396a8886ae3ca5e0a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n < ((pingPong) >> 1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Math80
### Patch Diff Hash-SHA-256:

ad040a4be4435bf039b3c85c35ca63f32daad6f594912aa78f0e97b2c5c6007e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Double.isNaN(dMin1)) || (java.lang.Double.isInfinite(dMin1)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Math80
### Patch Diff Hash-SHA-256:

235e5893a173c32dc1933e4c2e1a3c190bc12e5c97ceb828f2eb749fae91c6ab

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isNaN(work[j]); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Math80
### Patch Diff Hash-SHA-256:

a071257df6549d06ed49c6843a5372ea412b3a760bd08c4035f51c398cc8190e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isInfinite(splitTolerance); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Math80
### Patch Diff Hash-SHA-256:

a45a621d385797271e419c39e03ca4f51ccccab57438c0a3718ae4689963cd3b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((dN2) < ((2.0E-15 - 1.0) * (g))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Math80
### Patch Diff Hash-SHA-256:

6069eec6af0f865cbf2dcdc6fd98a73db62746cfb1ef1ef0e8c909cc2ac9cb0d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (qMax) > 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Math80
### Patch Diff Hash-SHA-256:

8c909eb350884b0eccbff5410b819d95dde48c369a5f2aef392da89b451cce88

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Math80
### Patch Diff Hash-SHA-256:

810a29d90a4f0557e7ed61bc0723c93e622a1879a0e2bff11da1f8d784b70ca7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(qMax);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Math80
### Patch Diff Hash-SHA-256:

21ff66282e0c7146f6dbda0cf44b31a7215fffd5fb3123c05f7b02b85f8a6703

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (eMin) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Math80
### Patch Diff Hash-SHA-256:

cdf971577bf34d8982763a6ca0b51763a3a01d951f8115f30802b5314dcbd774

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < (4 * (step - 3)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Math80
### Patch Diff Hash-SHA-256:

3902ca8c85a44fbb48eca390a91ee8140314171be18042ec7ad1ed0b4554ca94

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (cachedVt) instanceof java.lang.Number; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Math80
### Patch Diff Hash-SHA-256:

5d4561fd7e0c89074374043f1c606eaacbf9cc3daac477bab7bb0c9af91d61e1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((java.lang.Double.isNaN(TOLERANCE)) || (java.lang.Double.isNaN(splitTolerance))) || ((TOLERANCE) <= 0.0)) || ((splitTolerance) < 0.0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Math80
### Patch Diff Hash-SHA-256:

d27aabba05af498c90e9a48261fc9c32a9b522f35cf9bc1a54a23d7bedcfbf61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((dN1) > 0) && ((dMin) < 0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Math80
### Patch Diff Hash-SHA-256:

cbd17da3d15d3906901093d41125ca555816ed143b0a199e6eeee646b4f8094c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin2) < 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Math80
### Patch Diff Hash-SHA-256:

cbeee3ba5adff74b2a67d62f105930016e9f56f78918ddc2bfae7d96c2eab644

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step < ((4 * (tType)) - 16); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Math80
### Patch Diff Hash-SHA-256:

a6d826c29fd0cd8468c20421d9e7d902984a15a61e02fcf307828ac73bb9eda6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((splitTolerance) > 0) && ((eMin) < 0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Math80
### Patch Diff Hash-SHA-256:

d1676fc6f2dfb581ec8f84ebce314022e5b431711b3b181e9693164304922af0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((qMax) * (dN2)) > 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Math80
### Patch Diff Hash-SHA-256:

3e2217256e4da9200baad663181681f78752e90253de988218508c438fb8fdf6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((lowerSpectra) == 0.0) && ((lowerSpectra) == 0.0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Math80
### Patch Diff Hash-SHA-256:

44ed6a239beb489b44e5ae698894297cf77a0f88b94be29ac5f182bc1f1fe3e4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((TOLERANCE_2) >= 1.0) && ((lowerSpectra) > (TOLERANCE_2)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Math80
### Patch Diff Hash-SHA-256:

e53ac56af50f9c4d5d701c29acc8e973497f1b6e821a00c255e3381554c87eac

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((tau) == 0) || (java.lang.Double.isNaN(tau)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Math80
### Patch Diff Hash-SHA-256:

c361d45a47ce8f92230e16715cff981c0e6dcb0e29663397a1cc80a109f0bbb1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN) != 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Math80
### Patch Diff Hash-SHA-256:

645ceea42512502f971771ce5bc089ac6c13fe6ea14dd0bc08494d3e49d0fa5d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin2) > 10.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Math80
### Patch Diff Hash-SHA-256:

d20a1a764cee97e7d748d93baa9f8c6f781d06fbdc743626b542424264d23bb8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((org.apache.commons.math.util.MathUtils.sign(upperSpectra)) + (org.apache.commons.math.util.MathUtils.sign(TOLERANCE_2))) == 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Math80
### Patch Diff Hash-SHA-256:

070d192c581d435c0fa49b2ea777c1eb20b8df543253f1387dec5a81a46427ea

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Double.isInfinite(tau)) || (java.lang.Double.isInfinite(dMin1)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Math80
### Patch Diff Hash-SHA-256:

e62faff89c0e510687e2cc1091123c7499e2f2fcef1458f56a36415bf4050342

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) <= (4 * ((tType) - 3)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Math80
### Patch Diff Hash-SHA-256:

5f337223d418095706ff3bcf95d5be96d00e636ab5da18183eaf8af9d27886d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) == step; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Math80
### Patch Diff Hash-SHA-256:

d22ab98fd7b0da6c4e75d1a91cdd5cba3abc738870812397a5d0eed72d736e5d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n > n) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Math80
### Patch Diff Hash-SHA-256:

c40ec34537612b8b650d9c1e3557541acc6339c875ea10f97d2ade71807b96c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step == 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Math80
### Patch Diff Hash-SHA-256:

e4326fe3749fd1879e81f636b4af9a8a2e3aa2c94a6505518000d41df559af22

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((java.lang.Math.abs(TOLERANCE_2)) <= (0.1 * (TOLERANCE_2))) || ((((TOLERANCE_2) == 0) && ((TOLERANCE_2) <= (TOLERANCE_2))) && ((TOLERANCE_2) < 0)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Math80
### Patch Diff Hash-SHA-256:

b076477f26ef4a486b03ef8417e609360447fe1cf885f3c6979c6be918b2d167

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step <= 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Math80
### Patch Diff Hash-SHA-256:

afc38b5ec58be27246d31a7c21a373e0114d6dcf3e33e9c93ced9711f60875d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < ((tType) + 1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Math80
### Patch Diff Hash-SHA-256:

23a6d35bb1252c52917c58828177c1b76c507e9341bac9e28d540016e0662f69

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < (4 * ((tType) - 3)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Math80
### Patch Diff Hash-SHA-256:

3fcf4d490628453f8ea1dfc365cf026ed430519e6104c20eb8f19f0694fd345b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Math80
### Patch Diff Hash-SHA-256:

ab87c1438a4bbdc29d5d2a7a34f166c7434a9fd45aa4de5006ab34868e23424a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (minPivot) < 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Math80
### Patch Diff Hash-SHA-256:

bfb843f4d1663f8ab5eb48f0841d502de31b6622b3bf8b3b322b2f4cbd5de33f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Math80
### Patch Diff Hash-SHA-256:

bf7e42be30e9f2b6647427927a093da2e3bc4bed54905b68b372626799019c20

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((java.lang.Math.abs(upperSpectra)) > (upperSpectra)) && ((lowerSpectra) < (tType)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Math80
### Patch Diff Hash-SHA-256:

eef10bf64274c2d0c536a13cb5ab92013355692d675ba85969ddbec8ced62dad

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN) > 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Math80
### Patch Diff Hash-SHA-256:

2b11bd60efb731a366b4a60656e052758e17cc23079e317581ef7b517480e7f3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n <= 0) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Math80
### Patch Diff Hash-SHA-256:

2a67bb73374c589415a56e5d7e05e43daae488925c1e467c7dbbfae6da2eef66

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (java.lang.Double.isNaN(secondary[pingPong])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Math80
### Patch Diff Hash-SHA-256:

f78255b5a589212b86275a92ed88dc466a495f6611db3103e45c359a9c860058

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((pingPong) < ((pingPong) - 1)) && (((main[((pingPong) + 1)]) - (main[pingPong])) < ((main[pingPong]) - (main[pingPong])))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Math80
### Patch Diff Hash-SHA-256:

f7474eb170e8b5f4098ad719832c351a75ec401f05fa0b6b9ebe37e304682b49

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (main[tType]) >= (main[((tType) + 1)]); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Math80
### Patch Diff Hash-SHA-256:

c7ff0f96949c4b011ca98995e4b13e12c9438f71a082ee2cb451dc515def6319

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin1) > 0.9999; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Math80
### Patch Diff Hash-SHA-256:

a13e1c9f73ac45503d777996f91d522155f7c0cf04ad6ad192a49ddd6425fd16

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (eMin) > (dMin2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Math80
### Patch Diff Hash-SHA-256:

e4f4e249105d58228847d37c91a80cc02ce883e6d04080ba0b580cc28e9c456d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (cachedD) instanceof org.apache.commons.math.stat.descriptive.moment.VectorialCovariance; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Math80
### Patch Diff Hash-SHA-256:

70c3607e2f3663aa9caa8e4bc87f5e554ac25c765a585c227f0ebaa064d5bcef

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (TOLERANCE_2) < (splitTolerance); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Math80
### Patch Diff Hash-SHA-256:

9bec5694888e28deabf2cc04383c15947cd51fd38b13bab6f8ad24f0d2df8c97

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (splitTolerance) < 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Math80
### Patch Diff Hash-SHA-256:

e231958a778301a829b41f500a015cbf790ff8f0c3d9530ea1a549b43a2c097d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (java.lang.Double.isInfinite(minPivot)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Math80
### Patch Diff Hash-SHA-256:

764686136256a515f30664e3dd9345efa8b668fa0990490045be8087e09a805d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step < ((tType) - 3); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Math80
### Patch Diff Hash-SHA-256:

1a24bf1e055d7ebd023d713bfa2a2db16992599ab83f19a62eed60453149fa0d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (n & 1) == 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Math80
### Patch Diff Hash-SHA-256:

530cc04331d0d13a065afa5db6e5226c28694151321ffd16896727a86589b7b6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isNaN(TOLERANCE_2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Math80
### Patch Diff Hash-SHA-256:

69e370b7ce22fc3eb3605ed3afd532c62f5c8f6600b971d68f8d100ab5359daf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (minPivot) < (-(sigmaLow)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Math80
### Patch Diff Hash-SHA-256:

18803683b31fffadf42a7d3584ef3e2ec68879b28b4b40a200d221f7d05a4237

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((qMax) < 0) || ((qMax) > 1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Math80
### Patch Diff Hash-SHA-256:

f5d8ac5be5adc78e13340a3c3576aa37902a6874a2eb4fa2dc8a8b7fd38f5fcb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (j == 0) || (j == 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Math80
### Patch Diff Hash-SHA-256:

d3f4ac52b501ad9a2410c437ca3dd4ec035bf11d5c263912ff6018f0fab34b2c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) == 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Math80
### Patch Diff Hash-SHA-256:

ecaa6d75fd9d949a4051860f9404a7ebb1284320f4c69062c57bf0edfafc5ac3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (sigmaLow) == 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Math80
### Patch Diff Hash-SHA-256:

7425d2569bdc4b313a8442d1197bba395135143c0f6325a5fcd6db0fbad6b6eb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n <= 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Math80
### Patch Diff Hash-SHA-256:

56a44e878726fc3ee56e20af34ab8d1579d648b5eb79c0e6c924418d0678da0f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((pingPong) == (-1)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Math80
### Patch Diff Hash-SHA-256:

2c70e4ae6e3b84cb467033305e0e9fe691daca80553351edf743a396eb04d0ee

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step <= (4 * ((tType) - 3)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Math80
### Patch Diff Hash-SHA-256:

70d414fc9df84185d1ff6cce474bfeedc53e504f155eb4ad81a10125d6689521

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (cachedVt) instanceof org.apache.commons.math.stat.descriptive.MultivariateSummaryStatistics; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Math80
### Patch Diff Hash-SHA-256:

21480f187557e2347739c49f51a031d136640c1738c2745a6153afe835a0ee05

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Math80
### Patch Diff Hash-SHA-256:

ae1d73ef9477b84eed49644f192d474772ecf73e832bc72791879adc9a9c5b57

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN2) > 0.5; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Math80
### Patch Diff Hash-SHA-256:

24139c650d00a6cfcb6179a14ef213e911ddf9ffce6f4f40df54189e60ea07c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (main) == null; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Math80
### Patch Diff Hash-SHA-256:

f258a303dbce12fd56d66d05a33192222c631d9f4775d7d54447eea29f32a4be

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (j == 1) || (j == (j - 1)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Math80
### Patch Diff Hash-SHA-256:

147886cd478ad2be8463475b7f41f286855199d223f255ed388f6c3592e06de9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (g) > 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Math80
### Patch Diff Hash-SHA-256:

32dea27e8f35fcb9b8fbfbb807ab02d7afe20ec781647b3da7d033f7715af836

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isNaN(imagEigenvalues[pingPong]); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Math80
### Patch Diff Hash-SHA-256:

37b0af495924dca9ff995a02b6c8e55ea3960a681140fdf9a4fc00eee90e6956

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((secondary[pingPong]) - (secondary[tType])) > ((secondary[tType]) - (secondary[pingPong])); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Math80
### Patch Diff Hash-SHA-256:

b45e6ad6849f978f5506aac41dbf7865ebb017681443bfd502f040335c547bfe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin1) >= 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Math80
### Patch Diff Hash-SHA-256:

92d052f0d67b74423e0edf529935649cf9e0b7615c61e69f4fe068cd69434c18

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Math80
### Patch Diff Hash-SHA-256:

7e574d4d5ded23b4f26c4e481da29ed207573857ec0819cead1b43f2f51bdd51

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((secondary[((tType) + 1)]) - (secondary[tType])) < ((secondary[tType]) - (secondary[pingPong])); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Math80
### Patch Diff Hash-SHA-256:

0e1c1608c35b5bd35a86cf2c8d03cf2df17dbb20a3da308f4e4f0ab73786250d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((pingPong) == (pingPong)) && ((pingPong) > 1)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Math80
### Patch Diff Hash-SHA-256:

81ca893915b245413a8c363f6688ddc5fa2d7e1deb029e5314e5bb8765046b02

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.abs(upperSpectra)) <= (java.lang.Math.abs(dMin2)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Math80
### Patch Diff Hash-SHA-256:

f524f7d04529a376692d997cd8fa4eac911376478ec439ee1511204d41a1f94e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n <= 6; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Math80
### Patch Diff Hash-SHA-256:

89bb61688ea845a4008333b91935b8df6a7c0ff9b83740655c3c6cd1fb096d25

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN1) < 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Math80
### Patch Diff Hash-SHA-256:

63654b830fbf3482efeb264e71f9cdd47d16be4c197e7a8e0d4a401fcd7cab79

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (cachedVt) instanceof org.apache.commons.math.analysis.polynomials.PolynomialFunction; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Math80
### Patch Diff Hash-SHA-256:

519c96caaf8e45fca21114afa97e93b7bbb2d5452927b88078e04d11c512e039

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (2 * (pingPong)) == j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Math80
### Patch Diff Hash-SHA-256:

a8ca615fc19d0820a9ec616cc2768ec67d4becb0d81effb777ce8155d0c0a096

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (cachedV) instanceof java.io.BufferedReader; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Math80
### Patch Diff Hash-SHA-256:

e281781deace857a90587ae24f11a2be66068411237de0d80ff6133784a70961

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j <= (tType); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Math80
### Patch Diff Hash-SHA-256:

24a5674d67e02d3d491b8f510d1fa580bf2443427634f503359645590ced6cc9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (TOLERANCE) < ((((TOLERANCE_2) * (TOLERANCE)) - (org.apache.commons.math.util.MathUtils.factorialLog(((int) ((TOLERANCE_2) + (splitTolerance)))))) + (TOLERANCE_2)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Math80
### Patch Diff Hash-SHA-256:

5304f19b5fe717f6b2f11efacc79c4cea6840c29705700e2b9046499ef9e5108

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((TOLERANCE) > 0) && ((splitTolerance) < 0)) || (((TOLERANCE) < 0) && ((splitTolerance) > 0)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Math80
### Patch Diff Hash-SHA-256:

be5b7025d633eb2f7de546cbb56203fe19b37a5d4b61fe93294effed5dc68184

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (eMin) < 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Math80
### Patch Diff Hash-SHA-256:

b9e6c1055038fba689eb82c1295d8a9207babb0f6adc6140eea312283e41fcd8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tau) >= 1.0E-4; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Math80
### Patch Diff Hash-SHA-256:

9c9ceec4ca5863b7935cdac17c2829bbd7b8adf8a37d615945f95e618d9e181b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (step == 1) || (step == (j - 1)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Math80
### Patch Diff Hash-SHA-256:

77de93b3eced8f99791563484ba40a92ae01623ac953b56493221706ffa9c0c6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Math80
### Patch Diff Hash-SHA-256:

95906d899311c60e7e574d00ae7c1caf5bddf94926afc7b4190906de75c4ac9c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n < (java.lang.Math.min((step + 1), pingPong))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Math80
### Patch Diff Hash-SHA-256:

034ad31de048043a7ea21f3a982bf03900d02cd407c89a889ea1191ec8c6d2eb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) > 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Math80
### Patch Diff Hash-SHA-256:

cf4bc7143a13d831dd73ac0e2050ea14a5fe8a98d3a5cb979d4e196d1078f542

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.abs(((TOLERANCE) - (splitTolerance)))) > 1.0E-5; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Math80
### Patch Diff Hash-SHA-256:

9704261db05faeb2bbfab4c71751636d158d6ed9e62465664ad69a3d8b443acc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((java.lang.Math.abs(((upperSpectra) - (TOLERANCE)))) < 1.0E-6) || ((java.lang.Math.abs(((splitTolerance) - (upperSpectra)))) < 1.0E-6); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Math80
### Patch Diff Hash-SHA-256:

5b6e2d6620526ccca9d25203732864ea569a1caa7fce1e4af86476b6393c9f92

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((main[pingPong]) - (main[tType])) > ((main[tType]) - (main[pingPong])); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Math80
### Patch Diff Hash-SHA-256:

d2ab166c244d209a3358f0f8c8672d575bb58ef30f2ef9d681797cc1a05d84aa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < ((pingPong) - 1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Math80
### Patch Diff Hash-SHA-256:

d31c2640a97935b75fc35f897f77946aab810289eaafea898539015b01fa34c5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (eMin) == 1.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Math80
### Patch Diff Hash-SHA-256:

94e619a902bdd96f2784aaaeff44a4f7c1c7b3369d724d525050cf3b55980072

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Double.isInfinite(dN)) || (java.lang.Double.isInfinite(qMax)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Math80
### Patch Diff Hash-SHA-256:

0875bb47dcca7ee91c7c2fccc5510e789b5f4c0464ea5e621cb9b133a022e18e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) == n; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Math80
### Patch Diff Hash-SHA-256:

398c04fe50aa3355e5578287bb8cae666a7a8f0e73d40342b1d194e5c79b2c8f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) >= 1) && ((squaredSecondary[((pingPong) - 1)]) >= (squaredSecondary[pingPong])); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Math80
### Patch Diff Hash-SHA-256:

2c7d6dfedd5c9ae71be80fb624ffd752351df22552d3cf6aa5f7879a5fb7ab3c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isNaN(dMin1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Math80
### Patch Diff Hash-SHA-256:

04915e78d39a53b1395657dc118ac77446549c8b9825420e2d5d957fc8ec3d8e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(lowerSpectra);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Math80
### Patch Diff Hash-SHA-256:

8c2908fef3c1140a68a7aba1e6adb564447ead6a17f447415859da7bc8a07083

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (step == 1) || (step == ((tType) - 1)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Math80
### Patch Diff Hash-SHA-256:

d25d44447ccdfdf3eac6296460434c1e3186a1e4f1008dab90003966e53f9b91

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((dMin) >= 0.5) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Math80
### Patch Diff Hash-SHA-256:

5fa70b51d9e45aa4cefd7a99693e4403e7d296dd6c6882db22e52b7e3ae404b6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (sigmaLow) == (TOLERANCE_2); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Math80
### Patch Diff Hash-SHA-256:

51e246d34ad6f10e20c4a8fa5f8c8c5fd0ad7dc3d2a1a996c0784a3061c6b415

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((j & 1) == 0) && ((n & 1) == 0)) && ((pingPong) < 31); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Math80
### Patch Diff Hash-SHA-256:

41089db58e600a0b90a4779562dd7c3d9f013789b79cdc890873533a7c9889ce

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isInfinite(g); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Math80
### Patch Diff Hash-SHA-256:

4e5f14520dc250cf26b4e04a44c130c537365e044f4e2603a4b99944306ccb53

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (minPivot) >= (java.lang.Math.abs(((0.5 * (tau)) * (TOLERANCE)))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Math80
### Patch Diff Hash-SHA-256:

bdabd26b5da5e04a0a2657e867c7ecf75d4661d9817c2f545632aee6eb8139f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN1) != 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Math80
### Patch Diff Hash-SHA-256:

ca3909b54bc5eea83418936db01bf57e5252b92ec355e833b61df4acad139c61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Double.isInfinite(g)) || (java.lang.Double.isNaN(g)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Math80
### Patch Diff Hash-SHA-256:

1fb341e616bf566f11589bc4d289e6264ecda53ec193a7781ba5f67998fff155

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((java.lang.Double.isNaN(TOLERANCE_2)) || (java.lang.Double.isNaN(TOLERANCE))) || (java.lang.Double.isNaN(TOLERANCE_2))) || ((TOLERANCE_2) < 0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Math80
### Patch Diff Hash-SHA-256:

2099a422db36cd950c2582fdf95ad4af92edb181b7ef39ad5898f08224dde8f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(upperSpectra);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Math80
### Patch Diff Hash-SHA-256:

964e355ce98e0e4e169ff9d15f0ab9f81d0ea6bf32c81e881088618e935df7f1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Double.isNaN(dN2)) && (java.lang.Double.isNaN(dN)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Math80
### Patch Diff Hash-SHA-256:

17dbdc69cec45bda2bf1f7ef7649c60a01ecba3b8ef7cc6e12d791e4a7896b23

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j == (tType); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Math80
### Patch Diff Hash-SHA-256:

725d3e638de2d7e42a38519e38517e5ef8361696aacdaabeb8c306cc7fe2337a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (TOLERANCE) < (splitTolerance); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Math80
### Patch Diff Hash-SHA-256:

61949efd65060fc12e0cfe68f73299c86df39e5676cd2927b1362ca3cf7c9b58

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(dMin1);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Math80
### Patch Diff Hash-SHA-256:

4fc4b2aae5d3f87f26f376120fbfcb34837ec09aef66969c58a01a9574ce8a8e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(sigmaLow);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Math80
### Patch Diff Hash-SHA-256:

db8da923781d19903daa6937ec317bc76a177d9c5a72aec644cffdf3a8906ccd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Double.isNaN(upperSpectra)) && (java.lang.Double.isNaN(minPivot)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Math80
### Patch Diff Hash-SHA-256:

387d4c4c9ad2678b9a4a0a02dde7d9f74a2728e84ba18ed6821dcf54276f4486

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step <= (tType); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Math80
### Patch Diff Hash-SHA-256:

fb3918487e70392fb37ad4c099a624fea63b5972cff82cdad018a340f544c525

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; org.apache.commons.math.util.MathUtils.equals(tau, TOLERANCE_2, sigmaLow); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Math80
### Patch Diff Hash-SHA-256:

74d9d7d1b4ffa61eb3e032406517a42cecaf3dfb80cd0246ec714bd0f54716d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((((lowerSpectra) == 0) || ((upperSpectra) == 0)) || ((lowerSpectra) == 0)) || ((splitTolerance) == 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Math80
### Patch Diff Hash-SHA-256:

6db473fc9e4fabda61eb4fccec7f868418d97a43db876c09b8edda81e2954991

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) != 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Math80
### Patch Diff Hash-SHA-256:

68493b9477e5381e8471061848a16640f3c722f977d3e1f0574ca683c50a9ee2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((upperSpectra) * ((tau) - (upperSpectra))) >= 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Math80
### Patch Diff Hash-SHA-256:

a3d8ef792a93201ca85da0d218640e2a9afb03963829187c1ca39aa3a23bdd8a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tau) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Math80
### Patch Diff Hash-SHA-256:

3ee1fdb36d3007d0a83e5b53ee6ed65c233044fc7e6b26eea67a58d44bff9894

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (main[step]) == 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Math80
### Patch Diff Hash-SHA-256:

6efa098b8780c12582446557f1fd46fdc078a3e0700b79aa1ff64f1fdab3a1ee

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(sumOffDiag);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Math80
### Patch Diff Hash-SHA-256:

b3bf706a327a1a409aaa6c4d3c7db2a0fb105ecb18bd1ca0d1d40430319a0b0a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(splitTolerance);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Math80
### Patch Diff Hash-SHA-256:

6409cb537f9ed5ab2642327c5636fa9e4ef255519e42a6f48eed5efbdcd40b04

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step < ((pingPong) - 3); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Math80
### Patch Diff Hash-SHA-256:

73e0b42b7614b8809cc6d6df66053a5ced46707beb302649d984f25cfbcfecd1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tau) == 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Math80
### Patch Diff Hash-SHA-256:

8112f72ee8e66a88a2385aa5a1fefb7564f8b107a1809281657a4543f5eedd1f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (lowerSpectra) == 1; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Math80
### Patch Diff Hash-SHA-256:

b4f498dd61c78d951d45ea8d32c3b63cd82a62f33ee4241e1c09af89e59c0393

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (minPivot) >= 1.0E-4; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Math80
### Patch Diff Hash-SHA-256:

97e4100a1473648135245262a8888c7422f8307c071d2c5338ef964a7ef05290

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tau) > ((lowerSpectra) * (lowerSpectra)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Math80
### Patch Diff Hash-SHA-256:

22a6272f4e16855d0b97345b38606d6c590148011c7aa89efa40efa9abc5e11f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(j + 1)])) < (work[(j - 2)]); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Math80
### Patch Diff Hash-SHA-256:

d1d055b0cf974bb7c2f130530e66886a57d1235bce241671fc11e18522ff934a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[j])) < (work[(n + 2)]); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Math80
### Patch Diff Hash-SHA-256:

fcfc895982dbce44c2fcc0571530809b860961930de925702f3cb764df638cbe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) != (step - 2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Math80
### Patch Diff Hash-SHA-256:

84fd858a1101dab9a94d9c561f5da800529843e5b5a70afe246c3c28b51ab668

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((pingPong) != (pingPong)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Math80
### Patch Diff Hash-SHA-256:

4d59ce4e2894a856a744f622b27489bf8077b1d5184196d46a468f0e82679e68

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(dN);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Math80
### Patch Diff Hash-SHA-256:

0daa73e40f0db457a794ac18d5216742156481d41eaa7aa76fedc92deaf50c1e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (sigma) > 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Math80
### Patch Diff Hash-SHA-256:

e50ec0ef3f110a8a21e09f0a460b2231652745ba7b1bc98b027c730c803d56f9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(n + 2)])) < (work[j]); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Math80
### Patch Diff Hash-SHA-256:

e4d9b338e6cec616183c40a429161548c6e8584c4c9ae19bf5bcdf6703688748

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < ((tType) - 1); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Math80
### Patch Diff Hash-SHA-256:

9cc8257686a197c35a60980e648e648ac1ab3d2f88e4fe2f44da1c0a9d30a6de

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step == (lowerSpectra); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Math80
### Patch Diff Hash-SHA-256:

a543d88a3206ddbda78be2c216729e3da7d1b6da58ea2aaebbc93a533ad2013c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((TOLERANCE) < (splitTolerance)) || ((TOLERANCE) < ((TOLERANCE_2) * (java.lang.Math.max(java.lang.Math.abs(TOLERANCE_2), java.lang.Math.abs(splitTolerance))))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Math80
### Patch Diff Hash-SHA-256:

8e2426b43951961f470250f513d6c1d26e49f8f24cfd8f1f215719c8a4d67f61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN) > (eMin); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Math80
### Patch Diff Hash-SHA-256:

a8e757803eb252178607bf710507de682d9ecd95b78380b944b761f75e3e7a53

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step != step; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Math80
### Patch Diff Hash-SHA-256:

0465c540ed00eb5cd6c3cd9e369124c81488291da1c18128de8ac3284ef17d7a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (lowerSpectra) == 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Math80
### Patch Diff Hash-SHA-256:

16fa1031f66f0b899128b8565bb7363b73ec06f9d5ea5e7d2ed1f4871b85d819

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(n + 1)])) < (work[(n - 2)])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(n - 2)])) < (work[(n + 1)])); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Math80
### Patch Diff Hash-SHA-256:

25770864efd20ce0a51c74719c92f55059aa82356e86fb850f14c793cb0e0e43

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) < (4 * (step - 3)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Math80
### Patch Diff Hash-SHA-256:

c38014b14a8c4e207fed4a5a492d7b87c30b0f4addfc83df9423ed1ac2e1895d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (work[((4 * step) - 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Math80
### Patch Diff Hash-SHA-256:

71c2e5f5ca3f97f114d843e0a7b56164c4e312f6225b9c2fbf165d044e5e3dc8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (step < (tType)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Math80
### Patch Diff Hash-SHA-256:

b802c851645a1bf291762831da736e58ee741cbae4971e9d2cb511288ad6f0ca

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n < n; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Math80
### Patch Diff Hash-SHA-256:

e673f19e43f6e4ef10cafbd0054943919218b71ee79d486580ebbaac5e837175

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[j])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[j])) < (work[((pingPong) + 2)])); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Math80
### Patch Diff Hash-SHA-256:

6c41fff7a29735f99dbf4a208922fa44c3a98cb13a06f4bee9315654bb38132e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((TOLERANCE_2) > 0.0) && ((TOLERANCE_2) > (tau)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Math80
### Patch Diff Hash-SHA-256:

0ba062acc7e5e43d75bed1d9850f202d544a04efe19af73e4968cbe0372a6b03

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isInfinite(minPivot);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Math80
### Patch Diff Hash-SHA-256:

87dbe574f3a6e41621daeb413a90cee41d516d53d0098122ae26b2d16093d472

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * j) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1)))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Math80
### Patch Diff Hash-SHA-256:

4674ba8366ab11b858373d3e5b37c1e414d94666e226b11d724cec8071301e1d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) == (-18); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Math80
### Patch Diff Hash-SHA-256:

4dc895ee3819aaf086310c406210c1e6db01b6cf429ffe7f5fecd81802d5af9e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n >= (((4 * j) + 2) + (pingPong)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Math80
### Patch Diff Hash-SHA-256:

1a8a2f974ec56d4221c893254810ada286a18a8828d4c899b3a11637709175aa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) >= (((4 * j) + 2) + (pingPong)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Math80
### Patch Diff Hash-SHA-256:

c194f78181b0a6c0c742ce3ffc7d47ca80e2d8067f6c792fc13d6c6e8a23940d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n <= (tType)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Math80
### Patch Diff Hash-SHA-256:

53f4080f3f3931b750ade33653f41dbb4f0fd05872b4532c03aeb79ab5fd6184

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step <= 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Math80
### Patch Diff Hash-SHA-256:

225d6626ad60245e68107cf46b527fb1a9254c38ecc0892dc39337a9dab365d4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) < (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Math80
### Patch Diff Hash-SHA-256:

36b50b738dd0c9b9960b420f14b897dffee8efbb4f1e91ef32247d54ef6594e1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (transformer) instanceof org.apache.commons.math.linear.RealMatrix; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Math80
### Patch Diff Hash-SHA-256:

a78956441fe3e68d2699ba87bcb920e86d9b8c644564d59bd4b3d278b1c8abed

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((((pingPong) == 0) && (((pingPong) - (pingPong)) > 3)) && ((work[((4 * (pingPong)) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (TOLERANCE_2)))) && ((work[((4 * (pingPong)) - 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Math80
### Patch Diff Hash-SHA-256:

ab67bdd6f9ea41898c704c290094674a0970339bde885d11295becba5b6eedbb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) < 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Math80
### Patch Diff Hash-SHA-256:

03fb5104e75737b6b665fb5563e2e770263992e20cdd619e1f43799a1f2a4cad

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step < (tType); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Math80
### Patch Diff Hash-SHA-256:

57411170cdbc6dbd7610169540d1d102ec995d3cee5617535edfdaee4cd4dcdd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((((pingPong) == 0) && (((pingPong) - n) > 3)) && ((work[((4 * (pingPong)) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (TOLERANCE)))) && ((work[((4 * (pingPong)) - 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Math80
### Patch Diff Hash-SHA-256:

af24712b46ed292919234a8f89cc46d6e9eb72b6031a9faa231ad1a2ae10c220

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (100 * (java.lang.Math.max(minPivot, TOLERANCE))) < (sigma); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Math80
### Patch Diff Hash-SHA-256:

fdad7858cf824c0a16768f1767a035bffbbdd906cfd0fb17a869fb5b3dc66f67

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) == 0) && (((pingPong) - j) > 3); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Math80
### Patch Diff Hash-SHA-256:

593f7964494ddd7ab68913610f4809b062a12c44ce626addb1cfa10e2613ecd8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n < ((4 * step) - 16)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Math80
### Patch Diff Hash-SHA-256:

8ed00062432bb20b8e0a42563fe6361b2c2c7bfec57f99156f9087b0e3621922

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (sigma) > ((TOLERANCE) + (splitTolerance)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Math80
### Patch Diff Hash-SHA-256:

29d19cb1507c4874519196b0ae9c8176f2ec4ff215d85f7d4117034f8d7ba52c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(sigma);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Math80
### Patch Diff Hash-SHA-256:

e810b6a479f13e8ee26ecc569f1b38311c2f328f718f3d3d7396fac48ccd63b1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((pingPong) == 0) && ((step - n) > 3)) && ((work[((4 * step) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (TOLERANCE_2))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Math80
### Patch Diff Hash-SHA-256:

56623de1205aacc12f8018650430856e0277f3fb0d5b79f857807988ead630a4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < n; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Math80
### Patch Diff Hash-SHA-256:

a5bf44b3c9f6b502fa668c06d8c8fe33f926de00d74e7427863685d70e6c8b26

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) > (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Math80
### Patch Diff Hash-SHA-256:

fdc159f028f641ba387be087f79074039866e1050d0230b9746b1e995f3e8599

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) < ((pingPong) + (pingPong)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Math80
### Patch Diff Hash-SHA-256:

21b148953c804c73928cc76019e4feb83c2718075b20cf36a48aa07eb4598e37

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Math80
### Patch Diff Hash-SHA-256:

f78632629450cc3fc2067b7a611283433c7305ecb09da59de4b20a65bfda8bfa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n == (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Math80
### Patch Diff Hash-SHA-256:

ea874fc313f09d8da2df1dc5817d030ecc42ad1eee13c554df8c1dfdc849cb05

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((java.lang.Double.isInfinite(dMin)) || (java.lang.Double.isInfinite(dMin))) || (java.lang.Double.isInfinite(dMin)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Math80
### Patch Diff Hash-SHA-256:

b5e0b2b84cddb0f12c5ac7f6524ba4dc28d1ae9834e1b67e27a678b97eba2fa0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) != 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Math80
### Patch Diff Hash-SHA-256:

0acbb48f1596fe8bca3fd2acdc87ff959a86ca39cdac70542e283149fbb3188f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) < (dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Math80
### Patch Diff Hash-SHA-256:

81d0302b3049ccb14d3eef27251b65990d22d25379d4be7e30735f68a9c4e7a5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) != (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Math80
### Patch Diff Hash-SHA-256:

339b762e3b9b720ec5aa018e7d42725f4151fffac8f69eb86838db7f737b3ceb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tau) < (tau); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Math80
### Patch Diff Hash-SHA-256:

0ae6a54764c7ee50f3060f1458101d8d9bfc94e7c623096f19f609f6844cd163

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Double.isNaN(dMin)) || (java.lang.Double.isNaN(dMin)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Math80
### Patch Diff Hash-SHA-256:

3e73c7a723c44df408cb48d51468225c690b2eec5781fa2c6d27a6e94ed64899

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work[pingPong]) < 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Math80
### Patch Diff Hash-SHA-256:

9480e2f71f8722df5878a2210a6e287e2cb3544e16bb51312d52ab4d39441a0f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) != 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Math80
### Patch Diff Hash-SHA-256:

2206ac557ea926087092bdcd7334dfd0f469b48bd218d1c25865691a7ccdac62

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) > 100; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Math80
### Patch Diff Hash-SHA-256:

a215b3f8e8c474c7de7927d486393c3d0d3a4b1ffbb7ab8317a6049f496ad798

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(dMin)) > (dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Math80
### Patch Diff Hash-SHA-256:

b1c31060e5a1d8734661629956305756bb2c0a48198230f19fd484c1d1b39720

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) + (pingPong)) > (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Math80
### Patch Diff Hash-SHA-256:

33836be01ad57735ba866ff00c3c8d438754a5b56ce020714e27b68b3123fa0c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isInfinite(dMin); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Math80
### Patch Diff Hash-SHA-256:

c3feca856cbe9d0c8f247e42662518507b0d2522181c6ed6bdc40b8f35ad97e4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tau) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Math80
### Patch Diff Hash-SHA-256:

2059f1ebce0a3764fb95edd693ae827e29bc9b627cec36771f1c3eedc23bd94a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) > (dMin); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Math80
### Patch Diff Hash-SHA-256:

72ebdfcb9d14701279eb4ff19cb7e751b7e3cf341a5764846e2537376d2ede4c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) < (dMin); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Math80
### Patch Diff Hash-SHA-256:

f0faf41816880208e6613548464c654e9b2699bba2db7efd13e827d128a070f6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work[pingPong]) <= 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Math80
### Patch Diff Hash-SHA-256:

a1902ca2cdfb555698b14a9ea5249fee281d9a347808ef856855d8e0bafeccc6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; java.lang.Double.isInfinite(dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Math80
### Patch Diff Hash-SHA-256:

2a229947fba2be12644afe51ef070b81f0b6cdb0093bd727cbb5ff939596d97f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((work) != (work)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Math80
### Patch Diff Hash-SHA-256:

285e56e15797eda30d7b893de73cf588fa836f3fd4490eeaa68fbc781f06e6e6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) >= 1.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Math80
### Patch Diff Hash-SHA-256:

3a82dd2ea150044d120ac9e9a97015868978cb4e6356ff2d80c19ececded5b1b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((java.lang.Double.isInfinite(dMin)) || (java.lang.Double.isInfinite(dMin))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Math80
### Patch Diff Hash-SHA-256:

a89edf37a4c3259251ffa941f01b0e0bd4514e4df22a4259b41f619e79766775

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((pingPong) < (pingPong)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Math80
### Patch Diff Hash-SHA-256:

dc85b819517e7de67f4ad27726961dfcbef8e9e9384188c90f2f2fe67c5ea0d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tau) < (tau); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Math80
### Patch Diff Hash-SHA-256:

e98fcaa0969efbb56e6bb8418c4e848d98b5f0771ee44f5d72dff5b69e2dba48

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (++(pingPong)) > (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Math80
### Patch Diff Hash-SHA-256:

481ac675886f9387eae3fca540cc2d1966123eb858cfabf9f939482e1791a044

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((pingPong) == n) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Math80
### Patch Diff Hash-SHA-256:

ce6c47658919dbf38b92715f6df03394b9023cf73245a02fb8223b45f17ef98e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((pingPong) - (pingPong)) > 3) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Math80
### Patch Diff Hash-SHA-256:

70e33bdd2891b5590084d58dbf25842f61c35effc413c9d5275bf496b1252aeb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (work) == null; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Math80
### Patch Diff Hash-SHA-256:

5f5601b8f52cb62cc3b82c8b6d5daf57317bfa028f16e5413a940128a6c7dd9e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) >= 1; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Math80
### Patch Diff Hash-SHA-256:

915b9fc37afce043223c4cf1b0af4de0d8e0dc567592596a8845c667b8df557f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((dMin) < (dMin)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Math80
### Patch Diff Hash-SHA-256:

0b587e2b45a76fabbeecd5763391c1bde78b9863284632a5cc350b2600cd6a57

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) > 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Math80
### Patch Diff Hash-SHA-256:

3506e1394affadb5a201528a001f40679f3881e51403d5cd48fd603625f5a1e8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(dMin)) < (dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Math80
### Patch Diff Hash-SHA-256:

55ec52f5bc97c85d31a9cc782a722b138bedc10af36bd2fbbe11cfd41b3844ec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) == (pingPong)) && ((pingPong) > 1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Math80
### Patch Diff Hash-SHA-256:

5823f9b0303252fad4129486eea272138965a96a68c429cb666d867ebcd79d9c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) >= (pingPong)) && ((pingPong) > 0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Math80
### Patch Diff Hash-SHA-256:

958c2bff98efaccb542e4cd9f1a5866fb783d1760c0d5e68a01415f8f69b4edd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.floor(dMin)) < (dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Math80
### Patch Diff Hash-SHA-256:

8d4bb74229c29aea66672777ae4617eae4c687072da4055e609f889e9d2c849e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j <= (pingPong); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Math80
### Patch Diff Hash-SHA-256:

d56ecaacf52c19bce20925236a0757d952844cce2c9a64accbb1cf6cd8701f65

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((dMin) < (dMin)) || (java.lang.Double.isNaN(dMin))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Math80
### Patch Diff Hash-SHA-256:

c0a79c7b3769921c3319e9eba906022d9fbdcc796e1555845a599796bf9005a7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) < (-(dMin)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Math80
### Patch Diff Hash-SHA-256:

75f524960afad231e88b5a428e740a057149cd52134a90ef3917bcdc7f178026

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((pingPong) == (java.lang.Integer.MIN_VALUE)) && (((pingPong) & 1) == 0); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Math80
### Patch Diff Hash-SHA-256:

45912b5d74b4c5508a5351fa40e0dbd7b482c45e0bd8891596a02516a609ce87

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) < (-(dMin)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Math80
### Patch Diff Hash-SHA-256:

3b7ae557361cb4701381c6a63e7e03f0b1b79b16a58f88154d1aa52b5d920637

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((pingPong) > 1) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Math80
### Patch Diff Hash-SHA-256:

7f886a05b29d5e9f069c0e2473f5352ef2cc9e966f03089ffd82530b3cfd4dbd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) > 1.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Math80
### Patch Diff Hash-SHA-256:

1f0fc6982af3a9d4bf68bbb10b1a2fe59eadadba7170b30feca57a6ceef783c5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((sigma) * (sigma)) > 0.0) && ((pingPong) < (pingPong)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Math80
### Patch Diff Hash-SHA-256:

75dee17b9c50f0ae14575bce1e406a53be7000be52ae4f3f58c9fc02f111bba5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) != 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Math80
### Patch Diff Hash-SHA-256:

5d5e743a273e3c44c437493410f3dd46e1eb4a636d2bff93c7a481019903e656

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; step < step; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Math80
### Patch Diff Hash-SHA-256:

b3dcff57a7ce7f63bd3053cfc04aaa77813ac5a3fc5fd631d6252fc036fd45e5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (java.lang.Double.isInfinite(dMin)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Math80
### Patch Diff Hash-SHA-256:

1b3d8dc66a2aeb54afbbfa76aef35999f08f599e3fe4c69af0b6bf9b455eb951

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) > 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Math80
### Patch Diff Hash-SHA-256:

ae13edfa748660089999a57562a977f3c30a3a6c17223b8a8cbfbd406b87d683

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(((dMin) - (dMin)))) > (dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Math80
### Patch Diff Hash-SHA-256:

56ef6ae152c27d9ca87567af4b6ec33cd85ffa5bb2b549f0844cb52976880310

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(tau);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Math80
### Patch Diff Hash-SHA-256:

379199c0b38564f72b811d227345ee14f7ec3d1ce0ef1ce57a14593998540a19

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.abs(dMin)) < (dMin); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Math80
### Patch Diff Hash-SHA-256:

7b9b598a404803be38d40e6cfeccf31ef52d2ac067d508d6907cf562e23b9305

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j < (n); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Math80
### Patch Diff Hash-SHA-256:

446481fb44c6d7293efaec9903b6e8a0efcc4c89c91bf9f37fe8cfe8a80b4822

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((work[pingPong]) - (work[pingPong])) > ((work[pingPong]) - (work[pingPong])); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Math80
### Patch Diff Hash-SHA-256:

7f08aedbab14f85e667e466a69cdf46ed0c35a11202f853a846fc79386cd8cde

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((100 * (java.lang.Math.max(dMin, dMin))) < (dMin)) || ((dMin) < (dMin)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Math80
### Patch Diff Hash-SHA-256:

4b40d0422f554d7974b3eafce50ae056ab6692bb9a47126e961f74930dcebab7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((dMin) >= 0.75) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Math80
### Patch Diff Hash-SHA-256:

19f91ff0d5e9fa7ff90912037b548e02c92451e914d2759eb2e3683dc417a740

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) > 32; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Math80
### Patch Diff Hash-SHA-256:

96ff72c652fe7f41a34404157d9c49a747069f6f898154d029b724ea1a113e31

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; java.lang.Double.isInfinite(tau); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Math80
### Patch Diff Hash-SHA-256:

dc5b193f29a81a82b0ae0e6662853beec98ef235385bc8579c084285cca97d64

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((dMin) > 0) && ((dMin) < 0)) || (((dMin) < 0) && ((dMin) > 0)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Math80
### Patch Diff Hash-SHA-256:

af86aea4dc8287b99763f98b0a4106db3dc59a63951423cc87d2b908789ab132

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) == (java.lang.Integer.MAX_VALUE); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Math80
### Patch Diff Hash-SHA-256:

d3f3a679fb312cf049685831a0e58c1eec78ea33565df07320bf62b2a09c7af9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) < ((pingPong) - 1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Math80
### Patch Diff Hash-SHA-256:

2ec395bf80dfa051bf85aeb5929ff76dc708576ffd5bd233f88b4d5827b9abd2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n < 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Math80
### Patch Diff Hash-SHA-256:

7aef7cbf98f7f935b095eb87ae9ff6e354898c3fe2df245b521da1a8e57c1b69

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tau) == 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Math80
### Patch Diff Hash-SHA-256:

67ebd1baa5989ad64414946110a215355509f783bff78284cb11d990e39abaae

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(((dMin) - (dMin)))) > ((dMin) - (0.5 * ((dMin) - (dMin)))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Math80
### Patch Diff Hash-SHA-256:

ca995880be5227ede62969396f222e41999f494dfb4845078b0410b663238b22

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tau) > (tau); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Math80
### Patch Diff Hash-SHA-256:

3afc4f11fa98292eceffc91fd9c84d9f8ef5c2d95d1e3b1408a14dc99f5cc8e9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) > 0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Math80
### Patch Diff Hash-SHA-256:

474139ad12060f7bb1acdee027babf08684b8c7c7d63efbce4faac7dda8791b4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (work[pingPong]) < 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Math80
### Patch Diff Hash-SHA-256:

545f67c59420bd6cbc0b402a92fce6895ce2e35bea8ab40ac93df25dff7f23a6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (n == j) || (j == 0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Math80
### Patch Diff Hash-SHA-256:

12b51d70e4cd76c9f7cb3da02b1fbb7fb4197ca99641152294a2d404b1977693

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(TOLERANCE_2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Math80
### Patch Diff Hash-SHA-256:

ca95ef80ecfa3c3e4958d774312056e8f2a3f5ef0c5dd6c3059a3b84ad4acae6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (countEigenValues(TOLERANCE_2, pingPong, n)) >= 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Math80
### Patch Diff Hash-SHA-256:

6b1eeda5ad6d4f56b17da3008e3af877a233fb189bdde4e9b5db3c20c9afd64c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Math80
### Patch Diff Hash-SHA-256:

55df60ec379c1c7ea1606393c78a9d39ceb5312e9b74c1816cfe0c2908dfaba2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN1) < (dN1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Math80
### Patch Diff Hash-SHA-256:

1ecc1db7997fb85313f384402e3fe91ca315ad1f3fe4f0419930f311d0633db9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((tType) + 2)])) < (work[j]); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 455 of bug id Math80
### Patch Diff Hash-SHA-256:

c771f41ed0f95b8b8de70a23e48217adada1c63e9f4f7bf442c1dbd23c0b191c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) == (-18); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 456 of bug id Math80
### Patch Diff Hash-SHA-256:

ca5433868d70f910f82d02cbfb54b3d95d4756bb1d607ed4ee4f4ccb3412bc6a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (realEigenvalues) == null; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 457 of bug id Math80
### Patch Diff Hash-SHA-256:

e4eda4ef5aacfb2545cb5bd211ebeeb2be0cc9b5a4ac9757347ca9f67888a1ac

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (step - n) > 3; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 458 of bug id Math80
### Patch Diff Hash-SHA-256:

cb37a1abbef9a8ee51fa070e480a164304aaca1fd0c67664fd5f06fb79f1ba41

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * j) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) && ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 459 of bug id Math80
### Patch Diff Hash-SHA-256:

03198a6de39c6175c5dd4ca90045ae14bceb706d286f6975c16c0e277fb72788

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step == n; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 460 of bug id Math80
### Patch Diff Hash-SHA-256:

34302a0769e8eae1e71feb04bb1fbb5ae28956ef7fd5c5c135e76bae383afb6e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (lowerSpectra) == 0.0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 461 of bug id Math80
### Patch Diff Hash-SHA-256:

a05a5a78be8255f5dc3fb6de23cbf3f3821cc2bf190f8ecd294f8faf793c506a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; j > j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 462 of bug id Math80
### Patch Diff Hash-SHA-256:

0bdcb4511ae7fb86363e2217810c8bed6898cd56c86ef0150add4314f572ff46

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) > j; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 463 of bug id Math80
### Patch Diff Hash-SHA-256:

6654483987d516782b24e600868295ee58eb98764c09f93546c3b6a022e990df

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((pingPong) == 0) && ((step - (tType)) > 3)) && ((work[((4 * step) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (TOLERANCE_2))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 464 of bug id Math80
### Patch Diff Hash-SHA-256:

6e987416505bf356002c40889b391ca346e0b322a002af4dd4f52b83afc4b36c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j == n; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 465 of bug id Math80
### Patch Diff Hash-SHA-256:

d1a1b888eb62cb31470f84955fc6c62664c9ecc9c0bf91d8c033d7baec9737c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((tType) + 2)])) < (work[(j - 2)])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(j - 2)])) < (work[((tType) + 2)])); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 466 of bug id Math80
### Patch Diff Hash-SHA-256:

ed7c4aff111c07ca8e9af554eb36183f12eada49fddbcbb1dd990b189a7744a0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(n - 3)])) < (work[(n + 2)]); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 467 of bug id Math80
### Patch Diff Hash-SHA-256:

ecd4754bbdb74de9788dc8521fe8365f82c0cf7ca4fdcaecf7636c078b101d6a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (g) > (eMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 468 of bug id Math80
### Patch Diff Hash-SHA-256:

890c6f3d9ccb5a62155e5c4af0daf07e297cd3ceffac871ad983dc1c7c720f81

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j > j; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 469 of bug id Math80
### Patch Diff Hash-SHA-256:

c65260a82f1db0ab27661df4e3640dd23cf639a7376a3be139f19dbfebdfc136

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[j]); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 470 of bug id Math80
### Patch Diff Hash-SHA-256:

812df6b5f0fb63487f403b8799e7b14ebce52bf21ff402eb93a46ca81461c8f6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; n != n; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 471 of bug id Math80
### Patch Diff Hash-SHA-256:

53182acb70421d631a4da81e21b86a09a9b60094624b8cb888ea383491e3e19b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work[((pingPong) + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 472 of bug id Math80
### Patch Diff Hash-SHA-256:

6d583cc5c990d27485fcb1ed8ba22b6cfe8d3fbc9c7e6498e6819bb2b972abe4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (work[(j - 9)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 473 of bug id Math80
### Patch Diff Hash-SHA-256:

d1b32b3970ce1e0d6df4425372f23f4975f5e6c4d8290ec25a1c6e024b2a6e5a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n < (pingPong)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 474 of bug id Math80
### Patch Diff Hash-SHA-256:

a6da6c2c30667045af311029a332db16743ae23a9ec1dbecdf331be79c6f803e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (work[((pingPong) + 2)]) <= 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 475 of bug id Math80
### Patch Diff Hash-SHA-256:

39b963fc63fd1a4f5dd63995b45710db28edd064f8beb27db8b9c6de83f5a241

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.lang.Double.isNaN(TOLERANCE);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 476 of bug id Math80
### Patch Diff Hash-SHA-256:

ddec1aad50b4a176190e29372c3d0aaa8cbf97b908d20a0e2e68154c796e44e0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (((pingPong) == 0) && (((tType) - step) > 3)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 477 of bug id Math80
### Patch Diff Hash-SHA-256:

c727e1a244c178d8a05a1e0140d0c59f565ed604197378faf266051a86d83ccd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (transformer) instanceof org.apache.commons.math.linear.RealMatrix; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 478 of bug id Math80
### Patch Diff Hash-SHA-256:

0364e6f4cb57f2871850ea31b416f8da2fa20a42814f26a1ebfba302e457b512

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * (tType)) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) && ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 479 of bug id Math80
### Patch Diff Hash-SHA-256:

abbd1def422c3ebedc673039c0aaf3382af1a48ca14ec19a4436da59594afa51

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (TOLERANCE) < ((TOLERANCE_2) * (java.lang.Math.max(java.lang.Math.abs(lowerSpectra), java.lang.Math.abs(TOLERANCE_2)))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 480 of bug id Math80
### Patch Diff Hash-SHA-256:

74325bb86fea2317e6a951a812a9ee68369ba860dc70c6e221912ce6338305d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (n < step) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 481 of bug id Math80
### Patch Diff Hash-SHA-256:

01a69359e56b8bcc749f86339392b7648c57133fdc7d59f0577c9885a55f6b8b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) > (tType); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 482 of bug id Math80
### Patch Diff Hash-SHA-256:

6c87b457130303db7ad3cc3afd4df71615f4beba5b3d56ec41b7ed828194b495

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) < (dMin2); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 483 of bug id Math80
### Patch Diff Hash-SHA-256:

c9407e660081f3a75cff5e48827ba13a86fd37d2600e3beb38244f6a83f9ac56

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (step < (pingPong)) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 484 of bug id Math80
### Patch Diff Hash-SHA-256:

07aee2c6ab65bf0f441a800bb1ca102fd51a00bd036342cfef11790a319066a9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(secondary[pingPong])) <= (dN); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 485 of bug id Math80
### Patch Diff Hash-SHA-256:

9002ee7a93b962a10c8107b6865b0d203685a03246d93a065fd60687d888618e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) != (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 486 of bug id Math80
### Patch Diff Hash-SHA-256:

b9fd4e3d0bb04d68b377b8a17153ea6d07fba13ce25fa0b1750858d592e3504b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (cachedV) instanceof org.apache.commons.math.linear.RealMatrix; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 487 of bug id Math80
### Patch Diff Hash-SHA-256:

69ea52541ef27cdc0a95bcbec8689d4c0e1f85ee78784fa89fdbdd2fbe657284

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (minPivot) < (dN); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 488 of bug id Math80
### Patch Diff Hash-SHA-256:

344615efd3f3e87ca6eef81af7d6490b1467f4cc488ab45f3fc963452dac4028

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j <= (tType); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 489 of bug id Math80
### Patch Diff Hash-SHA-256:

6e43d5b0409a75ad20e3acbf69c6a32738188c13f076792841d1749944c87462

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[j])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[j])) < (work[((pingPong) + 2)])); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 490 of bug id Math80
### Patch Diff Hash-SHA-256:

676ccd6e72d36d59af17aee94939125fb68ab6bcbbdfc6701dc659473125fe3e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (sigma) < (eMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 491 of bug id Math80
### Patch Diff Hash-SHA-256:

aa39caf0ee93e8d5908c57fc9b20a6e0a2a97e46a73a5f63aa1e188ab64cb9bf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dN) < (lowerSpectra); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 492 of bug id Math80
### Patch Diff Hash-SHA-256:

863dc93321136ad147458995c33277308e04628c46a37b532d5d178f8d3a580a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (TOLERANCE_2) < (lowerSpectra); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 493 of bug id Math80
### Patch Diff Hash-SHA-256:

efb1e356d451237b6fed880449f7071e60eae76022da88395e37eaee9a5313ae

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((tType) - j) > 3; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 494 of bug id Math80
### Patch Diff Hash-SHA-256:

05da883d689398e6f0c6a977d212b375abec81a02f7c088d95d9ac4add1ae81e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step == (qMax); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 495 of bug id Math80
### Patch Diff Hash-SHA-256:

eccfc0532017040b70b305791db2a389b13f36f7d3b05d96a52acc10fda1f5d1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(secondary[tType])) <= (sigma); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 496 of bug id Math80
### Patch Diff Hash-SHA-256:

577ab5b27fe7e9f3bc7a3f2742055769c96345335a904d0c9fe266514a8a8d4d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n == 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 497 of bug id Math80
### Patch Diff Hash-SHA-256:

6468fdb9db22671520fb8eba899055fc38cceb52a927573f59dd0839b37e44f3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if (step <= (4 * ((pingPong) - 3))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 498 of bug id Math80
### Patch Diff Hash-SHA-256:

c945738893e835af210d5c5e4682016931714fa0c4a59a8d9e298312068d23e7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * (pingPong)) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) && ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 499 of bug id Math80
### Patch Diff Hash-SHA-256:

2fa3941181e8d3f514e55e80e3bcc4ea9fbef0e73ad334b2fae84b9c073c3043

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; step <= (pingPong); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 500 of bug id Math80
### Patch Diff Hash-SHA-256:

c1f7e737a6466e3c55b0783bedfe4faf261a50bebc3130c4c0cdc98a516c05f0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; n == (n - 2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 501 of bug id Math80
### Patch Diff Hash-SHA-256:

9339b9d34eaa4ff2483c6046c920ca20c77e6042355de5102c20da2f02dc1291

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin1) < (sigmaLow); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 502 of bug id Math80
### Patch Diff Hash-SHA-256:

ebff698707cf250ba518c60dabdeaf2d5cd5a313db91ed95499a33df1f8484e9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; j < (n - 1); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 503 of bug id Math80
### Patch Diff Hash-SHA-256:

ae1043d3bff58586f6dd28d227f0d5724780c14174c95965cae6f4a1b66959c9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (work[((tType) + 2)]) <= 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 504 of bug id Math80
### Patch Diff Hash-SHA-256:

36bece358af5c8b62ec759b39321d1e9a643e4e2c3f12e0e265b52bfda7b525a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (tType) < (-22); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 505 of bug id Math80
### Patch Diff Hash-SHA-256:

1390365bc6e2e2b3724b86860d1e05278a63f616a80579100db28764c077f981

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (sigma) > ((sigmaLow) + (sigmaLow)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 506 of bug id Math80
### Patch Diff Hash-SHA-256:

151e9db325a6a571acbc7bec1c4d068bfdab18e7f43e2dabd2380e10369e7d2c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tType) == (-6); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 507 of bug id Math80
### Patch Diff Hash-SHA-256:

cdc3ba62c19b05170687f1e1c403bbcaa4f91a820dbf81da6c0d11b4fd8d1271

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dN1) < (qMax); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 508 of bug id Math80
### Patch Diff Hash-SHA-256:

88784714ba0f129519cb8132b1b47d573c485f47044e6ec4979be881f1ef3b18

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) == j; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 509 of bug id Math80
### Patch Diff Hash-SHA-256:

6734231246d63faebe35fadd4cff173d853c2a904520b3c60670790a03fcf9dd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 510 of bug id Math80
### Patch Diff Hash-SHA-256:

e46c8b02390ff89ade3259c49b9bd698f947347cfeed0af38be7a99200b7ee7e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work[step]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (minPivot)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 511 of bug id Math80
### Patch Diff Hash-SHA-256:

b080f5ac9d980b8b9e76108a5f05eaea6ed9ea3e88fba127aef61ca3586b7489

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (((pingPong) - (2 * (pingPong))) - 4) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 512 of bug id Math80
### Patch Diff Hash-SHA-256:

d4210a22fddacb594f5fc315345502bb3ee4e671c8b2f7bab75cc2c24f96b4c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = ((pingPong) * 31) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 513 of bug id Math80
### Patch Diff Hash-SHA-256:

50d666ca09c268598c9f184a5ae278ab29e903df0bf2bd3c2fa375dcc5046603

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (((4 * (pingPong)) - 9) + (pingPong)) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 514 of bug id Math80
### Patch Diff Hash-SHA-256:

b80a07e8ce1d8c2b9424c2dece2c2a57bf5299d62ef0712b77b05ee7fde16dad

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = 30 * ((pingPong) - (pingPong));
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
@@ -704,7 +704,7 @@
 		final double margin = 2 * (((tNorm * (org.apache.commons.math.util.MathUtils.EPSILON)) * n) + (2 * (minPivot)));
 		double left = lower - margin;
 		double right = upper + margin;
-		for (int i = 0; i < maxIter; ++i) {
+		for (int i = 0; i < maxIter;) {
 			final double range = right - left;
 			if ((range < absoluteTolerance) || (range < (relativeTolerance * (java.lang.Math.max(java.lang.Math.abs(left), java.lang.Math.abs(right)))))) {
 				break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 515 of bug id Math80
### Patch Diff Hash-SHA-256:

0bd566f2b9d88a6c53ca0683bddd1ceea376ebaaeabf5c96280659456da77c64

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = ((pingPong) - (2 * (pingPong))) - 4;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 516 of bug id Math80
### Patch Diff Hash-SHA-256:

d81031b9d2c41cc5b4dd30093a747cad1e4a4e270a31adb9d51048393fa8aa20

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((1.5 * (work[pingPong])) < (work[((pingPong) - (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 517 of bug id Math80
### Patch Diff Hash-SHA-256:

7ae029f16e38c47248aee71584507fe6331f94d799d860150056413c3dea2eaa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) > 0.0; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 518 of bug id Math80
### Patch Diff Hash-SHA-256:

59441e7b95829547094f531609a8a635f294511f3828e0c3e0d3171a61713621

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 519 of bug id Math80
### Patch Diff Hash-SHA-256:

1d895268e5ca31acb7a42ee47ae431b38437dcb22d02cadd67420f38821286bc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (countEigenValues(sigma, pingPong, pingPong)) >= 1; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 520 of bug id Math80
### Patch Diff Hash-SHA-256:

4df61965c15e3050c4099c0c58c45f73cb0ce599ff15ed52a67c083c18c33be7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = 2 + ((int) (((java.lang.Math.log(((dMin) + (dMin)))) - (java.lang.Math.log(dMin))) / (java.lang.Math.log(2.0))));
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 521 of bug id Math80
### Patch Diff Hash-SHA-256:

f6730d7a4562c87c75edfef38e22249684d2c5539537ea5b506ee4dc4431b475

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (100 * (java.lang.Math.max(dMin, dMin))) < (dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 522 of bug id Math80
### Patch Diff Hash-SHA-256:

ff39d619df5fcb2d81cdd223aa80d788edbd0b1173b1644d239e1780ceedbc38

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) > ((dMin) * (dMin)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 523 of bug id Math80
### Patch Diff Hash-SHA-256:

06f31e2414d83fe812c68744cf6140130c2adc16ee4395df51e77e09f05dcc12

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) / 4;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 524 of bug id Math80
### Patch Diff Hash-SHA-256:

d87c05e402dfb2e9ed1c3856d65736476cea52c1153fbbb9ae650ad7df3b6d01

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((dMin) > 0.0) && ((dMin) > ((dMin) * (dMin))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 525 of bug id Math80
### Patch Diff Hash-SHA-256:

41eb3438312fb9a1a6f48ef45bd7a6b6b11be0752f8fa9b403836c8a03f89169

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (((pingPong) == 0) && (((pingPong) - (pingPong)) > 3)) && ((work[((4 * (pingPong)) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (dMin))); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 526 of bug id Math80
### Patch Diff Hash-SHA-256:

c4facc06f9bc3165da0eb2ed9e473852ddaa1da3ad76ddc9c0e6562d8b36fb4c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) - 11;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 527 of bug id Math80
### Patch Diff Hash-SHA-256:

b0fe85ed4f88092d2620e99701bd4c10d70c5eaa1cfbcd9cab0d0d16f021eac7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) - 3;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 528 of bug id Math80
### Patch Diff Hash-SHA-256:

fb2a42925734bd33b8e421e39cef43e648f68a974c6a0245b96c1b468b1dee7b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) >= (((4 * (pingPong)) + 2) + (pingPong)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 529 of bug id Math80
### Patch Diff Hash-SHA-256:

6a97cfb6919dd6b3f059d2180063b579d623aeb26f07cc0acb9c4e22214763a0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((1.5 * (work[pingPong])) < (work[0])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 530 of bug id Math80
### Patch Diff Hash-SHA-256:

0839a291728d88ee23353e1763bcb89296a841f0af6c43783929e7e7b8b775d8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (4 * ((pingPong) - 2)) + (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 531 of bug id Math80
### Patch Diff Hash-SHA-256:

ed1aa020ca73f330095fb49566291d0fee36327969dafbbb1940ccaa8138f275

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (4 * (pingPong)) + 2;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 532 of bug id Math80
### Patch Diff Hash-SHA-256:

0cf2b65e8e0b4dcc9bd0f84ae96a0b7969dba7a64682a53437aee205ecc9d8f8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) - 6;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 533 of bug id Math80
### Patch Diff Hash-SHA-256:

72df35683962d0ce5b3775fe0f4bb7011218da4e767997c81d02c63458bc98ca

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) + (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 534 of bug id Math80
### Patch Diff Hash-SHA-256:

3537068cc5ecf6d2fb27782bd11e6e0afffab3c58a6990e02ca582ccbf6d9407

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((pingPong) == 0) && (((pingPong) - (pingPong)) > 3); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 535 of bug id Math80
### Patch Diff Hash-SHA-256:

826c3d58df605e067d4055b2c52fbd38efd73f98070d4443c6b8c6a0073ba375

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < ((4 * (pingPong)) - 16); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 536 of bug id Math80
### Patch Diff Hash-SHA-256:

33e42c14ca57f636b4c18261d965df623aa1faf47c3267a48739e3635b4196ec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[((pingPong) + 5)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 537 of bug id Math80
### Patch Diff Hash-SHA-256:

dccd8968294cf2fc15f97662ced968c28149d04ff6bc9e589fb684c7a655e13f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[((pingPong) + 1)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 538 of bug id Math80
### Patch Diff Hash-SHA-256:

de5885d06914d9af3ee320210ac34438462df2c7a85c1584aeff77d52f482e3e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) == 0) && (((pingPong) - (pingPong)) > 3); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 539 of bug id Math80
### Patch Diff Hash-SHA-256:

17b40e64888557b4c6c307a0edbd9c550fbdb49e018a61423bd716a778be454b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < (4 * ((pingPong) - 3)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 540 of bug id Math80
### Patch Diff Hash-SHA-256:

2f997bb6bf630302e6c6c50ae6d171c435b629ca33025d513ee44296d3ddb4c8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (4 * ((pingPong) - 1)) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 541 of bug id Math80
### Patch Diff Hash-SHA-256:

580f27e3350dd5b26a0553eddb619da949caca68a6141311cba46c0198281b9a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[((pingPong) + 9)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 542 of bug id Math80
### Patch Diff Hash-SHA-256:

8b89e8f79654921391de4f58973c0c6a4f764aa7de0d33fa21304646d9e254db

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) < ((4 * (pingPong)) - 2); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 543 of bug id Math80
### Patch Diff Hash-SHA-256:

c6a89a7391c0b913c93b071c2e9976bda533597c6dea1cd58319bd63fbe6362d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = 5 * (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 544 of bug id Math80
### Patch Diff Hash-SHA-256:

8b3a613cedb1863806c93dbb79ee7b0b5642f602ec579daec6410e9e5f0eb137

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (10 * (pingPong)) * (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 545 of bug id Math80
### Patch Diff Hash-SHA-256:

2623d772b387b44478297e1f7ed75ba3b739cbe40c7a9ac581014f0b4d2224b0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[j] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 546 of bug id Math80
### Patch Diff Hash-SHA-256:

9aec52e8a2d68eedf33f7044df6577bf8c704c749b4c56c905c86540471dd2bf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) > (dMin); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 547 of bug id Math80
### Patch Diff Hash-SHA-256:

c869a95df888c5cbae03a1aaeda2e2c682bb61f12850dffaee21f99179b4ab88

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((pingPong) - (pingPong)) > 3; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 548 of bug id Math80
### Patch Diff Hash-SHA-256:

6fa4a5d3d24b7d347e2b703ccde19a79fa46dfda5f6e72b8fca77da9474d444d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (j == 0) && ((j - j) > 3); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 549 of bug id Math80
### Patch Diff Hash-SHA-256:

eeaacffcc8d22617f30f247ca2a7b7311eaa350b1bdf4b73ce7d5a1b379409b5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((pingPong) - (pingPong)) > 3; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 550 of bug id Math80
### Patch Diff Hash-SHA-256:

92100afff3675cf97703146a814af6eac36fd91297d48d9ba7618e664f9d5cf5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((pingPong) - 1) >= ((pingPong) - (pingPong)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 551 of bug id Math80
### Patch Diff Hash-SHA-256:

b9b140b7617e8a3286ee1caa68d620c6f567bbaef203f2f51f3ee6ac168a70c1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) - 9;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 552 of bug id Math80
### Patch Diff Hash-SHA-256:

cd644b1bf44040db6550f22628be5e8fde080bf02b1c21c20189c081144a8ed9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) * (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 553 of bug id Math80
### Patch Diff Hash-SHA-256:

1f21ac68bf58cf346c42001e29014c2dba42e08168da7c95c34f47b49e104a20

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; ((100 * (java.lang.Math.max(dMin, dMin))) < (dMin)) || ((dMin) < (dMin)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 554 of bug id Math80
### Patch Diff Hash-SHA-256:

b5ff82a88cfb43a7c5aa0e2f218fd915939b568577b544d64bda382c048901cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = 30 * ((pingPong) - (pingPong));
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 555 of bug id Math80
### Patch Diff Hash-SHA-256:

1b07b47783a71f03e527032c642ba963b83cc22f33ba7faef29199b48cf32afe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < (-22); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 556 of bug id Math80
### Patch Diff Hash-SHA-256:

f4f001a565c7682c5bfad2847fbc6dbfc742d44ae7ca6e1130b3c5e80091b458

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (4 * ((pingPong) - 1)) + (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 557 of bug id Math80
### Patch Diff Hash-SHA-256:

301a15fae85f34fb5119c604d788631c7043ef7786c46ce49a8d5f9ce4514abb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((dMin) < (dMin)) || ((dMin) < ((dMin) * (java.lang.Math.max(java.lang.Math.abs(dMin), java.lang.Math.abs(dMin))))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 558 of bug id Math80
### Patch Diff Hash-SHA-256:

71f6cfc81b9d7729e3ffbbc1c016a9c4309ccf73d374ac2c7df5759a07c09a1d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((dMin) > 0.0) && ((dMin) > (dMin)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 559 of bug id Math80
### Patch Diff Hash-SHA-256:

7ebcead33144dc00a7444b1a4a4108484c3b37cca0211532c56c0a7694289820

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((dMin) < 0.0) && ((dMin) > 0.0); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 560 of bug id Math80
### Patch Diff Hash-SHA-256:

4cdbbbbde13a3422e773ae18923ebf09f9b3f4e5745ee4d86152672b3e6d83c3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = ((4 * (pingPong)) + 3) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 561 of bug id Math80
### Patch Diff Hash-SHA-256:

b9fee9cb0759ffe2e886e894596f3ea9f7b6e48a6cd463e4369362e2ffb60a58

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[((11 * ((pingPong) + 1)) + (17 * ((pingPong) + 1)))] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 562 of bug id Math80
### Patch Diff Hash-SHA-256:

e0b3fa8aeeb51ad09afc11ab43b2c37ada0c5f73c73bce333fc804da5d93ce05

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (((dMin) < 0.0) && ((dMin) > 0.0)) && ((work[(((4 * j) - 5) - j)]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((dMin) + (dMin)))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 563 of bug id Math80
### Patch Diff Hash-SHA-256:

d361fda08ce05bfdf989b86bb888c82467142fd0577f4e5a50bc07257b074b4e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = ((4 * (pingPong)) - 4) + (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 564 of bug id Math80
### Patch Diff Hash-SHA-256:

0dc4b7e2ed2c5ba02328fe462a4e721bfb0d6c2ef51c2b4898874922290f2792

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((1.5 * (work[pingPong])) < (work[((pingPong) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 565 of bug id Math80
### Patch Diff Hash-SHA-256:

2377f62bf7e14ac8578427d367b6a884eab17b700168260a38f179a5e5ba6852

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; ((dMin) > 0.0) && ((dMin) > ((dMin) * (dMin))); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 566 of bug id Math80
### Patch Diff Hash-SHA-256:

d6b186cc622207287cbfba6aee11585d7b8edde2a0f46fab4d2274583402206f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((dMin) < ((dMin) * (java.lang.Math.max(java.lang.Math.abs(dMin), java.lang.Math.abs(dMin))))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 567 of bug id Math80
### Patch Diff Hash-SHA-256:

beb6553a539308566e2c1e031bba5c4067a93e1952554700661aea47f6dcc777

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (pingPong) - 4;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 568 of bug id Math80
### Patch Diff Hash-SHA-256:

45240121b75ee87b9bb7757e8cbeac1852f8e1af018b509148cd9dc28704c326

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[((6 * (pingPong)) + 1)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 569 of bug id Math80
### Patch Diff Hash-SHA-256:

6a9978bb68caad8340f32f894d83d674fae335b2c3e20e01e117418532349af3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = ((4 * (pingPong)) + 2) + (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 570 of bug id Math80
### Patch Diff Hash-SHA-256:

fc7d35ed4c40842b0c35237e9f61a8d88e43d1ddbad93b8acb6e856c7c3369f9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = 4 * (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 571 of bug id Math80
### Patch Diff Hash-SHA-256:

dfde57b66fd375ff63cf99b5a4ad5cbb5caea217f970b092fc9490f0d3ccb606

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((work[pingPong]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 572 of bug id Math80
### Patch Diff Hash-SHA-256:

9e87a0ad3c25afc7de676093888a7a1ffd7d0462c2bdd9e66d17898318b88b1e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (pingPong) < ((4 * (pingPong)) - 16); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 573 of bug id Math80
### Patch Diff Hash-SHA-256:

c4dd05266d2de4cefafca121ed6231d9543c81cae76926777bbd72d46902692a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (dMin) > ((dMin) + (dMin)); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 574 of bug id Math80
### Patch Diff Hash-SHA-256:

4df478b4891f1907f2dbb42d59b3ab4475c10199958fdadc3dcb800b7181e8e1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[(j + 2)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 575 of bug id Math80
### Patch Diff Hash-SHA-256:

0abfda664dbe9425244fd5947762a32ddd6a9a4f60c654b9f16b811ff60ace72

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (tau) <= 0; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 576 of bug id Math80
### Patch Diff Hash-SHA-256:

b86c58916231c3b894419e7663f394642fb756975c47b81e230ade5551a9434f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (work) == null; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 577 of bug id Math80
### Patch Diff Hash-SHA-256:

b2a923f77dff43dcee4dbc32cc349c36a747477f5faed676e9d1763d02a0c91c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,7 +673,7 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
+		if ((work[((pingPong) + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 578 of bug id Math80
### Patch Diff Hash-SHA-256:

300c7f0ca23220c1e4e902d01c0f61bb046fc21877ef8db07e4005400511a256

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
+				for (int k = 0; (dMin) > ((dMin) + (dMin)); k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 579 of bug id Math80
### Patch Diff Hash-SHA-256:

e470f71432010e5f06ce529f48da64f2ab23717a4e6f57ab65c51fc31b78c823

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = 4 * ((pingPong) - 2);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 580 of bug id Math80
### Patch Diff Hash-SHA-256:

23581f98e1740009f836e86720305479d5fa6bcbeac34c7edfefd54408eed121

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) < ((4 * (pingPong)) - 2); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 581 of bug id Math80
### Patch Diff Hash-SHA-256:

52d38a913c11b78c3e9ad35bce47a45adeb82c3bd767fc6ba6f932e0845859a9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (4 * (pingPong)) - 1;
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 582 of bug id Math80
### Patch Diff Hash-SHA-256:

8cd3624fd1c600f334c0f0f00973bcc444599397ab3c7fd39d189898d1acb230

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = (4 * ((pingPong) - 2)) - (pingPong);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 583 of bug id Math80
### Patch Diff Hash-SHA-256:

5032e9397afbb308655af9b46e3ca1db75336d10df8b6dbb63b5a8a1ba6010b8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,7 +674,7 @@
 
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
+			int j = 6 * ((pingPong) - 1);
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 584 of bug id Math80
### Patch Diff Hash-SHA-256:

4f49b6e44eef0c01638290962ce6b9e890be61166b2b20c59d1b04a652cf7422

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					work[((pingPong) + 7)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 585 of bug id Math80
### Patch Diff Hash-SHA-256:

b46d536013f71891359f1cfd8aad42ae7706ce7fe6cb006a0d666700f544c115

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,7 +675,7 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
+			for (int i = 0; (pingPong) == (-6); i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
 					work[(i + k)] = work[(j - k)];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---