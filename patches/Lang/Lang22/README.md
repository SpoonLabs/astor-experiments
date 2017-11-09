
# Patches of Lang22 from Defects4J 
Total patches 21
## Patch 1 of bug id Lang22
### Patch Diff Hash-SHA-256:

0f33b92a6b0e07893a34214c0e7ca194734cac73932a13667945fa7ac85b3f3c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if ((java.lang.Math.abs(v)) <= 1) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang22
### Patch Diff Hash-SHA-256:

5e44b181ad2c4e5a6ce6be5d4156eb09a623566c6a4f50b1484fc8ca8de136be

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (v == 0) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang22
### Patch Diff Hash-SHA-256:

a0bbdd944f51edde565fafb9ef0988aae05de15197ce1e64d900a375856d0cd6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if ((ONE) == null) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang22
### Patch Diff Hash-SHA-256:

3db1ced0a2c69f11216b99c67db4944aaf4ca59900f18225f6e1ee97fa7335cd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (u == 0) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang22
### Patch Diff Hash-SHA-256:

550ba0f534f182e860155af2a0fa2fbf9539384d6f1d3c04fcb7229d6f80fdf1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (((THREE_FIFTHS) instanceof org.apache.commons.lang3.math.Fraction) == false) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang22
### Patch Diff Hash-SHA-256:

b0b51e141c09c208e6cedb2b328050680d77a26a28db035eb458b46cd0ec7ff7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (((ONE_QUARTER) == null) || ((TWO_QUARTERS) == null)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang22
### Patch Diff Hash-SHA-256:

6390201d4080d9d8d74916d9c77a38f3e7feafc7338f5292bfd59f826202aef4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (TWO_THIRDS.equals(TWO_QUARTERS)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang22
### Patch Diff Hash-SHA-256:

2d93dcf82f4299097db6bd4e05d09e0fae50887a58479218025323ceacada0bb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if ((ONE_FIFTH) == null) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Lang22
### Patch Diff Hash-SHA-256:

dd1dd29bcbc158870b30fc961964807e7fd6b1d56a04d09b33d70ab571b1bd73

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (ONE.equals(TWO_THIRDS)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Lang22
### Patch Diff Hash-SHA-256:

70d87234ee5dc935f94a7450a960ac6481db60d8bede51d0dbfc6b29a07ec423

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (FOUR_FIFTHS.getClass().isArray()) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Lang22
### Patch Diff Hash-SHA-256:

fe34ca3ea9f46532f362d028426d5b7976707df7a05333ab0d55574eca589606

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (false) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Lang22
### Patch Diff Hash-SHA-256:

49093d4c1d36ac937d9c888dc516383e93c4e1784e463eaff702ebea4b2d9dd1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (u == 1) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Lang22
### Patch Diff Hash-SHA-256:

5b262dd6ea1c87a024f8b685f9537bdb7ab9e51c194a1e998bae21bbb7596208

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (((FOUR_FIFTHS) == null) || ((java.lang.Math.abs(v)) <= 1)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Lang22
### Patch Diff Hash-SHA-256:

b01b442bae74a8dd9fbfce93fcacdae7b0fb2f98f48a87e3784f5243c6ff79ca

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (((THREE_QUARTERS) == null) && ((ONE) == null)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Lang22
### Patch Diff Hash-SHA-256:

c3e9382d140a8db2d2096616b0fa69b0177ce89289f3cec12ab101e9883bc9b3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if ((TWO_FIFTHS) == null) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Lang22
### Patch Diff Hash-SHA-256:

a4f34459ee3922bad0a6469d6ab74f11627c40595d69a3a18c3edb5035fab682

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (((ONE) == null) && ((ONE_QUARTER) == null)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Lang22
### Patch Diff Hash-SHA-256:

36b758ab54d3217e5b9b13ee41f9a3476d0c52fe0e0fd6967f67f67032927cf3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (THREE_QUARTERS.equals(TWO_QUARTERS)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Lang22
### Patch Diff Hash-SHA-256:

7029e173c62f133919c374112b2ef2e88a5a37e973068d23f96d285556389deb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (v < v) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Lang22
### Patch Diff Hash-SHA-256:

d8ca015c84b47b803d0e788903a058cde83f3260e664f5ae6d18a7e7b964e875

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (((ZERO) == null) || ((ZERO) == null)) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Lang22
### Patch Diff Hash-SHA-256:

3d95c032b96cb1d7fdee3a3f298bc6e56a1aadfef0ee45ebba7c5458c11a2439

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if (u < u) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Lang22
### Patch Diff Hash-SHA-256:

781e86a40908f54a19e6118624b8b0d39de108ed12dec78ae7c51545a44dba32

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,7 +285,7 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
+		if ((ZERO) == null) {
 			return 1;
 		}
 		if (u > 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---