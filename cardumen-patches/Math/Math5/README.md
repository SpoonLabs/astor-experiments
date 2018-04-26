
# Patches of Math5 from Defects4J 
Total patches 28
## Patch 1 of bug id Math5
### Patch Diff Hash-SHA-256:

7c7f93cb4147908fff35370298c2c66df4f0f20a35a12b19c9a28e9e92aa1fd0

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (isNaN) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math5
### Patch Diff Hash-SHA-256:

85a1705d4b2b9cce308899cb543672da59709f8a297d1a3d89a3c2ddbefaa875

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if ((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(imaginary))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math5
### Patch Diff Hash-SHA-256:

a6888fa7915150fbbcce4fcb40b536802afbed00a9be5fc6f7649c76689cfb7f

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (((real) != (real)) || ((imaginary) != (imaginary))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math5
### Patch Diff Hash-SHA-256:

5049570b046b604811bf362a37360040695c0a73db5067a0a7a5e5f3552fc3f5

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (((isNaN) && (isNaN)) || (((isNaN) || (isNaN)) && (!(isNaN)))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math5
### Patch Diff Hash-SHA-256:

df62adbed3a5052f169f520cf485a84b191b8e833747a522ec7609250563f4fc

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (isNaN()) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math5
### Patch Diff Hash-SHA-256:

fa140d26b7f044838d1414f7b1f2c7eaeb6537cb6170efa87fed198c7c10adf9

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if ((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(real))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math5
### Patch Diff Hash-SHA-256:

dae8df374ce42a5da2c5f773d345fe96638a61c9f6f5306bca7999fabed2aac3

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (((isNaN) && (isNaN)) || (((isNaN) || (isNaN)) && (!(isInfinite)))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math5
### Patch Diff Hash-SHA-256:

76cd01d4825eff80caeaa901ccc0789797fd178d6c719954a28a777066cea8dc

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (((isInfinite) || (isNaN)) && (!(isInfinite))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math5
### Patch Diff Hash-SHA-256:

283f2d227bdf2add63257354b88333c6a1d712614837065302f974584467cc05

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(real))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math5
### Patch Diff Hash-SHA-256:

f146278934ab9b7f80ad727c090b9d9438e4c1030a41ca06da8f6b4f23da7095

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if ((isNaN) && (isNaN)) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math5
### Patch Diff Hash-SHA-256:

34a236806800f4b5eb54c768ea556f4852be6626267687b89eb070ca87909789

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (((imaginary) != (imaginary)) || ((real) != (real))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math5
### Patch Diff Hash-SHA-256:

aaebbc80deadb1a0ced1653ee30a262d0a5b4106dfc3e4bbda5d75e3eef1024e

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if ((isNaN) || (isNaN)) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math5
### Patch Diff Hash-SHA-256:

a038dcbeb8fbd5c7be9dfd5a253a9be2643883cba568cf29b62365b1573cbc72

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if ((isNaN) || (java.lang.Double.isNaN(real))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math5
### Patch Diff Hash-SHA-256:

3896ebff175f6d243231e1baf64aa80c7c0a7f0637c7db21ce9ad80d8d3c8e4a

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (java.lang.Boolean.valueOf(isNaN)) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math5
### Patch Diff Hash-SHA-256:

6982244fb88497f0008f9434a9232d407d8349be226f188a3367816ce94b80b1

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if ((isNaN) || (java.lang.Double.isNaN(imaginary))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math5
### Patch Diff Hash-SHA-256:

b3bb92d98a43054f5dd61c72ddc9ec6123ae117f0ec41259df15f3a8257872d7

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -144,7 +144,7 @@
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
 			org.apache.commons.math3.complex.Complex c = ((org.apache.commons.math3.complex.Complex) (other));
-			if (c.isNaN) {
+			if (((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(imaginary))) || (java.lang.Double.isNaN(real))) {
 				return isNaN;
 			}else {
 				return ((real) == (c.real)) && ((imaginary) == (c.imaginary));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math5
### Patch Diff Hash-SHA-256:

73ec06784dbe03b6539c6608037cc5421c7831a2eb8e5896f0436c01ed2da5fd

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(real))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math5
### Patch Diff Hash-SHA-256:

4507e8f592c546fc34184d08852451ab9935f7d7a0df325f9c659c4a649fbe4a

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((isNaN) || (isNaN)) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math5
### Patch Diff Hash-SHA-256:

1521c010b296c55f9eaf77e465d2d45495c956ad7df4636518406dda48d1cd55

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((org.apache.commons.math3.complex.Complex.this) == (NaN)) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math5
### Patch Diff Hash-SHA-256:

3a3ee6b3c216f6d33471886cd8e2dff9c8aa627f790b56bc0663f6743d275eb3

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((isNaN) || (java.lang.Double.isInfinite(real))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math5
### Patch Diff Hash-SHA-256:

bf9c0788bd6b3cd0601b5739c3e290c1b1f3a5ab452e901f6612bbfba5192151

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((isNaN) || (java.lang.Double.isNaN(real))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math5
### Patch Diff Hash-SHA-256:

d789c5e28922650ca3e245bb5ae28c408b79067923d3de32c2f7b27cb8f4b81c

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((isNaN) || (java.lang.Double.isInfinite(imaginary))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math5
### Patch Diff Hash-SHA-256:

250906eaa58245fe03228b4df6acf272bd606e8f88f9bbfa549c685be9ab21e9

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(imaginary))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math5
### Patch Diff Hash-SHA-256:

b8619be370afdab42d073e5ca9a4680162e4b53080a679949d5edd33905f34d9

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(real))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math5
### Patch Diff Hash-SHA-256:

f14295c5a4a38f91884c0c5e0cf14ea5e5846922d9bb95aa3588394a02db3784

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(imaginary))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math5
### Patch Diff Hash-SHA-256:

44e5e0a769848ef1fb1cbb7d45f370c83f869777ff38e3e6dbcdbebcded7ad0d

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((isNaN) || (java.lang.Double.isNaN(imaginary))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math5
### Patch Diff Hash-SHA-256:

ac2742a1b3db8d7d928f259fce4796f6637266a00a4a437a03525c9559e93bc1

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((isInfinite) || (java.lang.Double.isNaN(real))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math5
### Patch Diff Hash-SHA-256:

6f13d08942232b7f4ac349164cf231654035aef5052fb63c3f90c29c2ed1107e

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -139,7 +139,7 @@
 
 	@java.lang.Override
 	public boolean equals(java.lang.Object other) {
-		if ((org.apache.commons.math3.complex.Complex.this) == other) {
+		if ((isInfinite) || (java.lang.Double.isNaN(imaginary))) {
 			return true;
 		}
 		if (other instanceof org.apache.commons.math3.complex.Complex) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---