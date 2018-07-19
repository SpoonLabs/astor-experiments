
## Patch 1 of bug id Lang14
### Patch Diff Hash-SHA-256:

cb83b9bf2edc4a3ce43b75508114dc342a1446b005caa920bd92b7fa8f2ab4cc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang14
### Patch Diff Hash-SHA-256:

c38efdf50eec31777b7c62d0e1c8c01d7ee98a336a7fcdd61b3ec3b03ede7c4f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1, false);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang14
### Patch Diff Hash-SHA-256:

b8269e0613f9847c6799fc4796eb21a6daaba1e1ceb25fcdce6223919007ae42

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang14
### Patch Diff Hash-SHA-256:

46ecb6c43c89dc6c603a087aa4a89657e09fa356462a5d0f0dad45607c495651

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2, false);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang14
### Patch Diff Hash-SHA-256:

08d7361031b930ade7b37e580605e523483e43cd42f65a424586e83039b27a96

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2, false)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang14
### Patch Diff Hash-SHA-256:

b481f99ee9e8701b9cd0d05133c191b37057f23552124b991b0473b5d1fd5bbc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1, false)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang14
### Patch Diff Hash-SHA-256:

ac523ab94e6c92b068da4ae720d4ad380454e478925582a799987c171f94d1b9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang14
### Patch Diff Hash-SHA-256:

99b5cd82aa0ab6578d83df44832f1895ddb4a009e5ea733a6d325fdbb018cc2f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
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
## Patch 1 of bug id Lang27
### Patch Diff Hash-SHA-256:

6d30fddbe3e9ae7904b95098c5f4e85101ca747fdf2a7f3e6336a66b568a0051

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang27
### Patch Diff Hash-SHA-256:

07b28111b32b54c42ca1fc1b37a027c31cb56e8f15253ebcb8f1f014ca213ece

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > (-1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang27
### Patch Diff Hash-SHA-256:

8b34271669698b27bdc9bfbf828469238a249b1a3eb8d60817b724a0bbc9ea3b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos > (-1)) && (expPos < ((str.length()) - 1))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang27
### Patch Diff Hash-SHA-256:

9f0915b63a69b88b966d9e6357b7870f7723f12f4f78d26105ac2470f7b9d0c8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos < decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang27
### Patch Diff Hash-SHA-256:

b0447430ab388be7f93b44c6d0f19fb7ac12814baa1a625d584eb4b13d0ccf73

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos < expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang27
### Patch Diff Hash-SHA-256:

6654d553dd78d8e0fac7a941150c00696f2369131c1dd0e2af6418897abf929c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((FLOAT_ONE.floatValue()) == 0.0F) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang27
### Patch Diff Hash-SHA-256:

c6236829ca1c0e5e8870c48539d9ded8d8b376949bacfb6eb93f785ba9aeab98

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos < decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang27
### Patch Diff Hash-SHA-256:

eb9f791ac9a4b9bba5a042f7410d8c5a9dbbd51914e0f1d5a7d5bdff9759566c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_ONE.floatValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Lang27
### Patch Diff Hash-SHA-256:

d727b831eeb149f6ca2bac2dbfd26d323d51e35218472224fd36d2353cb25598

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_MINUS_ONE.doubleValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Lang27
### Patch Diff Hash-SHA-256:

3b72f04ca42e7be581ff3ca85a9e9f9c172970213f2d23622c2b89d21faaa864

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Lang27
### Patch Diff Hash-SHA-256:

1c1452af550f1feb7ed5144d343df7d15740c8942cf02833f9973c3778af3b6b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.startsWith("0x")) || (str.startsWith("-0x"))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Lang27
### Patch Diff Hash-SHA-256:

5cbd6fccbb919c1e71680341da225afa91aeae0cf48bd7942ec0853edad51ef7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((FLOAT_MINUS_ONE.floatValue()) == 0.0F) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Lang27
### Patch Diff Hash-SHA-256:

63ed08a4d12ebe54a423a351276fa55c726e335be7f3da340cdf31a35361c977

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_MINUS_ONE.floatValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Lang27
### Patch Diff Hash-SHA-256:

d54948a45e17945fb64f5f008ac0945ee665a8247f650cc3b0c38f3c603d1d3d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > (decPos + 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Lang27
### Patch Diff Hash-SHA-256:

5b0d7f9f7bde3aed4e667c3c39c24e847027804fafc1f78403000864fb7443eb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_ONE.doubleValue()) == 0.0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Lang27
### Patch Diff Hash-SHA-256:

4daeeaf8e74e8253ed7689b08fd9e53d8bfc960674c1e3b1b9b49cdb423d908d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > (expPos + 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Lang27
### Patch Diff Hash-SHA-256:

2e408679a955f0cdc6cb21ab0c79cd5e6372dac56619ebb09ab331d53a097106

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > (expPos + 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Lang27
### Patch Diff Hash-SHA-256:

9228e19b1d23372728873ab4821efdad4684f8276f72be5486fe6708d402c433

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (false) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Lang27
### Patch Diff Hash-SHA-256:

0feb107356d724b98c3b70c9e2bf2f8ece6973804ace393caf13e486d1741ff0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == (expPos - 1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Lang27
### Patch Diff Hash-SHA-256:

3e47b231cc381380b150c183edcbd3b549d5c3537e233d8019fbcff06834ab99

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (BYTE_ONE.equals(FLOAT_ONE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Lang27
### Patch Diff Hash-SHA-256:

b8cf26b4e341c749ab2b58cfe77e27d420bdd225bf3677fbe3e14c0b5b3284fe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > 255) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Lang27
### Patch Diff Hash-SHA-256:

46597dcbb4fc10d343819818a3382c86b7cf138c545e39acf2802513f9bcca8f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--decPos) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Lang27
### Patch Diff Hash-SHA-256:

cdca9d499dd5b055fe9752b715532672abfd7d7d76313606ddbc216e0193ab8f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar >= 56320) && (lastChar <= 57343)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Lang27
### Patch Diff Hash-SHA-256:

51b8dd26f88678f1cc6607abea8d0deb219690c5d68a405fa7fa202ed145a9c2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((decPos < decPos) && (expPos < expPos)) && (java.lang.Character.isHighSurrogate(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Lang27
### Patch Diff Hash-SHA-256:

a34fb30678a0dc06428f6b62113aeb4e9b1c588ee2803297b1443a6f7f7d317b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Lang27
### Patch Diff Hash-SHA-256:

6eba9e54b28e31d71ca35c74e2f0a6898ddbda01524b0f1b6955748b7f24a828

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((LONG_ONE) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Lang27
### Patch Diff Hash-SHA-256:

a45b9d0ba7d1daa1aa823d181ac780d9cd45e5cb9fa203a20081e2ed90d30ad4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'S') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Lang27
### Patch Diff Hash-SHA-256:

b79b6314485f9afd5a62dd4e772d088b29bdafce4db3dd1228a1163c0fb3a121

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (INTEGER_ZERO.equals(FLOAT_ONE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Lang27
### Patch Diff Hash-SHA-256:

85b120b56729bc925b3b971c62e578371d71c0b6cfc7c5df332b910e6040c7e8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar >= 56192) && (lastChar <= 56319)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Lang27
### Patch Diff Hash-SHA-256:

3add71810723f4ccdd88240f5214534f3b8c875b6d428d10e5d374d950df74b9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (SHORT_ZERO.getClass().getName().equals(FLOAT_MINUS_ONE.getClass().getName())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Lang27
### Patch Diff Hash-SHA-256:

99aadb852c234063a2e75485949356e0a4071fef8635d71a78a5a6dfcfdc8c9c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Lang27
### Patch Diff Hash-SHA-256:

34b89312985d2b99c58b4fe6b6d58b8b086f9998232dfc491bd9eb0f51df9d47

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 12) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Lang27
### Patch Diff Hash-SHA-256:

17626ea577ac5a2ccafcd45c823b43b61475ce310facf96fa4c38aacbc93823a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Lang27
### Patch Diff Hash-SHA-256:

47c19802961a08554fc305e79a1bfa2aa42560505be92544cbfa486eed80b118

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Lang27
### Patch Diff Hash-SHA-256:

138a586d9db1b5efedb79c8ab98025feb879f94fc85e41e75d336ff203d1c977

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'R') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Lang27
### Patch Diff Hash-SHA-256:

cabb6af60ec5f2db25eb482c2273c428cbe6e574abcda0a46b8318c8aad9bc34

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'Y') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Lang27
### Patch Diff Hash-SHA-256:

2c5ff2da473855f1ff6cc176ee35a8dc33548caef13d81558a7a1005b6b90b67

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'X') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Lang27
### Patch Diff Hash-SHA-256:

7887def65c84dfdcd4e4066b70ea3a999684b2d83e980eeadf538a71cc4ea6b6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (java.lang.Character.isTitleCase(lastChar)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Lang27
### Patch Diff Hash-SHA-256:

205cac264e3db7507c84df47790aec16a9374262283412c82f19109def779828

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 64) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Lang27
### Patch Diff Hash-SHA-256:

749eeb3457c2d8fd87b5878fc3d5f3883b241bea1c563b0a0991076943c6c52f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos >= 15) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Lang27
### Patch Diff Hash-SHA-256:

2bb99468d28dd84a111ebcf1d7e7fb5f121e1cf9accab1c5e274cf91224735bb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 4) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Lang27
### Patch Diff Hash-SHA-256:

6f28a0757ac51052a012f3c8e319e1d1dc5a95c2adb1d12020e0cbdf056bdf7e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'o') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Lang27
### Patch Diff Hash-SHA-256:

8dee78b6d04479b439748981ae5bbd7ad8ff1ccb263432dac5dee788b9c86deb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((SHORT_MINUS_ONE) == null) || ((DOUBLE_MINUS_ONE) == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Lang27
### Patch Diff Hash-SHA-256:

930895ecb46526c1522de1a124e1abc09a57548ca786e31842dcd36ae0a57b11

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (INTEGER_MINUS_ONE.equals(BYTE_ZERO)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Lang27
### Patch Diff Hash-SHA-256:

e3c6b89453d5ec2dbfc7e27e5b179ae3259256204da6bf18c9ca06be7b3872bf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((decPos > 0) && (decPos > 0)) && (decPos >= decPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Lang27
### Patch Diff Hash-SHA-256:

197d39b1a07d51d020b838dd0e05743bb013aa80e70ab5f2a70183faa4fea6d0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos + decPos) > expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Lang27
### Patch Diff Hash-SHA-256:

a29c8632c843b923880744ba0862ada14f1ae0b960ff379bcf4b9a5a881f29be

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((DOUBLE_ONE) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Lang27
### Patch Diff Hash-SHA-256:

5369db697f55d9755c3269ffe7f63e12bd9c35491297477e6b7ff95aa1274bba

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((lastChar == 't') || (lastChar == 'T')) && ((lastChar == 'r') || (lastChar == 'R'))) && ((lastChar == 'u') || (lastChar == 'U'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Lang27
### Patch Diff Hash-SHA-256:

40889794fa72d204ea46dc00cc5460a19aa46e9e26926bbd60a0fba6c00a8bbc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == (-1)) && (decPos != decPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Lang27
### Patch Diff Hash-SHA-256:

ce5d642f98fffdb9245c27c56eec6dc60db4074e97bd896b87c24b37f4d37797

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (SHORT_ZERO.equals(FLOAT_ZERO)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Lang27
### Patch Diff Hash-SHA-256:

919b9d94e92af5a561db7e2a8d5e968f3cb49375c9a547ea4fafc75e548d1e2c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar < 32) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Lang27
### Patch Diff Hash-SHA-256:

e13e344d737d254e1b5e10ab98367d342aa5b26d28bb87de74b218aff19e3ffb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--decPos) >= 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Lang27
### Patch Diff Hash-SHA-256:

b40fa5fe122d4f7109bcf5e27286068b8af0842d15a213428148316f4fffc012

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > 64) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Lang27
### Patch Diff Hash-SHA-256:

ecee54f9ee95ee2f36dac154f6f0ae39c76c68ebde2ca7b74e4db4464d4ffc91

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((((lastChar == 'f') || (lastChar == 'F')) && ((lastChar == 'a') || (lastChar == 'A'))) && ((lastChar == 'l') || (lastChar == 'L'))) && ((lastChar == 's') || (lastChar == 'S'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Lang27
### Patch Diff Hash-SHA-256:

1ad11ffb22c93c82ff3f0a9b144483870be1eb8020658ee29a8cffe71881127d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos < decPos) && (decPos < expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Lang27
### Patch Diff Hash-SHA-256:

dcb40cb16180c36a977df4241a75f80ade21371dac5cf6885875c4e2627ec772

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'O') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Lang27
### Patch Diff Hash-SHA-256:

d8f91a559585699685455b058994a3d06942b0a6ad079c8ffc9e56c97821194a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'A') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Lang27
### Patch Diff Hash-SHA-256:

692ea608f2d6d93584450316c87bd9ce523e321205a8c4d78c21cc65f267f795

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 25) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Lang27
### Patch Diff Hash-SHA-256:

eefc17e00e66571cc7f8f5f5c23affc391160e0a0226dedc0a5d493503710aeb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos < decPos) && (expPos < expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Lang27
### Patch Diff Hash-SHA-256:

cbc04cc8113fc16cfc44a57fbdbbdeac839d3b4ddbe6ea5eaaef8869471da8cc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar >= 55296) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Lang27
### Patch Diff Hash-SHA-256:

72a1f246c80c63131118100bd40c231cfda6f76860200a57585ba7c966e97c35

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > ((expPos - decPos) / 2)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Lang27
### Patch Diff Hash-SHA-256:

2b503c1ea5d35a01c4981706704b0a7c74f257474c9e486c693ac9bf1b349223

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar >= 55296) && (lastChar <= 56191)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Lang27
### Patch Diff Hash-SHA-256:

89e3d3427f18dde5856bef5d46ab053762f329f04e6ea654b3dfc8d4347fc66e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((lastChar == 'y') || (lastChar == 'Y')) && ((lastChar == 'e') || (lastChar == 'E'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Lang27
### Patch Diff Hash-SHA-256:

55e99423eb0caf85feb634ff5e8e418de5abb6c41d3f27a60348f45ec85f3114

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((INTEGER_MINUS_ONE) != null) && (INTEGER_MINUS_ONE.equals(SHORT_ZERO))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Lang27
### Patch Diff Hash-SHA-256:

b3f225d3c17a0c015145b788b6aa4bb6eb35dba014cf578f4c7550fe145c9c05

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 15) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Lang27
### Patch Diff Hash-SHA-256:

d7b09200ebc4f1c39c0e2452778f700ed75e471b77ca1255c4c8c4c0f2a49fa1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos >= 0) && (expPos >= 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Lang27
### Patch Diff Hash-SHA-256:

9e60ab46cbe711dc5494746dd314661d44f0910ba1132dfd9a46683428985da3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos != (-1)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Lang27
### Patch Diff Hash-SHA-256:

025dff18ca44b97e35249d5b5630ec3718eddb7eab89efade50fcda61f49109c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Lang27
### Patch Diff Hash-SHA-256:

0cc775dd6b068f9e493500d8a984d007883e585bc5d4190b81ad18aa2c1e5fea

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 127) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Lang27
### Patch Diff Hash-SHA-256:

c35e0c38d8445666cbb0d4aced6851094db021291342e36aa69551b77af0f7ff

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'x') || (lastChar == 'X')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Lang27
### Patch Diff Hash-SHA-256:

23f77928f2acc693f3b3dee3283ee355a28e4667686d61f3de5def830769da7e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 65535) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Lang27
### Patch Diff Hash-SHA-256:

9cdc80c43a89a7c3122132a45bc39fbcbbf848fe20873f7bf3d5677bc6c2acde

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 1) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Lang27
### Patch Diff Hash-SHA-256:

477f5ed3842030133162f27c04010ee29418b768b1a83c15d77413e3da4c2942

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos >= 12) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Lang27
### Patch Diff Hash-SHA-256:

2f3fe67d236d2ba21595604947b8df5e98da91ba470d711dd07d2c558d0b9e5d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar != lastChar) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Lang27
### Patch Diff Hash-SHA-256:

d6509e79c31bab4d4247c7b630979ddbaacb0231df811bb2016929072963c8e6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Lang27
### Patch Diff Hash-SHA-256:

132eec1c21c8f1075b5cdc53c7a7a3a513f4e02ee3f0fa86abb549de9b0271b2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos != expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Lang27
### Patch Diff Hash-SHA-256:

61fc3adbf21fc29add0af5005d63ac222999234373631de2d376691cdc207413

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (org.apache.commons.lang3.StringUtils.isEmpty(str)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Lang27
### Patch Diff Hash-SHA-256:

03ec1b5f1d9fce573b760c2683cc507da1c2022a23bbc4c36b6ab45d6acaf320

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((java.lang.Character.toUpperCase(lastChar)) != (java.lang.Character.toUpperCase(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Lang27
### Patch Diff Hash-SHA-256:

a7282aea96145eff066bb60e87322f69b510c43e773e6ed873a12602038f7122

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar >= 56320) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Lang27
### Patch Diff Hash-SHA-256:

1fff1365ecec2a2645a8b5b4e1a2d2855a6d906ec2dd8c4c6a3788d550e14ebe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos & 1) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Lang27
### Patch Diff Hash-SHA-256:

55605c8cd0609d3b45f163530e501ae940b825d609ad66c66ce658303e83ad37

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((lastChar == 'f') || (lastChar == 'F')) && ((lastChar == 'a') || (lastChar == 'A'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Lang27
### Patch Diff Hash-SHA-256:

9db53ba1c7ec75ff09d96bb322176521207963e0b98d5834d2a6474de6e01ce9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar > lastChar) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Lang27
### Patch Diff Hash-SHA-256:

44ce1f36d0d3fe8a7fcaf533ae4ffd7090b0c93f1f4bcddb4b71afce2b94f405

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((lastChar == 'f') || (lastChar == 'F')) && ((lastChar == 'a') || (lastChar == 'A'))) && ((lastChar == 'l') || (lastChar == 'L'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Lang27
### Patch Diff Hash-SHA-256:

6d1c8c7bde15503800b4734915f573c4e4f6cf9859eb5f33235591c4938cb2b6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == '_') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Lang27
### Patch Diff Hash-SHA-256:

d2d2c232372f2e4bfa1bb6a0a0fc42ed477da5430f53d4f16afe474ef5b113e5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos < expPos) && (decPos < expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Lang27
### Patch Diff Hash-SHA-256:

51f037ce1a768e47a2be6416b29de21542e03ae2fc7a33f61b858309208c5466

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((DOUBLE_ZERO) == null) || ((LONG_ZERO) == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Lang27
### Patch Diff Hash-SHA-256:

6316b88db8ac1a5f2487c159901ccd98c9e2249c810d9fefef49f50a9ecacd21

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'n') || (lastChar == 'N')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Lang27
### Patch Diff Hash-SHA-256:

24b7e3b8d7a8335f1ff615b9de342d24e902d29c356abc905ea4f84616be32ed

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 4095) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Lang27
### Patch Diff Hash-SHA-256:

ddaa204b870d162afdbff21f94e5f4e0c7340733c1d94564b758e85a42f0430b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos >= 1) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Lang27
### Patch Diff Hash-SHA-256:

a39aa62da9063dd6d05b33f5046574b0935f68a5516b24df70e4abd044827844

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar > 'z') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Lang27
### Patch Diff Hash-SHA-256:

1d75ce4cb90919343837dccbc9e1e820318055d1a187597d17a31ccf1d02bb14

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (DOUBLE_ZERO.isInfinite()) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Lang27
### Patch Diff Hash-SHA-256:

3cf8e1d797173643965a14dc451677dea68d2f0554b0c72acdc62cd4d7690674

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar < 16) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Lang27
### Patch Diff Hash-SHA-256:

e27bd119b442e75587d12de5724e32c6ea903a75f35464005e3ab75ca560e4bd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == 1) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Lang27
### Patch Diff Hash-SHA-256:

342b70b1f2c2b2d9e52fc5a13496ccb5fab3596734b6213009292caf748e5f15

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (LONG_MINUS_ONE.getClass().getName().equals(INTEGER_ZERO.getClass().getName())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Lang27
### Patch Diff Hash-SHA-256:

8c86782505817a3f986b199e6853d79d6278b1521a27b77ccd30227960d459c8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.length()) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Lang27
### Patch Diff Hash-SHA-256:

5410ce01ce875fbfef62ed0634f995d487530b691114133caa6f5b241535ce3c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.charAt(((str.length()) - 1))) == ';') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Lang27
### Patch Diff Hash-SHA-256:

a1757b7584ea90c67272e7fa22c00c3a35faacafc0383ca0b58f72ee96df820f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos + 1) < decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Lang27
### Patch Diff Hash-SHA-256:

b3a0e31ce78997b546a9bb3833c30626e01f2f230ce51540702134b9b59e331e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((expPos + 1) < decPos) && (java.lang.Character.isHighSurrogate(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Lang27
### Patch Diff Hash-SHA-256:

da6b19efb1eb0295049368acee3eca330d9378da425409ce8cc596b8f2770412

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos != expPos) && (decPos >= 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Lang27
### Patch Diff Hash-SHA-256:

a292b1b992a25abc29c6b33091a3d25b22efd41f59ddd32b57a5638c09182fc5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.charAt((decPos + 1))) == '\'') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Lang27
### Patch Diff Hash-SHA-256:

940832785c4dd228283253d0b4fc5773995dec46fe689643efab69d4425154d5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((LONG_ZERO) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Lang27
### Patch Diff Hash-SHA-256:

7f5b7277cfa54e891061bfc4d4f9225240804aab1c673d7df4d6354f85da73ec

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos != decPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Lang27
### Patch Diff Hash-SHA-256:

a0f4377a21b7d20021a4d5740d028383b4e1c7d4202ee832c5e0e05f4d5510dd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((INTEGER_ONE) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Lang27
### Patch Diff Hash-SHA-256:

b6158c01dacd1a0b3d3b2547bd940dd45c572ee27b38cbaa115efef7635a2c05

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((SHORT_MINUS_ONE) != null) && (SHORT_MINUS_ONE.equals(SHORT_ZERO))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Lang27
### Patch Diff Hash-SHA-256:

e9f05dc0911687ce0b07b6b81aa1b23fa7d3957d6bb538b92d2f7ad91c328234

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Lang27
### Patch Diff Hash-SHA-256:

7ad1b1b1730485ef41cc706be9351b200f608fd42d87e79da576cc442fea5219

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((decPos & 1) == 0) && ((decPos & 1) == 0)) && (decPos < 31)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Lang27
### Patch Diff Hash-SHA-256:

96b6fdebf2bc84851fd21ac7a0bddda3cc90985c6d43ade2a11aae51aeda5955

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'y') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Lang27
### Patch Diff Hash-SHA-256:

7f57839c71dd4a07fc13fcf065cfb26ad985775fb5fdd5bc6fb6bdd8c3d9ec96

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == 1) || (expPos == 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Lang27
### Patch Diff Hash-SHA-256:

01025bb181f149dd7d4adfc6e3eedff24eb8a94987cba501d3e69cbb838e4989

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--expPos) >= 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Lang27
### Patch Diff Hash-SHA-256:

3a84b26c7116b0e8a2a7a22e022906873158635a0bb4d6c1a065045ac1215b2e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'n') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Lang27
### Patch Diff Hash-SHA-256:

083861f4f53f3d089c67924516d4970588c25d5d8728f1dae3e2f780f6ffbdc4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 's') || (lastChar == 'S')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Lang27
### Patch Diff Hash-SHA-256:

3df9524dba7e4665b5bdd4f06271d2f7b07e95437ee90ef766f429052cae1610

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos % 2) == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Lang27
### Patch Diff Hash-SHA-256:

d89ed0291a30447e1c769954849b1433706e9ff3ab82e16211f97c02c3551853

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'N') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Lang27
### Patch Diff Hash-SHA-256:

2d86a19ef8dd95c849d0bf86bbf1b1167bdd91a1f082b1a3bf3b34d62327ca56

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Lang27
### Patch Diff Hash-SHA-256:

d677c614cf1540a06c011d8a5c54827684169ae771c04e5a10cfab5e97852b55

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.StringUtils.isEmpty(str)) || (org.apache.commons.lang3.StringUtils.isEmpty(str))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Lang27
### Patch Diff Hash-SHA-256:

895cfc5e3168ca1b46011ae7527dce9e009b485f7f1c280f71254b65ff7eb67a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'x') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Lang27
### Patch Diff Hash-SHA-256:

b44d7312ae06bdc68c2f95981f3294865ceaa1ff3ce78777b9ca22f296124511

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((expPos + 1) < expPos) && (java.lang.Character.isHighSurrogate(lastChar))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Lang27
### Patch Diff Hash-SHA-256:

889b0ac4b99d738d25d052001ecfff9eb202decb919ba40fc37fd156e03d8517

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.BooleanUtils.toBooleanObject(str)) == (java.lang.Boolean.TRUE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Lang27
### Patch Diff Hash-SHA-256:

85d30fcd4049771ec734cb17ecc66bbed2af5bfb9e47b3afe8c7f3be393bcd03

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 't') || (lastChar == 'T')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Lang27
### Patch Diff Hash-SHA-256:

59867b258bf7300b23fe2a99e60b83ff916c187408df704f8125acf162317534

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str == null) || (str == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Lang27
### Patch Diff Hash-SHA-256:

96792d979569f953d6ed9f3c2b42edcfbcd39d17311de3fad4ebb0e362d723b7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--decPos) >= 2) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Lang27
### Patch Diff Hash-SHA-256:

df6ab7897d7c1746cb8a3f64a55513aec8aa10433b1ba9b3f451f4cedd4067de

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((INTEGER_ZERO) == null) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Lang27
### Patch Diff Hash-SHA-256:

169b89350ebd3702c9dfc0fa30efe8f6d18776fa883933c2baec275654c4e66e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str.regionMatches(true, expPos, str, 0, str.length())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Lang27
### Patch Diff Hash-SHA-256:

d527fb30e99c465c8a14f3d1530c801b094b0c67f629ab502af5ae8c47a0b6f1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.length()) != (str.length())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Lang27
### Patch Diff Hash-SHA-256:

2415cc915d052d588b1f09c40ebf4bc2190d989ed7e17a54742ab45e6a81bc41

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > (java.util.Calendar.SATURDAY)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Lang27
### Patch Diff Hash-SHA-256:

3035e75e84ac843dea3262cd78279223e6c6fbd58b4b7e182efca8671227f3b7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Lang27
### Patch Diff Hash-SHA-256:

09173a99b04cb2c8f92a045a6ab2cfaa3272944a34fddbb6a63f92fd9e06d4fe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str == null) || ((str.length()) == 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Lang27
### Patch Diff Hash-SHA-256:

b0d4fbed55f7409f00e3b6d92ff6fa967fcf911b4776914d5c5ca019845c80d0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar != lastChar) && ((java.lang.Character.toUpperCase(lastChar)) != (java.lang.Character.toUpperCase(lastChar)))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Lang27
### Patch Diff Hash-SHA-256:

4fda0526bb9b1a7152fcff89edeb35e3394ce2b09a57a76fe01e99f6c3c607ff

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 't') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Lang27
### Patch Diff Hash-SHA-256:

d5278af27b19cfea21164fc867072896bda6f5d4fa3341841ef58d491cff0a3f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str == null) && (str == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Lang27
### Patch Diff Hash-SHA-256:

f09815424f9fd830c038f1a778d99b2f7c3e48a1ebdfc3c73bc5bc6fa187c730

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == (java.lang.Character.UPPERCASE_LETTER)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Lang27
### Patch Diff Hash-SHA-256:

ee44c93c5f4b363e0d237e269e22ae256c8566c47cb0789f6843e80eeb48071d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'F') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Lang27
### Patch Diff Hash-SHA-256:

7765db9a9fb2595823c24fd69fbe630194bfefd7693d57596e5216449d173133

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (decPos > expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Lang27
### Patch Diff Hash-SHA-256:

ce61ff3330d8d9b86872da669dac99d33a0ba89aafafe8e4c4ae3da04147bc5f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos > 7) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Lang27
### Patch Diff Hash-SHA-256:

4898ef3ffae4b0dbd5012c9c4a6f8fa140f0e8953ae5a9c8dadc7ee2cf3ef190

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.length()) > (str.length())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Lang27
### Patch Diff Hash-SHA-256:

5767fb700c996b2269d64808ec76107643dfdb4966f24a94504f0e92a401b057

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos + 1) < expPos) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Lang27
### Patch Diff Hash-SHA-256:

2af0ccfedd4c9a73d304d15b9ca373f5c65845e48dbb118cf4b3611c699b8e71

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 's') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Lang27
### Patch Diff Hash-SHA-256:

53fe5b652d0a3194797ea947e410ec3aee1b04ec733841db4b99726af97c2c75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str.regionMatches(true, expPos, str, 0, expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Lang27
### Patch Diff Hash-SHA-256:

20068e1f68ab9fd904e2656534871e404f541e1c9f20cb2346d412a78164a9d6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == (java.lang.Integer.MIN_VALUE)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Lang27
### Patch Diff Hash-SHA-256:

b3680beff78fe09ff3eca489d4fcaa0b723692057568a860830589845cd20d3a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.getClass()) != (str.getClass())) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Lang27
### Patch Diff Hash-SHA-256:

7bbf990770c8f81bf04bd66be526e1a3f246d102ebd2597e8536512b2c22adb1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'o') || (lastChar == 'O')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Lang27
### Patch Diff Hash-SHA-256:

c1399531dad8c54a10353ce32f8d21e09afd2893705696a2a49d23d0f44affc6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (expPos == (org.apache.commons.lang3.time.DateUtils.SEMI_MONTH)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Lang27
### Patch Diff Hash-SHA-256:

002945bb47495c6dbae8b78e0e5efab3834cf8a189c0da38d5fc940638d49d47

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (java.lang.Boolean.FALSE) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Lang27
### Patch Diff Hash-SHA-256:

8056264de216202a15ae3bc7cb0e475746fc7ed8347b11851313363668e72258

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.StringUtils.isEmpty(str)) || (str == null)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Lang27
### Patch Diff Hash-SHA-256:

03d4d6bd58b4fb407d155b083258784a82b7ca8acd0596d2e0cc624e72b64e8c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'f') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Lang27
### Patch Diff Hash-SHA-256:

fa612d822e7806d3d9cbb7a37962094b5d5ba5c419403242493fd616ab0fbcc8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((org.apache.commons.lang3.StringUtils.isEmpty(str)) || ((str.indexOf(lastChar)) == (org.apache.commons.lang3.StringUtils.INDEX_NOT_FOUND))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Lang27
### Patch Diff Hash-SHA-256:

dfa6b76e2bb47994043e105f7b9bcf65e662d70f1ada95a05e6e94c3d64c0b15

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((((lastChar == 'y') || (lastChar == 'Y')) && ((lastChar == 'e') || (lastChar == 'E'))) && ((lastChar == 's') || (lastChar == 'S'))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Lang27
### Patch Diff Hash-SHA-256:

3b2ebe75b06b69072c8bde080061b1f4fc3963a04a6de18dcabf30cc6b744fe9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'U') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Lang27
### Patch Diff Hash-SHA-256:

653fdbe233ed83018468b7ec2f42c66231e76b7dbcd03476800d15acd6af9efc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((expPos + 1) < expPos) && ((str.charAt((expPos + 1))) == '\'')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Lang27
### Patch Diff Hash-SHA-256:

3640973fee14c22215c63b2414e286457dc76112ede44a6c48fb31dd889d6c01

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (str.startsWith("L")) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Lang27
### Patch Diff Hash-SHA-256:

8968adcdbde038a7859881e5d2b270184cce021750036c8cd9c9a1dadb1c1724

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (lastChar == 'e') {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Lang27
### Patch Diff Hash-SHA-256:

bb328c1099637a0c733839f1a2ad2184776938625d1babbae44253836d11d196

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((str.indexOf(lastChar)) < 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Lang27
### Patch Diff Hash-SHA-256:

7591dfe4703c5da016138516e5bf53a5f94fbfddfef97ba8fcfca8dddbdef6af

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == (-1)) && (expPos != expPos)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Lang27
### Patch Diff Hash-SHA-256:

6a4fd200d45ec7f49a275fd771c6aebb34ba4147c5a86a2124d4484ddb48bda2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((expPos == (java.lang.Integer.MIN_VALUE)) && ((expPos & 1) == 0)) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Lang27
### Patch Diff Hash-SHA-256:

5c44039e1f831a2ad1301d26fc303382fcf33f1e343a5cb578ac860103d2957a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((lastChar == 'y') || (lastChar == 'Y')) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Lang27
### Patch Diff Hash-SHA-256:

9d55585ab049d15e6b2f58f254ce108470175c9a6dd95d7953c4ef4fc50f7df5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((--expPos) >= 0) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Lang27
### Patch Diff Hash-SHA-256:

0e2e22331d67259b853bb0368020736fae8647a75504d6dc32ef973f5aeccd66

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring(1);
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Lang27
### Patch Diff Hash-SHA-256:

a33b11911b21bd09963e3399684f17ca58a0d3f8cc9108de71ab56515b2fd5c6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring((decPos + 1), str.length());
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Lang27
### Patch Diff Hash-SHA-256:

2ef9796d9e12b0e9965ccb662f368a76f2842baabf6656ce0ef86e7676df04cb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -152,7 +152,7 @@
 		java.lang.String dec;
 		java.lang.String exp;
 		int decPos = str.indexOf('.');
-		int expPos = ((str.indexOf('e')) + (str.indexOf('E'))) + 1;
+		int expPos = (str.indexOf('e')) + (str.indexOf('E'));
 		if (decPos > (-1)) {
 			if (expPos > (-1)) {
 				if (expPos < decPos) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Lang27
### Patch Diff Hash-SHA-256:

3bdb5afca5df5e375fe88f806af652129c39bec32c82a7000b1243725c7e09bf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring(0, ((str.length()) - 1));
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Lang27
### Patch Diff Hash-SHA-256:

fa0552fe6b78e09c8609676ccb9bea70a6ee710fbcd4137a9623bba896428ca2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring((decPos + 1), ((str.length()) - 1));
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Lang27
### Patch Diff Hash-SHA-256:

f17193c0db20d941bdc5e05c3f3058418275ab78e9b3b230cfc3ba1e1c27f640

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str.substring((decPos + 1));
 			}else {
 				mant = str;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Lang27
### Patch Diff Hash-SHA-256:

6c6e6fc948b90e648817f65aa4994640b49a9b08d173332b36ab782364598360

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if (((str == null) && (str == null)) && ((((str.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(str.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(str)))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Lang27
### Patch Diff Hash-SHA-256:

fdfa343a2bec1cd4fb481ed5dcc5d5a8d8362908c0bb12719013c80ec4e752f5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -164,7 +164,7 @@
 			}
 			mant = str.substring(0, decPos);
 		}else {
-			if (expPos > (-1)) {
+			if ((decPos > (-1)) && (decPos < ((str.length()) - 1))) {
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Lang39
### Patch Diff Hash-SHA-256:

13a27b10c7fa746c1e685fc43a332cc8e9d4e0e5cd9b17b85c359b13f0b44123

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= tempIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang39
### Patch Diff Hash-SHA-256:

8cec83b3c00a50695b7226cbafb71b9232143ff857a47190023766b82b1b34c7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength == tempIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang39
### Patch Diff Hash-SHA-256:

24722574ca61ee2b6dc5821a3cd0362c5cee906d3fd7663bad2650f47d23103e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase <= (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang39
### Patch Diff Hash-SHA-256:

62b82dc3a60c04449b5bab01ed775cbc1f545b35278cd8cbb6a05d4655241bac

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || (org.apache.commons.lang3.StringUtils.isEmpty(text)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang39
### Patch Diff Hash-SHA-256:

142656a7ab0928532001450e4b24f4087c46173009d278e1a8804cc29f1be893

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (repeat && (timeToLive == (java.lang.Character.LOWERCASE_LETTER))) && (textIndex == (java.lang.Character.UPPERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang39
### Patch Diff Hash-SHA-256:

f084c44c7a4dbc1d13625ac8759638413bae209596e4249ba4d06d50920eb5d4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang39
### Patch Diff Hash-SHA-256:

0b43d98eb2b12af0805d7aaaecdf0e02781677c14599b714e1a3cd7f6d536df0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.StringUtils.isEmpty(text))) || ((EMPTY) == null)) || ((PAD_LIMIT) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang39
### Patch Diff Hash-SHA-256:

0cf913b86856902a53913f3ef3e2536a1e72423733f02711d26f8749745e8a43

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Lang39
### Patch Diff Hash-SHA-256:

25bd1362689da195ab4333d2ec0f4ef347cae973b26f19fb0a93d07e150eb50f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Lang39
### Patch Diff Hash-SHA-256:

9e6a8f43006850c189d5d45975ef6c19c0dcb257708e2eb38f2abb926f9d2137

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex == (-1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Lang39
### Patch Diff Hash-SHA-256:

379c699ed9b58f56f65b5363c6507a88518f19c721af8a22f4566d414a194a75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Lang39
### Patch Diff Hash-SHA-256:

6587655641610b4aa39815dfc5fd50e7253e283723aee65243c52be31ba02f7a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.indexOf(text.charAt(timeToLive))) < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Lang39
### Patch Diff Hash-SHA-256:

56502eab0f3c02551192824ec60449855054954305f82e0a6c3b1e437f8256dc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) == 1; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Lang39
### Patch Diff Hash-SHA-256:

797bd8f9aedf63d67960eaea9ef84060d47608568847ec3fe8b161870b459a42

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Lang39
### Patch Diff Hash-SHA-256:

1378ff20579f66f2cae9a5e297a6793c32a2849129df0b0c25314283be15313c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength != replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Lang39
### Patch Diff Hash-SHA-256:

cffa9f27176c87d88f68f1c5ab68d3efe332182446ca9ec2e2e66a6648d0abc1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replaceIndex < 0) || ((INDEX_NOT_FOUND) > (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Lang39
### Patch Diff Hash-SHA-256:

535d28ffbb368fccc4e3ebdb5ba6da4719306db97e457e8a4c38aabbe8a666fa

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.StringUtils.isEmpty(text)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Lang39
### Patch Diff Hash-SHA-256:

a8e235b58b4dd61a463ddfeb423bd2c214086fd7b25b9fa946b4a8a4c4974888

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Lang39
### Patch Diff Hash-SHA-256:

dceb9c344c96189b4f32e1513952e4cd34e4ad51af77411c058e37e6485f8112

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Lang39
### Patch Diff Hash-SHA-256:

0c8fb627adb0d95c51ae816e53a491effbb70e0c4f0f6593b3a8dc4c71c0a6d1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Lang39
### Patch Diff Hash-SHA-256:

ee9a46a80fcc7adb2b5127e6a9daf4418eaf20262f86591e90f5b7098ac87f02

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Lang39
### Patch Diff Hash-SHA-256:

ec6b685608cd6f5c396ac02d8fa17ed0cd06e8bbfa8857c6be237df6a116a649

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Lang39
### Patch Diff Hash-SHA-256:

c022ce7f59853cdeb56226e123064f428513e085e4d2bf3460a7992824a5b594

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Lang39
### Patch Diff Hash-SHA-256:

3fd7c2d1e31f04a1c7a920a8dc548983334ca46667ec4366156d1ae4acc8df60

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.length()) == 1; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Lang39
### Patch Diff Hash-SHA-256:

7de4bca0f2125f6b413d723c37ad79e0816cefeb6e7e430d65217455c8c6997b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Lang39
### Patch Diff Hash-SHA-256:

989da1a4a20e1c4bbba683ed2c48ee0702ae3feddcdc23c133e0f959ca03b049

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) == null) || ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Lang39
### Patch Diff Hash-SHA-256:

a84d5288d234966172ecfb85004c3af969148c279d4e363abadc5045b7fdefb5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength < (EMPTY.length())) && (searchLength < (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Lang39
### Patch Diff Hash-SHA-256:

3e5d5699f6ad1f992848e415876dd38dff0affe354fa3e23a7e99efc9b02908b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementList == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Lang39
### Patch Diff Hash-SHA-256:

77bb63ae823a2cfba8c12e24323be6bfd58b26957004739577501b0f0d60270c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Lang39
### Patch Diff Hash-SHA-256:

d01f2fd524e1d1f2370bce59c128ca28e6db2aaa39a32f9304dbf875e299ead7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Lang39
### Patch Diff Hash-SHA-256:

f1a57dbfa90887d27fb13b60ab187a35d7647104f42abe77bd32f99fe8f9c6d8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY) == text; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Lang39
### Patch Diff Hash-SHA-256:

0f3b59a927d7b94fa3a062a7caadcfe829802523c5fb0e5baa95d067101da572

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength++) == (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Lang39
### Patch Diff Hash-SHA-256:

cf87db3c794c3e778e7fb035a75fa8068781205f013d8edd58c952d2ac6f5220

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text == null) || ((EMPTY) == null)) || (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Lang39
### Patch Diff Hash-SHA-256:

e171449ac6c5041f1dd1f8290cea381dd5e49b6cfcd9090b706b29a9b6a9f65e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((noMoreMatchesForReplIndex[replaceIndex]) || ((searchList[replaceIndex]) == null)) || ((searchList[replaceIndex].length()) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Lang39
### Patch Diff Hash-SHA-256:

14104defa7c29a3309efbba8332bc53ce1a35fb646a23955b7c8f05c22fa697b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList.length) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Lang39
### Patch Diff Hash-SHA-256:

13cebe443a6839a890df1a243a089ba097eb914aea022d4bba29e7443235d349

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Lang39
### Patch Diff Hash-SHA-256:

de36d92f38f4b6aabff2e55d1bc26b6027dbfbd115a25fdd9b7b99e9c99bdcd7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Lang39
### Patch Diff Hash-SHA-256:

8ef83e420f7cad1568387d84814ad172d5d21848e5746b5e713c8a03de256c48

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchList == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Lang39
### Patch Diff Hash-SHA-256:

768ff5cc51c3207e96d38ca40f01a2985cfd6edbd817ccd5a3ef7f9a187db49a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength <= 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Lang39
### Patch Diff Hash-SHA-256:

def1c90a7650848fb2450440d00dce61f9134c4d508fbe26bd6b0ad8e242b35e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text == null) || (text == null)) || (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Lang39
### Patch Diff Hash-SHA-256:

02453f64926143e5b98b8b99b77189f32a7e6d6d7bbbaede859d29f2cf0b89a6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Lang39
### Patch Diff Hash-SHA-256:

5cedb18e7b47f16a274a3c51f691ba39894112b941ef3fcddeac838efa76f2eb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (tempIndex++) == searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Lang39
### Patch Diff Hash-SHA-256:

e4d4630fbba8ad09fe61f58f8727bf9d15eee9042f761a595edb5feb3d2e23e2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Lang39
### Patch Diff Hash-SHA-256:

75a30934f62ea104aa214fc657543bb3f900886c24c1950e197887d34c0dbbdb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Lang39
### Patch Diff Hash-SHA-256:

927c45f7104b82042469dcb5e5057257fdee6d1a1ce3398e7ea7b2f7ea5520c5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Lang39
### Patch Diff Hash-SHA-256:

6d5e3017ffe51bcebd1d49a61c61a44867ff73a60d6b453645ae5e3ff8daeb95

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Lang39
### Patch Diff Hash-SHA-256:

ae8dfbd508032dcdf7068a97b5777b5de28b676706e39ce1b1f145e8f67308eb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength > replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Lang39
### Patch Diff Hash-SHA-256:

5f1754b662fe901f86afd8df791a07207220d8773233f84a16569ba1f48ace48

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Lang39
### Patch Diff Hash-SHA-256:

376b700eeef09d0954c9a4ffac86ab1ef3c6e5a027a9582bc965f35a318a5c60

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > (PAD_LIMIT); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Lang39
### Patch Diff Hash-SHA-256:

10d187a5f22574bbc712947d5a8fcdbf90d7abcc84655cad576e83a53d1902a6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Lang39
### Patch Diff Hash-SHA-256:

f68c850ff21a7f63abbbebea9cb8a4b71e3b8b0386dfca53c3263ca100654953

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive == (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Lang39
### Patch Diff Hash-SHA-256:

b8bfcb68ee6f266aeb31b54abaa7605269e228fdc0e8689d2efa2757a1f29778

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) == null) || (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Lang39
### Patch Diff Hash-SHA-256:

e4f112993d93d816fd40287d69634fab98f1e3c9f2df6b709c2be9e96a02c638

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.ArrayUtils.isEmpty(replacementList)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Lang39
### Patch Diff Hash-SHA-256:

5e1c702b19da6ddd3c446cf4ba8960965621dd3fc44df50fd1b2dc0d1e00e311

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text == null) || ((text.length()) == 0)) || (searchList == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Lang39
### Patch Diff Hash-SHA-256:

852a4b4dfb251f9e13ce08c20d17f34a03a0fad08cd0d6051021b4465848bee9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetterOrDigit(text.charAt(textIndex))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Lang39
### Patch Diff Hash-SHA-256:

57da409c855513976d63fd5a73a88922a112b38d8e9a117c3750399ecca7e7b1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Lang39
### Patch Diff Hash-SHA-256:

b3318140959af687070c7d5e564bee647bffd3c23b0718c6e0a9961726511fd1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex > 64; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Lang39
### Patch Diff Hash-SHA-256:

b0febaff80fa1bc9f571609cf9bb0d9c7deea4a39b080721c42da19b32a27bf4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Lang39
### Patch Diff Hash-SHA-256:

a3e9cba4d1df4df1bed9f2fb41f7cc9bd2cf372076bd507a0e2af4d302a95460

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.StringUtils.isEmpty(text))) || ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Lang39
### Patch Diff Hash-SHA-256:

fedaecf494546b6de2048cec269050c01fbb05ba7e057b5d0458876e7c32b1aa

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength > 64; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Lang39
### Patch Diff Hash-SHA-256:

0b94df182e9292226b16d1160e871e74053ea442bfeb0cdcccb4751cf6effab2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (repeat && ((INDEX_NOT_FOUND) == (java.lang.Character.LOWERCASE_LETTER))) && (replacementLength == (java.lang.Character.UPPERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Lang39
### Patch Diff Hash-SHA-256:

8c1e16e97e13bb40a4d7ddd6f28508b0f8b8a024294bede86929eb9f69342198

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive == (-1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Lang39
### Patch Diff Hash-SHA-256:

fcb61d130b263cb24b56ab61993604173fa0b524e68f0abf16e6922a6362b586

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) == ((text.length()) - (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Lang39
### Patch Diff Hash-SHA-256:

cb51767ad48cbe79e3098714181ad3bbf44d611ee5b99b5d49782c3710075cbd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Lang39
### Patch Diff Hash-SHA-256:

84a1f5025dc1cfbb630b9207e3a131481f5e355012ebce56461c69ac35a0ef95

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) == ((EMPTY.length()) - (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Lang39
### Patch Diff Hash-SHA-256:

505c382bdf75f24fb5a8e408740fb11d7b8f830e288197a394662d0fd6584f7b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start != textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Lang39
### Patch Diff Hash-SHA-256:

7160c635c72101e9495ad88da08731de2f66fc8b505410df0a41e93ec9f2b31f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Lang39
### Patch Diff Hash-SHA-256:

41592315546df144d6e90f4d660febcbd829d509394c04f92f55dfd7a88b02da

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Lang39
### Patch Diff Hash-SHA-256:

72f003895e0f4a644601cee09ce1db6737d4d7fc816e71cddb819a9902bed5fb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Lang39
### Patch Diff Hash-SHA-256:

f68a2eeed9ad5095b0ef8581193e18c7fa55cde0ca028289fa9749573254b062

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase == 1; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Lang39
### Patch Diff Hash-SHA-256:

3efea553ff9f959f0674ec1ccfb99b795e4ffea0fd54f2389ff943f9058333ff

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) - (INDEX_NOT_FOUND)) < (replaceIndex - 3); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Lang39
### Patch Diff Hash-SHA-256:

694dc9b1bea8dee6edff5013b0e236453e5242b571ef1e9ac39bbe5c33a0553c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase == (PAD_LIMIT); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Lang39
### Patch Diff Hash-SHA-256:

7f837b8a7513f90a4baa83a21b6bf63d42309e4e67c15cb68a14b2c948178ea8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) == null) && ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Lang39
### Patch Diff Hash-SHA-256:

ec4701b1221f70c8e0b561ff3c55d2cd10e84c2893b43ba5e139741a9dbbace1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive == (java.lang.Integer.MAX_VALUE); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Lang39
### Patch Diff Hash-SHA-256:

4db5743a79b9a24c839d30b30e07cd006541f1c53eb4f055a076d6989b71ce1d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Lang39
### Patch Diff Hash-SHA-256:

231c43a3d30d7ff41b3afa4ab6180ad5190a923cdd751929f77a46ef387752f7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) == null) && (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Lang39
### Patch Diff Hash-SHA-256:

91b708318bc1925b8e0468d0c033d0338d96953324eea57315a7eac4765b3a88

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength++) == searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Lang39
### Patch Diff Hash-SHA-256:

63bdc1ffcd279b64dbf85bbf5c5ee412fb5ca62310481f50c7f1d97382a2a27b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (-1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Lang39
### Patch Diff Hash-SHA-256:

55f268a30beeae72b6921f3d6826826cd91ebad36c37eb7f33aa10e733c9c50e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength > 64; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Lang39
### Patch Diff Hash-SHA-256:

e1d0a1271a1a6035ce5723a353aed7ccd3e70ff10b4b988ed715e74ac7b3eafb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.StringUtils.isEmpty(text))) || ((EMPTY) == null)) || ((INDEX_NOT_FOUND) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Lang39
### Patch Diff Hash-SHA-256:

3e3bee6638f6afc952467c95dc452c5a4200a0ff97b0e8fb7e3abae2799a687f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Lang39
### Patch Diff Hash-SHA-256:

59fb5b838c53d7f12abaa61b4bfc4c8b64dde186bd3069821c34ffae42645671

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength <= 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Lang39
### Patch Diff Hash-SHA-256:

2e9399dbab8535c74e02c4375035d35e2759db6fd690fd4558e8099ed803a3a8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.StringUtils.isEmpty(text))) || ((EMPTY) == null)) || (replacementLength == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Lang39
### Patch Diff Hash-SHA-256:

c43a06255b234cb8074565c26ed010690ff0f2b499c2b10f82bc1fb5addf5859

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) < (EMPTY.length())) || ((PAD_LIMIT) < (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Lang39
### Patch Diff Hash-SHA-256:

77bf19c1e3fc464f992b8a835cf8afcf7e01f488cc9e801e5ec6abfcb13b7c9d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != increase) && (java.lang.Character.isWhitespace(EMPTY.charAt(start))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Lang39
### Patch Diff Hash-SHA-256:

aef017d70f367d401080fd6262b23fafba8d1e3ace9b631d7bb848357bdd4913

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive > searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Lang39
### Patch Diff Hash-SHA-256:

85dfadeddfb5deaefcac1fd7c18cf41664063c4b0e8fadf9ced5f8dc11d5e7f4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (timeToLive < (EMPTY.length())) && (timeToLive < (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Lang39
### Patch Diff Hash-SHA-256:

345488ee9568619e8f00589659137b07df6fefe934b347b69379b91f71e6ace7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || ((text.length()) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Lang39
### Patch Diff Hash-SHA-256:

3cd876b26280d38a0c6b864c89d8a11222b90a32ff5f07eafd9fa00f18323c62

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex < tempIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Lang39
### Patch Diff Hash-SHA-256:

6f9bf081247fb3633e70503d0daa30684b37bb67471053a6cbc9e22686b1f08a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex > increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Lang39
### Patch Diff Hash-SHA-256:

9fefa6ab4a0cd5a6945ae333a7f339950c959bd7b1a8fd5ac90d9ada1f86cdf9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList.length) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Lang39
### Patch Diff Hash-SHA-256:

dd9715aea5c298531b4ed7d02dd4c34f64cb28e6400299e25eba0fa0d1b4f46b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((((text == null) || ((text.length()) == 0)) || (searchList == null)) || ((searchList.length) == 0)) || (replacementList == null)) || ((replacementList.length) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Lang39
### Patch Diff Hash-SHA-256:

eb11223f546deba3df1c1772e9f02900e65e99699dbe7bf30c424e27a6211161

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start = text.length()) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Lang39
### Patch Diff Hash-SHA-256:

e7193bcb2e9423ea7cdd3caa6bcd9de3ac122612e27660c5fb7af91d13d43e34

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Lang39
### Patch Diff Hash-SHA-256:

009ebdca1d1a384d6a7e2c4a2a6d6cd180eb7dd6925226f8bd1fec2407371698

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList == null) || ((replacementLength = PAD_LIMIT) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Lang39
### Patch Diff Hash-SHA-256:

908520466269a27f5c89c0018cf8cf8edb7bec00e0feb2ecdddc8621a416fc8f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Lang39
### Patch Diff Hash-SHA-256:

d477e7650d6dd1f1c48b37634cc699908b352f43293d479fe68548500a35384a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList[increase]) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Lang39
### Patch Diff Hash-SHA-256:

9cf01466152c487cf18e71ec28e040a5a3c0aea5a7337fcb8c0d65fb3a910480

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.length()) > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Lang39
### Patch Diff Hash-SHA-256:

0ba886d99f61473a0768dbf5d9c8d61ee6a5aa310606a10d066a22e8a2963812

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < (textIndex - start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Lang39
### Patch Diff Hash-SHA-256:

ac6ee704be0776c9a09032c958c3a9de0341e134c68a480d9693f704beaabe86

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((text == null) || ((text.length()) == 0)) || (searchList == null)) || ((searchList.length) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Lang39
### Patch Diff Hash-SHA-256:

b829a07cf7c0903cdb6fad786f40f5cdc88b18ffad9be229ae81789c71fff714

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength == (-1)) || (searchLength == ((EMPTY.length()) - (EMPTY.length()))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Lang39
### Patch Diff Hash-SHA-256:

6bb9e0a3330cd1a8b2e39ef2126f4dc7b19acca112cedbb827c5130b53ade396

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || (searchList == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Lang39
### Patch Diff Hash-SHA-256:

7b8770c37cd73ceb9b665d72c983aaece5a359307d92356cb69c51e54bc53ca3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase < start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Lang39
### Patch Diff Hash-SHA-256:

c4e2f667e8f45b116c7ece497b582855b8277f865c0d85cab55be797e678e231

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength == (java.lang.Integer.MAX_VALUE); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Lang39
### Patch Diff Hash-SHA-256:

c996b305225d0d2137963dc297dc7b55de6e6a86a47b1c54beaad6ea17dbb84d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Lang39
### Patch Diff Hash-SHA-256:

5800ad8b3dae0121064af31c33f81e98914b48adca7e51ed838738864af6961c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Lang39
### Patch Diff Hash-SHA-256:

a4e5089ee933c9926d0a79cbb3df3613d2adce672625dd3891108a91cc5359b3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) || ((EMPTY) == null)) || ((PAD_LIMIT) <= 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Lang39
### Patch Diff Hash-SHA-256:

5d0ef1abb439ed375b4477dd8fa2eea1bfebbf47143f247a6fbc13b2008021b0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex != tempIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Lang39
### Patch Diff Hash-SHA-256:

113f39028c7669de0ec484b5a2064ae1cd2b66e43386c25b221e9aa1200ae983

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || (org.apache.commons.lang3.StringUtils.EMPTY.equals(text)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Lang39
### Patch Diff Hash-SHA-256:

20a4e3f8d7c7a28a7514935929f9d8c8be90ace0260c16fe221b6232f5a43abb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive < timeToLive; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Lang39
### Patch Diff Hash-SHA-256:

943108cad0f929c4ac303eb6036dc81d0c1bce99f1b8763eaba25e701f4a61bc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || ((tempIndex = text.length()) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Lang39
### Patch Diff Hash-SHA-256:

a33c1edf1afc4e5208d16d814e21222325ac85fa9523ff754811bf3e9ba158f9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength == (-1)) || (replacementLength == ((EMPTY.length()) - (EMPTY.length()))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Lang39
### Patch Diff Hash-SHA-256:

9542f395ca5b36ad19819bc5d3c0c855c9f8d29a7193a54f2084ccefbfeaf728

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (repeat && (replacementLength == (java.lang.Character.LOWERCASE_LETTER))) && (tempIndex == (java.lang.Character.UPPERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Lang39
### Patch Diff Hash-SHA-256:

45f7d6a6d2eac30bbc70adc47473d70ed0b6aa3a247ab27b009b0b9b439b8113

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase == (java.lang.Character.UPPERCASE_LETTER); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Lang39
### Patch Diff Hash-SHA-256:

e72e5dbf4697e4ec72eb39b1f9d7d0b7d8235b7b4922984380db093889cbb91a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase = text.length()) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Lang39
### Patch Diff Hash-SHA-256:

5c2a4b5cb928bea1909ffc93f7db321a49b86ff5d2a9f794f7c47548f3760aa6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (repeat && (timeToLive == (java.lang.Character.LOWERCASE_LETTER))) && (tempIndex == (java.lang.Character.UPPERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Lang39
### Patch Diff Hash-SHA-256:

c3763014cf7bf67057ad4ac79193d5726fa399d467819403f19ea251d5640b42

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Lang39
### Patch Diff Hash-SHA-256:

65bb69b6d4d2c2d8c9311d4e8f87bf6330a482b2f758c6b308371727d6ed5d2a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex != start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Lang39
### Patch Diff Hash-SHA-256:

635c1d4dea83babdb23f010d6c123a7306ffc2c5db8a6c449830934d3e6b46e7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex > replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Lang39
### Patch Diff Hash-SHA-256:

f53f13cc77beea7dae9b768074605d076e904dcfd520ccf6929e4d06d3863ea8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Lang39
### Patch Diff Hash-SHA-256:

8611e0693243d511dc534522fd529f19a16bc4453fec7649d0b5277382ed9184

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Lang39
### Patch Diff Hash-SHA-256:

95845d2a77996f30054e4b4a30a3e07b50d1bbb6d23a04db9e5c45c51ba8d017

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength == (-1)) || (replacementLength == ((EMPTY.length()) - (text.length()))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Lang39
### Patch Diff Hash-SHA-256:

b48a4b86e8f8e97d47a87b68fde2278f47426b37d00c2288d28213953ab544d5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength < (text.length())) && (replacementLength < (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Lang39
### Patch Diff Hash-SHA-256:

5042c3818683052ad81f2a63db7b5e467202b88e6eabeb2c9233ce712e2d8dd8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((((text == null) || ((text.length()) == 0)) || (searchList == null)) || ((searchList.length) == 0)) || (replacementList == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Lang39
### Patch Diff Hash-SHA-256:

434ec0f81785a90c968708e5b0d490bf8bdae4f458b24b798fc91c0181ae0624

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == ((EMPTY.length()) - (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Lang39
### Patch Diff Hash-SHA-256:

18ad58e4dd60a5319712b3b3f51f92b289581e28860fdaeda79757c76cbb1cde

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Lang39
### Patch Diff Hash-SHA-256:

fa415c2fc7f0e1f5f833d14e66e7fc672d91383851c6819b60917a0501d45217

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.CharUtils.isAsciiPrintable(text.charAt(start))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Lang39
### Patch Diff Hash-SHA-256:

942909879afed4519f8ffb175c1c372c1ebd6458ba0fa3c70fa40451a9b32b98

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Lang39
### Patch Diff Hash-SHA-256:

1534e1b0984afd3b7841733d6ce14fd9dd14a324a9ad506a9d9257a0f52c55a6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex < start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Lang39
### Patch Diff Hash-SHA-256:

96b6cbf6fd4d6c6a6522dc5b48fcbd80826005571e0beaea09eefde7e7d7d8e1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Lang39
### Patch Diff Hash-SHA-256:

7a4956db065a813c9520cebdaa2571a399276adba2fbdbf5ce52f48d5215123b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Lang39
### Patch Diff Hash-SHA-256:

155fbc2a85abdbc26b1d12fd8782408f1d5023f35273a3223eb0b41131e3d0b9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != replaceIndex) && (java.lang.Character.isWhitespace(text.charAt(start))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Lang39
### Patch Diff Hash-SHA-256:

49a26a9aee0d27802f2376ff5b003bb21088c7d542898262ae25b36231db1b1e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Lang39
### Patch Diff Hash-SHA-256:

96761cf8af21b18efc6c64b7381104a37e1156f24da3a8732789a70c650e8b70

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex == (java.lang.Character.LOWERCASE_LETTER); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Lang39
### Patch Diff Hash-SHA-256:

1fb54de04a314f6c5f86bf82cde91be25a1f14f4739b4d16cd7714b6c7cd5aff

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex > replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Lang39
### Patch Diff Hash-SHA-256:

4fc2d533648aae5ee1eaded618d46e5f11a9cfebf466d25eccf199f883475d76

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList[0]) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Lang39
### Patch Diff Hash-SHA-256:

8e0b95bc37de028303f46a0b6e68cbd463f18c95dc70d5d37e0c0afb8ccbb8a2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; repeat && (start == (java.lang.Character.LOWERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Lang39
### Patch Diff Hash-SHA-256:

66fb876a72be6fea66ce1310e468de285978b07b05d86408a95878bac287c46d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetter(text.charAt(increase))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Lang39
### Patch Diff Hash-SHA-256:

c05da005059fc5b7b1fa6029ca61c95ec8018e4f6e88bdc3e056616cf3a9aa52

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength == (-1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Lang39
### Patch Diff Hash-SHA-256:

10b81ea6072d66f4321625fee77a80415c264f0d15c2da430177896026f267a4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength + ((PAD_LIMIT) - 3)) < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Lang39
### Patch Diff Hash-SHA-256:

7ee735a360b54286a1d45938a01d5dc82554a1dbb1ee3e651777e4c50c160c08

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList[increase].length()) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Lang39
### Patch Diff Hash-SHA-256:

c974046560d25e8c95aec86306ee791ef90ce9b12c89808d607dffe0700f1fc0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Lang39
### Patch Diff Hash-SHA-256:

af860478392afaaa8f1c7c489f12a79e6044e090c0dfb550d6fddc629461919c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList == null) || ((PAD_LIMIT) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Lang39
### Patch Diff Hash-SHA-256:

47b4a62f03f7ef889310bae1b4299313645198882cefea037287b255b7bc5c21

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) == (-1)) && (tempIndex != replaceIndex); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Lang39
### Patch Diff Hash-SHA-256:

c50ed2037f7b112665fdee4d6668641298ee9ee06aa16e1b13948aee0d4fb817

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) == start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Lang39
### Patch Diff Hash-SHA-256:

9c0e8384236a831de6ee5742be35fd06d00a6f2c04b159adfd7d88e3efaa7899

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Lang39
### Patch Diff Hash-SHA-256:

99946389db52c22afc7d3edd38bba36942943a174ddb79ac316bcd3e5f311569

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; repeat && (tempIndex == (java.lang.Character.LOWERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Lang39
### Patch Diff Hash-SHA-256:

75cd460603fcdbebf474161a92377c20c3f7d2732f9638d82540b516541ffc61

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength == (-1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Lang39
### Patch Diff Hash-SHA-256:

0c71b5ccc48449356ea51d87dd7c682d75ccd5b882460b4c892139045742a03b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex == 1; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Lang39
### Patch Diff Hash-SHA-256:

5e2ee4e027775540ebc616cae2cf5db612f38b9aeadadb0246383efd4f6b9991

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) && ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Lang39
### Patch Diff Hash-SHA-256:

594eeba938d9b79274413ec7467cb229df8d239487c125342f4da8b53cb62c5c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(timeToLive)) != (text.charAt(timeToLive)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Lang39
### Patch Diff Hash-SHA-256:

d73d48f77490533a4cc8836fb5cf354d40970438ef2090006244fdb7a456bae7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength == 0) && (!repeat); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Lang39
### Patch Diff Hash-SHA-256:

142e61ff305cff26dc646b2565d6016b73f6d5941a96df95c893803b0f005070

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (timeToLive < replaceIndex) && (timeToLive != 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Lang39
### Patch Diff Hash-SHA-256:

300ea63b6e13a5fac3cd0202f9b97d7b4686a982ae8e42c52435777123f5c8c8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((searchList == null) && (searchList != null)) && ((PAD_LIMIT) > 0)) || (((searchList == null) && (searchList != null)) && ((PAD_LIMIT) > 0)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Lang39
### Patch Diff Hash-SHA-256:

13471ddb0c7d90f2146875ce0febc50cbf7c955dca7ef164794c03c76e3e91a7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((timeToLive + (INDEX_NOT_FOUND)) + 4) <= (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Lang39
### Patch Diff Hash-SHA-256:

32aa2182720ecf0875f834b9d9cd4710d63fc5cf3cfefa190b028db8416f2063

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != 0) && (java.lang.Character.isWhitespace(text.charAt((start - 1)))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Lang39
### Patch Diff Hash-SHA-256:

741640029e0182ace2df1f99675170e3f6ab54de0ff03efcbb8300cfe6834c94

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex > 7; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Lang39
### Patch Diff Hash-SHA-256:

d4dd5ab2f51beabe575bd30d258551ff2270e0e1fca118ee55ab15e506f826af

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.getClass()) != (text.getClass()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Lang39
### Patch Diff Hash-SHA-256:

fcf945abc931db5aa5b30f644703f9666dc36cecb7899f939df12b716561bfef

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > 65535; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Lang39
### Patch Diff Hash-SHA-256:

6fed1526441007828ff4619777a12ef4cc1f7d20acc8d1de66441ea0feb1a1db

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(0)) == '-'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Lang39
### Patch Diff Hash-SHA-256:

ddbbfcd0f01c7284cd9da809e7527d4dd877459611006dde7a4a83cfdb854a6d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "on".equalsIgnoreCase(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Lang39
### Patch Diff Hash-SHA-256:

f3ffb32550eb5041ccc06dbd004abba47b19437c30df23f4576fa8d22e9039f2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Lang39
### Patch Diff Hash-SHA-256:

7e69f8f2778a3a5f2c674dab2a297eee146c2b445735cc0718369fbb381972d3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.StringUtils.isNotEmpty(EMPTY)) && (!(org.apache.commons.lang3.exception.ExceptionUtils.isCauseMethodName(EMPTY))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Lang39
### Patch Diff Hash-SHA-256:

64089bf6b875b687104b1022bea32b4b79bb101b729ed82fdf3f80a00656867f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex >= 6; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Lang39
### Patch Diff Hash-SHA-256:

09f15b432bded73ed6a8307ec0be3e5bab4bfa579cb5e1daec131bf15b4ed976

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) && ((EMPTY) == null)) && ((((text.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(text.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(text))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Lang39
### Patch Diff Hash-SHA-256:

d7e7180a5eec3d2fb17d7d558c51e9bd89ef3ce7ab4eac8ff06078b3636f86c8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) == (-1)) || ((PAD_LIMIT) == ((EMPTY.length()) - (text.length()))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Lang39
### Patch Diff Hash-SHA-256:

ef701492061d82b82c1051140a3ba376f8b9058606a69c886a6c61b3a29a9338

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "false".equalsIgnoreCase(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Lang39
### Patch Diff Hash-SHA-256:

81ae1326296afd8fb2f2049b764c1a79784befc37d3a1a0aaa322f8f1559576c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList == null) && (searchList != null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Lang39
### Patch Diff Hash-SHA-256:

cbe2f7e8bcacbb41d7fcf6d9e1ddb88c3b76ca8ba7bdf1eef9cbd4f8073b73c9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((replaceIndex + 1))) == 'u'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Lang39
### Patch Diff Hash-SHA-256:

7380ec5aeb64e27ab81b9ecedef7d6203e5dd1930b890a6fa2eeed00486b98ed

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(text.substring(1))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Lang39
### Patch Diff Hash-SHA-256:

557d2cda7896c6490fe98b367d3f5c6260f61b55335c7623d69d28aa52de3188

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Lang39
### Patch Diff Hash-SHA-256:

eaeed96e05e8ae79e602e9d50ebd333a32efe49faa93af89b4c53b3b362033f7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList != null) && (textIndex > 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Lang39
### Patch Diff Hash-SHA-256:

61cc9d538a62b00a3f8f853c7eb42010104f66ffa729ef85cd3c326e82096834

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex != (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Lang39
### Patch Diff Hash-SHA-256:

c94662eecd06f42a5279af6cf1d3c61fd502df5eb9c7a9354d88ee1f4fcecc6d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(1)) == 'R'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Lang39
### Patch Diff Hash-SHA-256:

f6f7630df467001bffd2cf1645360f0517cda29ec11c83b5b576540dfd4d7b0a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.length()) != (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Lang39
### Patch Diff Hash-SHA-256:

773fdcbc96c8af482384b9df23c6b84e103ab4379a8a6bb94439dd45dbbea7ab

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.startsWith("["); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Lang39
### Patch Diff Hash-SHA-256:

b7dca5e4104652a39c34a5628070c37cad706e3477f57c7cc46c5b2b2f869e10

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.startsWith("L"); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Lang39
### Patch Diff Hash-SHA-256:

3f08d24d4328adcca0a2ddbe4900ea412015aa31d021891960f304e4f59ed2e3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.startsWith("0x")) || (text.startsWith("-0x")); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Lang39
### Patch Diff Hash-SHA-256:

2524bc557d2335f819088bf5480f6dcce7cde69ddb14e91ee4defc3ad0ed5dba

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.builder.EqualsBuilder.reflectionEquals(text, EMPTY, false, null, replacementList); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Lang39
### Patch Diff Hash-SHA-256:

adf3045eef1d850d1cdf3fa2b663732256844588e1aa0150ab69290654860951

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.exception.ExceptionUtils.isCauseMethodName(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Lang39
### Patch Diff Hash-SHA-256:

9bbeae8a44aa806e34936d74d870b5cb9d9888a389ee5376ede19076d9b87d39

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.StringUtils.isEmpty(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Lang39
### Patch Diff Hash-SHA-256:

0c2fbaedad2cd68502c74bb5a816d9f80990ac1609b446d701065a26d07dfc80

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text == null) || ((EMPTY) == null)) || ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Lang39
### Patch Diff Hash-SHA-256:

8a4931b459222579ed8c69c316798ee119be74262b2f1c3235b34507bfa02de1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(1)) == 'E'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Lang39
### Patch Diff Hash-SHA-256:

0e07521ec21d1fa39a179bdad07a77918de6425c0ebfde5b1924c137ac3ecce0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex > 7; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Lang39
### Patch Diff Hash-SHA-256:

a44996cf844ec9b7053f6700c381925b5c5de12f36a0402a963c6eb42a6d53b7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > 255; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Lang39
### Patch Diff Hash-SHA-256:

029c171d3bbdb68a0dde686b9c5a65de7d86c48aff258ce0a496b2943e8079ed

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) < (PAD_LIMIT)) || ((((PAD_LIMIT) < ((PAD_LIMIT) + 1)) && repeat) && (!repeat)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Lang39
### Patch Diff Hash-SHA-256:

0c8e13c9125c527aacce99ac64d8a1d72152ed63d2efd25ea4a1d6712a866f4b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((timeToLive + 1) < (text.length())) && ((text.charAt((timeToLive + 1))) == 'u'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Lang39
### Patch Diff Hash-SHA-256:

5c658f5af1af77db27d7038572e834e83cf85543fb0682fa0e17f435e2ec76b5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((INDEX_NOT_FOUND) > 0) && (replacementLength > 0)) && ((INDEX_NOT_FOUND) >= replacementLength); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Lang39
### Patch Diff Hash-SHA-256:

2bbdfb25883ee6b1f4acda64359c217c46743666058840b6a2c551b986de4099

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.regionMatches(repeat, PAD_LIMIT, text, 0, text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Lang39
### Patch Diff Hash-SHA-256:

bd16e2c019a4ef6de177e69623fd26fa979cd2f55f85295cd4f46d36fb20c1e1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.ArrayUtils.isEmpty(replacementList); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Lang39
### Patch Diff Hash-SHA-256:

fb18eb7a8458819a0bcb007f0cf4b48dbf75d83f141a9a2712a43c041e0d30fa

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.equalsIgnoreCase(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Lang39
### Patch Diff Hash-SHA-256:

03f8ee1d7e397ceb11e921aeb34cf0300ab4b40d61f8277a08c56b3f626413ec

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((replaceIndex + replaceIndex))) == 'u'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Lang39
### Patch Diff Hash-SHA-256:

389d97ec93646338068319fb3ec60a6aa93e8cab72189eb4cc61e24885006bf4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(2)) == 'S') || ((text.charAt(2)) == 's'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Lang39
### Patch Diff Hash-SHA-256:

d1ea5e93cbf52bdb66298dae7fa5ea2cf346f5d1492a75c7d5c83ce739412cdf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex >= 4; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Lang39
### Patch Diff Hash-SHA-256:

4e60b57cf89c90718562eeeb18e3512efc180222cdc8f38d50a041c4e0a87a2e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((text.charAt(1)) == 'R') || ((text.charAt(1)) == 'r')) && (((text.charAt(2)) == 'U') || ((text.charAt(2)) == 'u')); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Lang39
### Patch Diff Hash-SHA-256:

f12a92e70f7b57076c1b295ef415860ba5ddfa0be177a0b9fcd767ccd04cc514

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start - searchLength) > start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Lang39
### Patch Diff Hash-SHA-256:

b95d2601a576342fcb0d4f8259d3b62d565ad036b34cc48ecd40608398e8d3a5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start != 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Lang39
### Patch Diff Hash-SHA-256:

9a9c8c999bc82fcc0cb556254834183a518ed85edb51395a2afd90639a376968

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) || (text == null)) || (replacementLength <= 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Lang39
### Patch Diff Hash-SHA-256:

c6c76b07665e19b3b0aba4dba143cb4e103369fd51313bdbd1d56b97dd83024d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength == 5; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Lang39
### Patch Diff Hash-SHA-256:

962201cccff408c95bd6e6c7189150d2bf3bdd48d0c57bd2b045e1350b84124a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((INDEX_NOT_FOUND) != timeToLive) && ((INDEX_NOT_FOUND) >= 0)) && (timeToLive >= 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Lang39
### Patch Diff Hash-SHA-256:

b0172a71fa23ac7c178501d5494761b0e6aaf138cfd212eb18b1c588a0d1fb39

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength != searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Lang39
### Patch Diff Hash-SHA-256:

5ee84a4c6a0f79a3b216c01b7a9a896eb0b0e3c35bad91759a3f434be8a06883

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetter(text.charAt(timeToLive))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Lang39
### Patch Diff Hash-SHA-256:

c2ec59987495017f4526c0abe6a9788ef74bd2a7988d1c82e13fe5b453889de7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Lang39
### Patch Diff Hash-SHA-256:

9b4d1739fe4c4a117cfcacc7d22600180849d321775e3d69aaca68749f09929f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(0)) == 'L') && ((text.charAt(((text.length()) - 1))) == ';'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Lang39
### Patch Diff Hash-SHA-256:

a927ecbccfc2da047cf2673c977161677f01072fb10172091f3f07e0977c5e09

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(2)) == 's'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Lang39
### Patch Diff Hash-SHA-256:

c9ad82b82ecd5280309ca9c944408c5f6710bb61552e2fae931ba1df8d70be56

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (timeToLive != 0) && ((EMPTY.indexOf(text.charAt((timeToLive - 1)))) != (-1)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Lang39
### Patch Diff Hash-SHA-256:

a43bd9f64a341ee16555100a781011fb1f0230e28ebd6193659a4a774001e020

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > 64; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Lang39
### Patch Diff Hash-SHA-256:

11802ab3c4a6a8d1a26bc682f98699f4a1ca0bca8b13eb2f5b1f013d86179947

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength == (-1)) || (searchLength == ((text.length()) - (text.length()))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Lang39
### Patch Diff Hash-SHA-256:

27e2815905d0b020808bd8bf39f048df74e4c9695bf76f8895192505c1e7b143

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "yes".equalsIgnoreCase(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Lang39
### Patch Diff Hash-SHA-256:

01cd5b7d26b8804b86f5f4f0a2767a72c4c006ad1640f8185702d98250d592eb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (timeToLive - searchLength) > replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Lang39
### Patch Diff Hash-SHA-256:

7b294262a161c336c584292c1863dbe8bb36eca5906b99eda5288c082d7b22ff

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == 1; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Lang39
### Patch Diff Hash-SHA-256:

5801ea0e7c8755f82128aff2b748d81386a581eefcf7d6f360edcfac0c3ab02f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start >= 0) && (start < (INDEX_NOT_FOUND)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Lang39
### Patch Diff Hash-SHA-256:

78b3e6d7db2bce359d16bd45fa65fea09c745677e122f04d24a6b5277ef21e08

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Lang39
### Patch Diff Hash-SHA-256:

fa9d92a91fa3315636cdf29715634e4de08c2f7c80b6e753e61ea6edce8c8cf7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.length()) > 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Lang39
### Patch Diff Hash-SHA-256:

f700255b0c43e23d6576f8669fa16a505a895e2880913f2e5a8867bcda8e7a5f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.getClass().isArray(); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Lang39
### Patch Diff Hash-SHA-256:

dee2e7653241f05437ff15ea94c50dfed0e9625fab8feafe99c6e38bdedc5966

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < tempIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Lang39
### Patch Diff Hash-SHA-256:

9232bb157519e03b5cc22a956cbaa1bf68248a8c6b5aec36084195c1c12ffe7b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase + 1) < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Lang39
### Patch Diff Hash-SHA-256:

808967d0c301429b85dd2b2edfbec5eef7e80d1070fea5b127ae08c17a2bd51d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(2)) == 'U'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Lang39
### Patch Diff Hash-SHA-256:

426fedc4ff104191ea00138f69f4a0476b3fd7e09cabae52e0c34bfa92dbc971

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.CharUtils.isAsciiPrintable(text.charAt(increase))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Lang39
### Patch Diff Hash-SHA-256:

a52c4f5f231483971f992c5cfcfab6ed67a309bbea4c93e331f322de10dc30a5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Lang39
### Patch Diff Hash-SHA-256:

27a8f6b60f3b5c322bfd7976cc9625a03a481d07334253a9765232c7518696e1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(1)) == 'E') || ((text.charAt(1)) == 'e'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Lang39
### Patch Diff Hash-SHA-256:

8443f068b6e457acf9f549c8434f09e1da914bd6ee04979c5869db41b71a4959

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex == 2; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Lang39
### Patch Diff Hash-SHA-256:

74f423dd99737ac349364d92cbc5e7eced509bb1d0b1fc7681282290677f75a1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex < ((EMPTY.length()) - 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Lang39
### Patch Diff Hash-SHA-256:

668fcf69b0c1759c128e169db53d632c462f13731e298b0535ee627798d313fd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "false".equalsIgnoreCase(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Lang39
### Patch Diff Hash-SHA-256:

a8f07df31c177de8c97618d0b0b08af3c77cead78bb9415d9af59506e201e164

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex > (PAD_LIMIT); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Lang39
### Patch Diff Hash-SHA-256:

3b3d66a306ae0f34786cde3e3542298442d34ecc05b2cff8500fa3c41d325a31

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(timeToLive)) == '\\'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Lang39
### Patch Diff Hash-SHA-256:

a7532a18982198c1413b925ff072102b2b087169853189e5124c68867011e550

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex >= 4; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Lang39
### Patch Diff Hash-SHA-256:

3ff657524a1bce7ed495a9eb3b0238d7e7ec36ae51cd641e4ca4ec27b92a7650

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < timeToLive; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Lang39
### Patch Diff Hash-SHA-256:

4cbd7ee3c8ecbab488fe2c3aaa2d1deaaffad18a3c5112f17fe71395334e6d34

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLowerCase(text.charAt(increase))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Lang39
### Patch Diff Hash-SHA-256:

1d6cefb8c9d5f6d7730bb079714ad0cea392b22ee784258511467675ec89c930

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(2)) == 'U') || ((text.charAt(2)) == 'u'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Lang39
### Patch Diff Hash-SHA-256:

823d508a7a5719a9c4055c6d5186cb759a9aa363551195080678ce385109fcbf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength + 1) < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Lang39
### Patch Diff Hash-SHA-256:

28f3271684d00805d7c2577901776f7b212a05379a7663d0f304fedbee369734

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((PAD_LIMIT) + (INDEX_NOT_FOUND)) < (EMPTY.length())) && ((EMPTY.charAt(((PAD_LIMIT) + (INDEX_NOT_FOUND)))) == 'u'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Lang39
### Patch Diff Hash-SHA-256:

13dee92763490342582f7105a49aa495ad31af5b6c1010ed8d594ee9fe5ea246

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((searchList == null) && (replacementList != null)) && ((INDEX_NOT_FOUND) > 0)) || (((replacementList == null) && (searchList != null)) && ((INDEX_NOT_FOUND) > 0)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Lang39
### Patch Diff Hash-SHA-256:

e903f1ec7a6284149619ff6821d8828ebe82be5db6786b9437dfc05fa9815d82

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= timeToLive; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Lang39
### Patch Diff Hash-SHA-256:

fa87b564965289db3b29ac80cd37c3bd5387e777bda1e273ff25ac2bd520b355

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(((INDEX_NOT_FOUND) + 1))) == '#'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Lang39
### Patch Diff Hash-SHA-256:

c615cb47f4dbe493e648dcce6ff67bdcb7f60634a77cc14051ef1dcf097f6e7c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Lang39
### Patch Diff Hash-SHA-256:

818980cea27e770ffddd6e043cb3e63295b50edf64beda963b4f7ca744c3ac02

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((((text == null) || ((text.length()) == 0)) || (searchList == null)) || ((INDEX_NOT_FOUND) == 0)) || (searchList == null)) || ((INDEX_NOT_FOUND) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Lang39
### Patch Diff Hash-SHA-256:

04acd914b581aa60dd36a5b24623542aa9118e47116e0474c4cce2f7bb56a1dd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((searchLength + 1) < timeToLive) && ((text.charAt((searchLength + 1))) == '\''); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Lang39
### Patch Diff Hash-SHA-256:

0c0cca05b3d36331908ecd8c28ee5fee1403dc19369ec1ad8b8cc00f2f3040b0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "true".equalsIgnoreCase(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Lang39
### Patch Diff Hash-SHA-256:

1c54688e9c7737c96204bb5342556ec71283a8847d55834b2421ce7487b377fb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text == null) || (text == null)) || ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Lang39
### Patch Diff Hash-SHA-256:

54a54f1557515ee4a25db596fb63407dfc1227fc6bf93f8d764d6cdf15d652c3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.length()) != 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Lang39
### Patch Diff Hash-SHA-256:

f3bde95cc63d01ff456457b1b48d267f944b7c50d7ececb056ab97b7d8d5ed75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replaceIndex < 0) || (replaceIndex > (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Lang39
### Patch Diff Hash-SHA-256:

ab1895ff6196116ad348f566330eb25a11476319b71c56f7f2f2fa7786ae0e70

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((tempIndex & 1) == 0) && (((INDEX_NOT_FOUND) & 1) == 0)) && (replaceIndex < 31); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Lang39
### Patch Diff Hash-SHA-256:

739a146c96325516f3feb4b6feae578810c2d03ae80969a3ac0a4239cdc0f412

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.equalsIgnoreCase(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Lang39
### Patch Diff Hash-SHA-256:

5f0083a635cc6530f3722ba0b93e6f611e401ad0d9c2e3fbeddc6e91e64a731f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text == (EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Lang39
### Patch Diff Hash-SHA-256:

3d94652b1c68cbdcfcb6c1ed5a2c1efed9d0e09e656be1b9b26f938e735098cf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || (replacementLength <= 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Lang39
### Patch Diff Hash-SHA-256:

3878d6f3c3d30721944e8cb9c252faf15817b3f562cf0203ed64f20ad1186090

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((text == null) || ((text.length()) == 0)) || (replacementList == null)) || ((PAD_LIMIT) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Lang39
### Patch Diff Hash-SHA-256:

bf2787f248687ad1f582d41b456a965efbe2ed58736b01a02165bd7004eba3e6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (!repeat) && repeat; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Lang39
### Patch Diff Hash-SHA-256:

2afddf169c49f68229d4edb70873903fb06154bffe9a2bc35b1c5651cbc5fc98

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength > (PAD_LIMIT); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Lang39
### Patch Diff Hash-SHA-256:

c877b512ba2f80c5912f39d08edab00aec039fe3f44ad2a383e3ee8f81c89480

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLowerCase(text.charAt(start))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Lang39
### Patch Diff Hash-SHA-256:

adf6a0feaa1a11c7c38b62387d3bc013ca562d696327810cf6b7ff453f3921f8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex >= 15; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Lang39
### Patch Diff Hash-SHA-256:

3c79490762be1e06469c3b068fe591ae5019c4328b0198b0a0419b4248e21335

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((start + replacementLength) + 4) <= (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Lang39
### Patch Diff Hash-SHA-256:

7565e4985c5a25573333d803769fb621bc4f874f871533bee75bd678fe9911b1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (--increase) >= 2; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Lang39
### Patch Diff Hash-SHA-256:

1aeb846bee9ba6e7196cc2d5f526adbe80285a4abe54d2f4fd5ad7813a52d313

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.endsWith(";"); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Lang39
### Patch Diff Hash-SHA-256:

c6c3f3f371adb1618a46df1874f8f7cb8e6efc9cf4b8033f5499862a0a2cb5e7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; new org.apache.commons.lang3.builder.EqualsBuilder().append(EMPTY, text).isEquals(); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Lang39
### Patch Diff Hash-SHA-256:

cbb4686560b36552dc8797e443da478e3ed3698034d7b56e6d57571043c2b1ae

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive == ((text.length()) - (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Lang39
### Patch Diff Hash-SHA-256:

9ce50cb95739072a46a7057fd0c76fdfb1892da817d6f36c79b0c02bc7154517

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase != 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Lang39
### Patch Diff Hash-SHA-256:

d418fa0dffc7786289cc43157de6d4cd0f2519cc0d233841c3c5104ad679810b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.builder.EqualsBuilder.reflectionEquals(EMPTY, text, repeat, null, null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Lang39
### Patch Diff Hash-SHA-256:

a65e70fd7502cdfd7234ae77d1cc22b28fb7ff532d4f4c9034e4492d7c060e80

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex > tempIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Lang39
### Patch Diff Hash-SHA-256:

97c4254a72e7a1608c479b419d11cfb08dc0b576a191c4f6f616c91bd11cf76b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((tempIndex + 1))) == '\''; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Lang39
### Patch Diff Hash-SHA-256:

39cf123948d6aa55eb712cc9d162fba096233f099002452a3210732c34cb4163

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((text.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(text.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(text)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Lang39
### Patch Diff Hash-SHA-256:

ea9a6941e6791d2883252c5a129f4bae9f16cf417a6c174ae0a6f30df0bdb28d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; new org.apache.commons.lang3.builder.EqualsBuilder().append(text, EMPTY).isEquals(); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Lang39
### Patch Diff Hash-SHA-256:

0c0ef63a0a604e0a6034f9e8a825a2aa326255126d7e9d18fd7d9643a21d435d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex < ((EMPTY.length()) - 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Lang39
### Patch Diff Hash-SHA-256:

dd28755836f3e109d377d998adfeceaa3f02ba6ce3854a05020a1302984abedb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetter(text.charAt(start))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Lang39
### Patch Diff Hash-SHA-256:

992b53740710d9d722ecc87bde373401453e2a4c54cecd2adc067ae6df14b4fb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(1)) == 'e'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Lang39
### Patch Diff Hash-SHA-256:

6ddb45c30fd11a5828ca09918c5f513ca47d5ed69865b0f96ab5a515f31d1a87

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.regionMatches(repeat, timeToLive, text, 0, text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Lang39
### Patch Diff Hash-SHA-256:

96cea5465e6ce35e10dc4bc504e3dcc9e600cdcc79e5a076ea219c6a2543918b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replaceIndex < 0) || (searchLength < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Lang39
### Patch Diff Hash-SHA-256:

1b14997fc52b16b56a2c1141cf8827466d3f63d4fffd2924c95c315a4f742a75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (textIndex < 0) || (textIndex > (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Lang39
### Patch Diff Hash-SHA-256:

8191b7de2d729455e1d67b30855c9fd5c4f5b5cae246435206ede87687599343

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) && (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Lang39
### Patch Diff Hash-SHA-256:

e2b5fc6e3e60bde5daa9a123e138c6fc6473266e60c0e29e1c4a1cb807c5e46b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) < timeToLive) || ((((PAD_LIMIT) < (timeToLive + 1)) && repeat) && (!repeat)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Lang39
### Patch Diff Hash-SHA-256:

4f623af61402d1acd583ce0cf839d6da6c2fcdb3bbbd6ad4ef97899381b6e5d5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < (replaceIndex - 2); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Lang39
### Patch Diff Hash-SHA-256:

afc7f6c477df835358d513c616a590ad3b8be1c6e2d4b061a5acde0ad8a1e667

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(2)) == 's') || ((text.charAt(2)) == 'S'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Lang39
### Patch Diff Hash-SHA-256:

dc9233bbef242245b884bb98451309daa0e10ea4347f30d2181a3cf448557b75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text == null) || (org.apache.commons.lang3.StringUtils.isEmpty(text))) || (org.apache.commons.lang3.StringUtils.isEmpty(text)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Lang39
### Patch Diff Hash-SHA-256:

d0edb3025fe40462b100a32a3ef6038dd2ed3428fb08b888967b88edb5a6fba2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.startsWith("L"); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Lang39
### Patch Diff Hash-SHA-256:

4e39ac85332b5ea1a393b7bddf4ba1551081177f40e66ca6d29f398fc8b8114b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Lang39
### Patch Diff Hash-SHA-256:

71f08e11b428de65e9a78a65c1caf7dd4ae91a0e00162c01b9bcc92e5a2b55d3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.exception.ExceptionUtils.isCauseMethodName(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Lang39
### Patch Diff Hash-SHA-256:

2d4ff1e91b74bdee2bc74516d6ee5be28ac0d2c52e0511dac2e74d782be5ffc9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList[start]) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Lang39
### Patch Diff Hash-SHA-256:

d801a167047e54cc9e644972cf707565d7c93769f77981ca461e5dd96c0dad84

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) && (text == null)) && ((((EMPTY.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(EMPTY.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(EMPTY))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Lang39
### Patch Diff Hash-SHA-256:

c7a7efc0db5a61796f353ad93507cd5421f1dce3f3ca3d92e71d0ec6e110a680

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength + tempIndex) < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Lang39
### Patch Diff Hash-SHA-256:

b49a8692ae3a81e03d743ece7dc1aed6e4b8b356dd843c6787439683f71f9705

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (textIndex >= 4) && ((EMPTY.charAt(textIndex)) == '^'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Lang39
### Patch Diff Hash-SHA-256:

769eb7b337f663c1ae220550d1ed2f1b4f6cd81950bd1f76b5685026fdcabb8f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.getClass()) != (text.getClass()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Lang39
### Patch Diff Hash-SHA-256:

23a2c91a324d2ccc646b1d28167e35d8919e8c8101696c0cfe7073dfaa363a72

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Lang39
### Patch Diff Hash-SHA-256:

9c1a9064fb5e15b14990a36a17c5c1a3f440717cf9bc12380bc60ac457c20cbd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start++) == searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Lang39
### Patch Diff Hash-SHA-256:

324d5d9bbdedc3db00bdce32795179de030081dd7d65b93a1a5d46d32815e12f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList[0]) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Lang39
### Patch Diff Hash-SHA-256:

ed527b812658320a3bf925ef42c49166887a180cb8137ca98f7ab7eccf250fea

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(1)) == 'r') || ((text.charAt(1)) == 'R'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Lang39
### Patch Diff Hash-SHA-256:

350b1483e48ecd3441a9eceea8ec5fa375389f8108a8c63381adbafb661a84e1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "off".equalsIgnoreCase(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Lang39
### Patch Diff Hash-SHA-256:

a26b16dcfa2c0396b77b4ac279fd129dd8f0ab56a956cd7a5f26d9881dfb522c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) < (text.length())) && ((PAD_LIMIT) < (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Lang39
### Patch Diff Hash-SHA-256:

e8a3780f1b17b726a1361892820b653fcc6900e5a6c66a96be3c80a114621e91

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) >= replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Lang39
### Patch Diff Hash-SHA-256:

c2e03bcf4d7d6416529e32a8be48b910b368165f0cf35cc6e23201e0649f20d9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.math.NumberUtils.isDigits(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Lang39
### Patch Diff Hash-SHA-256:

0eb05e83839e7f23b3e178b650e15a8ca2d80a592a09decefaada6edeb0ffeca

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.regionMatches(true, PAD_LIMIT, text, 0, searchLength); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Lang39
### Patch Diff Hash-SHA-256:

66a26760d959813ae4fc86544ad64f85c4175ef85888f4b9c6ef0a90560cd5ee

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.math.NumberUtils.isDigits(text.substring(1)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Lang39
### Patch Diff Hash-SHA-256:

0ea7514c53e368ab766d13b3cde523c8ed949fd1b33b73743477461a2334101a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.endsWith("[]"); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Lang39
### Patch Diff Hash-SHA-256:

af91218542d806847c0e0f51460492ee7736d926fb038aee22b5df1f49d59991

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(0)) == 'L'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Lang39
### Patch Diff Hash-SHA-256:

a9e77c8ae5fba64d55e97d69fe2f07ce5eb82c30cb0e8955ca2925878239c60b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((((text == null) || ((text.length()) == 0)) || (replacementList == null)) || ((INDEX_NOT_FOUND) == 0)) || (replacementList == null)) || ((INDEX_NOT_FOUND) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Lang39
### Patch Diff Hash-SHA-256:

ebb17e3ba8ce59c85360fc17b466370b3123a1e178e45f4ad7ea2e6cf793cf6c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.equals(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Lang39
### Patch Diff Hash-SHA-256:

ab03eeb48235db966bdd6b3d2027f7cf491f9ffd5f75323faa3bb2d884a5c6a4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Lang39
### Patch Diff Hash-SHA-256:

ce9d01af911b3953dfe012e37a2763992e0ddccd64b9cd8ecfdd5c9f57f38cdb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.StringUtils.endsWith(EMPTY, text, false); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Lang39
### Patch Diff Hash-SHA-256:

0ef717e680a60a66ca9ea121387941fb426478b3052e19f5ff7c2a878859eea9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.StringUtils.containsAny(EMPTY, text.toCharArray()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Lang39
### Patch Diff Hash-SHA-256:

b1215d0655852b5046404485d2151a887e4e895dfad08aa5d56fc1004846067a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) == 0) && (replacementLength >= (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Lang39
### Patch Diff Hash-SHA-256:

4df081cb25837643fe9f3cf153a9d1602f2d87d2c4da85094a15d307ce5bf195

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start == (-1)) || (start > (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Lang39
### Patch Diff Hash-SHA-256:

42d45e3ca1eee5ac5e922e471afe7c63b5012546ee67e3df44581caf53825692

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Lang39
### Patch Diff Hash-SHA-256:

9f099fe4b2a43ab108696cc05bf2052861406b425020dbde97f1bee5712a3857

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((PAD_LIMIT) + 1) < timeToLive) && ((EMPTY.charAt(((PAD_LIMIT) + 1))) == '\''); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Lang39
### Patch Diff Hash-SHA-256:

561aa8e9f1df4a6b96991ab3983248e810d7d68ba88a3ef32145135df840bfea

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(textIndex)) == '^'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Lang39
### Patch Diff Hash-SHA-256:

7cc5db2d260cda9b474f7cae8994deceefd6f1db14835bcd3e37e5aa4414ea1d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Lang39
### Patch Diff Hash-SHA-256:

20179dce2f534bf542b04d73889a8bd6503b45f0c2251a16b7082f49a76d0063

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength <= replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Lang39
### Patch Diff Hash-SHA-256:

b117c375668e376f51c9a94f51569b1eb6041b13d5fd12af42870b026e9fb6f1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength == 0) && ((PAD_LIMIT) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Lang39
### Patch Diff Hash-SHA-256:

544ae0f40969da5cd9afeee3b66ee6811599a85e47a5cdd5b42cbdb0e56d9c09

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) != (PAD_LIMIT)) && ((text.indexOf(EMPTY.charAt(PAD_LIMIT))) != (-1)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Lang39
### Patch Diff Hash-SHA-256:

56a23b43eae41f415e13db7ffc82bf0aa7a1142e44f5b2e0bd6c11fb5057492a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(1)) == 'R') || ((text.charAt(1)) == 'r'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Lang39
### Patch Diff Hash-SHA-256:

4719332cc7d827a2571f6d6d4fc749752afa0a151a5910092582fc82f37f1c09

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) == 0) && ((INDEX_NOT_FOUND) >= (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Lang39
### Patch Diff Hash-SHA-256:

69a5c38d8fd71086377343642d7d8d8f5e057a8f0fd2dc12dd144108c2eebe8e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text == null) && ((EMPTY) == null)) && ((((text.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(text.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(text))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Lang39
### Patch Diff Hash-SHA-256:

d1ccfeee915a07fd756fb7e0f69cddcef6cad61014357177edafcbe64dd5941c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start + 1) < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Lang39
### Patch Diff Hash-SHA-256:

4f5f3e0bf1d7e6080946f8873231d42575f1a7484dd806982f9da6fc1ea8425b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex > (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Lang39
### Patch Diff Hash-SHA-256:

2de35ffac3922862357db2e9aabc418c8e2f62cccf694f1bbe31a04f5168b5b4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(2)) == 'S'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Lang39
### Patch Diff Hash-SHA-256:

640e7e2dd250914880df5a7ec658462879d5cdf0b9d9bdb61f66561d18c0aba8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength == (replacementLength - 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Lang39
### Patch Diff Hash-SHA-256:

bc5b35cce7ffce7030f62f013f79badce3cda4a61e801d89819b024e9b3dea63

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(timeToLive)) == '&') && ((text.charAt((timeToLive + 1))) == '#'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Lang39
### Patch Diff Hash-SHA-256:

2977012a9c10ada40634c567ae4ebc2e21218e2c36e3aa1f7d23ff111218285d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "no".equalsIgnoreCase(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Lang39
### Patch Diff Hash-SHA-256:

9321d5e56b2f40a3f186aa158676976daa359eca9643cb994ceafe2c7abcbb3e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Lang39
### Patch Diff Hash-SHA-256:

6e43b5b7a70a9bd2518a06c7c428389d6e8ce471faa8cb0e352c135df835b950

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.regionMatches(repeat, PAD_LIMIT, EMPTY, 0, EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Lang39
### Patch Diff Hash-SHA-256:

9ecbee8462110880942c7ecc54429a930cec9feb66d0c0089558952c8ae37b7a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((((searchList == null) && (searchList != null)) && ((INDEX_NOT_FOUND) > 0)) || (((searchList == null) && (searchList != null)) && ((INDEX_NOT_FOUND) > 0))) || (((searchList != null) && (searchList != null)) && ((INDEX_NOT_FOUND) != (INDEX_NOT_FOUND))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Lang39
### Patch Diff Hash-SHA-256:

f2c6b8dcb01ce05fe6f2144460c017574931ab7c585fb5d641436b85b694065b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength < (text.length())) && (searchLength < (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Lang39
### Patch Diff Hash-SHA-256:

b0868978e4d92ef30daa425669d00d2b723bcac0be8f5fa4b0c646d8e3365fb8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((textIndex + 1))) == '-'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Lang39
### Patch Diff Hash-SHA-256:

e43e1d324c729b45bdd435a4c8b5651da19eb69234db44a7c7fdf74b228a3416

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < (textIndex + 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Lang39
### Patch Diff Hash-SHA-256:

a196a6bf38ea60896e1c52fd7cf8ec53e3ccb6a37383cd094ffb7dfb072e9506

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) == 0) && ((INDEX_NOT_FOUND) >= (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Lang39
### Patch Diff Hash-SHA-256:

bea1c11661d5a6a5eab6cb41cda069d64da4f625eaaa734b98626185d29b12ea

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.equals(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Lang39
### Patch Diff Hash-SHA-256:

3529146a71f7f9a13948c0fffc4bd9eebb5062def6da452c734aafbb78a35176

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) != null) && (increase > 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Lang39
### Patch Diff Hash-SHA-256:

d2989381a71bf883a94ad8d44cc650834ce3df8e63ca09c5112fdacd187e044e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (timeToLive >= 2) && ((text.charAt(tempIndex)) == '^'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Lang39
### Patch Diff Hash-SHA-256:

5cc23789a2df9a491c090d2a2d5cbbbf05de57cbbccb71996ff80f3e32fc26b3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.getClass()) != (EMPTY.getClass()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Lang39
### Patch Diff Hash-SHA-256:

7b2447936e2cdeb4907dd380b799fec4ce8e70c0171e91c213c944900fdd21f0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex == 31; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Lang39
### Patch Diff Hash-SHA-256:

0ba7df3590be75a0d2fbeead51cf96393442dac3fdf536ffcf3cee8289272ac0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(2)) == 'u'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Lang39
### Patch Diff Hash-SHA-256:

c80672f068f99cf9344de588a712304547e5bf1c8254a52ee6d33e0666366dbb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.charAt(2)) == 'u') || ((text.charAt(2)) == 'U'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Lang39
### Patch Diff Hash-SHA-256:

1cb5c3303d05b548104634fb24975faf3b52a868507b174acdc2cba2a4214b72

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((replacementLength + 1) < searchLength) && ((text.charAt((replacementLength + 1))) == '\''); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Lang39
### Patch Diff Hash-SHA-256:

b20f47cbfac6116ffb0314e12586770bb7939de8e87edea92c9c2ef849c05546

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "on".equalsIgnoreCase(EMPTY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Lang39
### Patch Diff Hash-SHA-256:

986f90562dc7a6d9f05824e73c6295e12748d89fc7897c190e05140f630db785

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetterOrDigit(text.charAt(increase))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Lang39
### Patch Diff Hash-SHA-256:

24d1f6224cf596fe452be118a129853486afd74c7740eb85bb5425208b7c01db

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex != 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Lang39
### Patch Diff Hash-SHA-256:

babf52c292a41e750a1085c2ace7a8e91b0299fa0248dddafdd9d15a3d624f88

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start = replacementLength) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Lang39
### Patch Diff Hash-SHA-256:

b207612fe9563cc297088b0684db86961491dcd109a620df9fa4d8811bf638e5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < ((EMPTY.length()) - 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Lang39
### Patch Diff Hash-SHA-256:

a81d8f7fc366b5f829df19a8a8051e6c9543d137b820ebfe7daa0c19cc08e8c6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY.length()) == 0) && (replaceIndex >= (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Lang39
### Patch Diff Hash-SHA-256:

e03aedf30b1b61de1748ac45fe03abcfdac4f7b4cd4d9ebf9e816c9214798ae4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((textIndex + 1))) == '#'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Lang39
### Patch Diff Hash-SHA-256:

951111387f1fb5ba9ffb94e4a052a01cbee524a3291d3916f173d85b4f8c1f93

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text != null) && (textIndex > 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Lang39
### Patch Diff Hash-SHA-256:

1ed23a828e93e9ab460592bbf407bb7ebc0435f704c937301d51b65bdaf0ef18

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive == 25; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Lang39
### Patch Diff Hash-SHA-256:

32950d233d8a1b8f1c8bb954ba0418675b436db1d08e8f58171ccad5e7fe248d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replaceIndex - start) > replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Lang39
### Patch Diff Hash-SHA-256:

f8bc2e4d7e58dcf9ab0d4776cf99e5aeb17c14c3e7d8982ea5754e97a5be5ea6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) == null) || (searchList == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Lang39
### Patch Diff Hash-SHA-256:

0d3559a31c3812e4665f591c1acc05f6d550ce1e107df924e9fdca0e24de7916

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList == null) || ((searchLength = replacementLength) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Lang39
### Patch Diff Hash-SHA-256:

ab8454a883e5d782b5cedbeeff6e067b5b5d71edf0b3512c8bead042c4772e0e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((replacementList == null) && (searchList != null)) && ((PAD_LIMIT) > 0)) || (((searchList == null) && (replacementList != null)) && ((PAD_LIMIT) > 0)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Lang39
### Patch Diff Hash-SHA-256:

c1fedcf2bc96c6cb5c7e23d0b922ac87723067268e8468edb9b19de6e6a56093

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((text.charAt(1)) == 'r') || ((text.charAt(1)) == 'R')) && (((text.charAt(2)) == 'u') || ((text.charAt(2)) == 'U')); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Lang39
### Patch Diff Hash-SHA-256:

ca31a0dc0b04cfd106f8c99f95c9dbd70103e3a6aa7bd58332b8653744795529

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text != null) && ((text.length()) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Lang39
### Patch Diff Hash-SHA-256:

b2fcb29a7c8cb0b55f4a500f37186d17bb9ed4edd5346ebcc0aa5783d753c5f0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.startsWith(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Lang39
### Patch Diff Hash-SHA-256:

89093df4cfbaef1a424cfd6fb6acb759c8ce5300eed5ff54791f7301c3ff9879

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase >= 2; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Lang39
### Patch Diff Hash-SHA-256:

d905bad4609c6ac7db58c2d00bb8daf85d079bcb16f6159708519fdecf3b2d00

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.StringUtils.isBlank(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Lang39
### Patch Diff Hash-SHA-256:

257676f8beef93f050806d1d8c7ebcc644cfde918d5418db430fa7a4fbea4d61

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive != timeToLive; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Lang39
### Patch Diff Hash-SHA-256:

e8508824a65dedec2ab7e288a65744f6519c141d2d613f9004a5be1a10ec70ae

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Lang39
### Patch Diff Hash-SHA-256:

1cb9071b72cd57d52cd576ee857d6fee8dcf5ef0d65216833febd582d122a53f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength > replacementLength) || (replacementLength < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Lang39
### Patch Diff Hash-SHA-256:

8142e08502ddb3a89d1e355341192ab05345652ab266b7bbe42daaf19332eab3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.equals(searchList[start]); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Lang39
### Patch Diff Hash-SHA-256:

c1275cbd35da404452aa4e24d33fbeb918a7621a8f1bd7298a9e29c9c83a7b66

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.startsWith("--"); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Lang39
### Patch Diff Hash-SHA-256:

3e8168238a81c4986911988b53271ca695358599314d8e06985779d0a8e729a9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) + start) < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Lang39
### Patch Diff Hash-SHA-256:

45944e2981ec4233452b6255fd2a3a1515dcb6d9dd51085297272cbcdc84c727

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength >= (PAD_LIMIT); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Lang39
### Patch Diff Hash-SHA-256:

011fe0f1e2b5da7ac6a1aa29755534270e3c94ab2524d91574af7f5363afc6bd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; !(org.apache.commons.lang3.StringUtils.isBlank(EMPTY)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Lang39
### Patch Diff Hash-SHA-256:

c10323428f9ffb7dd9a5219985e605473d7d14e4ee01df12bc71a5c39436581d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex == 5; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Lang39
### Patch Diff Hash-SHA-256:

51ec32c4f8c5f03711b569e50a2a0e1c26a29b9a7af62d7d71dfd7caf4fe5659

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase == (-1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Lang39
### Patch Diff Hash-SHA-256:

167560a0eeb95499abe4e9ed19a9f36fe2d264cc9db971df199449ab01a1701c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) == null) || (org.apache.commons.lang3.StringUtils.isEmpty(text)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Lang39
### Patch Diff Hash-SHA-256:

ba7897e6df121d0c10525024096c14315847ba10dc37788a342584b868e3f3dd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Lang39
### Patch Diff Hash-SHA-256:

45131a173b64a40c639615d9e634d93c01cbaa3e1ec830c6a68005078e7560a4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) > start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Lang39
### Patch Diff Hash-SHA-256:

5e41e1f253a4772cdc2e547e0b2663317fca7f99397f0ad7e02c366a82f6e382

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) < 0) || (increase < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Lang39
### Patch Diff Hash-SHA-256:

dc066ec50d75d9ed130f93277dd2fd07b86a99b32a16bf23b18ba9826a6dd367

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength > 255; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Lang39
### Patch Diff Hash-SHA-256:

99b46c1528c71084fcc83e2d3e0cbbc140cf9ce33e678d9afc7e0d65f08e08ac

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength == 0) && (start == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Lang39
### Patch Diff Hash-SHA-256:

ab6156e23a5f33f67b3e6c9bb68e695e1349ee78efdbd594999f5785a44377e6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || ((PAD_LIMIT) < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Lang39
### Patch Diff Hash-SHA-256:

9953ecc42c48c64302314a21dd05f676eae16165d858124c0c903cfcfe7d38ac

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) == 0) && ((PAD_LIMIT) >= (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Lang39
### Patch Diff Hash-SHA-256:

a493c23c2cbb541829b882322fb43bf39bdd7bb9376a112281505ee5bec40520

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex == 2; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Lang39
### Patch Diff Hash-SHA-256:

b155d6115e69b8f3bd710e6e2a61c28238f2b66bbae09bad992efbcbff2680a9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; null == replacementList; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Lang39
### Patch Diff Hash-SHA-256:

7a6477082c708d10ba48bb8b0e22f88fb0e8dae5b4bc2df069c93ab74b9b17ea

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList[replaceIndex].length()) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Lang39
### Patch Diff Hash-SHA-256:

4aa35b08acb71b47ecf0437ffe5ee11b3e4eda492f263ec0f353ac525ea65d9b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start >= 4; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Lang39
### Patch Diff Hash-SHA-256:

d5ea182b027245830e11e80999fa652e81f293ab7dcdc737fc7bc35c0ff4c4dd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; "no".equalsIgnoreCase(text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Lang39
### Patch Diff Hash-SHA-256:

937125265d30615048946d00d0bd7df07246c4dd2d97cb394d6493053d8152fc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) - tempIndex) < (tempIndex - 3); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Lang39
### Patch Diff Hash-SHA-256:

4acdbefc91097a4a593bf93b5bf96905cd55df1f324d031397452aad2f68d986

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) > replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Lang39
### Patch Diff Hash-SHA-256:

671ccfa973cd2354716c41cadd33e78bfdf00220a100f8ac1846c15c2aec6e9e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((INDEX_NOT_FOUND) != (-1)) && ((EMPTY.substring(0, INDEX_NOT_FOUND).trim().length()) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Lang39
### Patch Diff Hash-SHA-256:

d26fa929d286afe5861884ef1f17acdbbcee6b392f5ed957be9bf1e991833762

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) == 0) || (org.apache.commons.lang3.ArrayUtils.isEmpty(replacementList)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Lang39
### Patch Diff Hash-SHA-256:

b1e750e2307ec1e6aaec31d76922596f17a77cb5239634158bd3623001f08573

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) >= 3) && ((text.charAt((timeToLive + 1))) == '-'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Lang39
### Patch Diff Hash-SHA-256:

8d3d977f80b7c4ee4336cdc057f7574b830abab8a0cc073197bcd7db9c144888

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || (start < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Lang39
### Patch Diff Hash-SHA-256:

c11191daa5a3724bafa70aeb594e821d5102a8b6c52d25089843827bccd368fe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((replacementLength != replacementLength) && (replacementLength >= 0)) && (replacementLength >= 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Lang39
### Patch Diff Hash-SHA-256:

9b39d56a911084e16c809040c794ba543b72b5ae087c5126a4fecdb68ae446dc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(textIndex)) == '&'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Lang39
### Patch Diff Hash-SHA-256:

987808b7b4fa4df87862119ba1d79074bf49a24f8679ab51a82953445af9a7c5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > 7; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Lang39
### Patch Diff Hash-SHA-256:

0cae60b3592efa75395d7c58afcc6ba4d1615e1f0c73d9c48fcb81fbbaaa347c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Lang39
### Patch Diff Hash-SHA-256:

9e90fd1590307ac016fd15b996d1f6377bec507d461bd81c3cc98c7104866a75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((textIndex + 1))) == 'u'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Lang39
### Patch Diff Hash-SHA-256:

75acb42c5c5428249df2517abfe601fd636c64d4b386a04b94bcccee10263ff2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(((text.length()) - 1))) == ';'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Lang39
### Patch Diff Hash-SHA-256:

263fbf6564a5f8dfa5b922b1407bb292db9da499b0cc353e71bb58087f01ccea

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.StringUtils.containsAny(EMPTY, EMPTY.toCharArray()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Lang39
### Patch Diff Hash-SHA-256:

b0bcf35e1c6128bdcdb602ab04698d464ed15b964337e5256da7e59c5c979d54

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; repeat && (!repeat); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Lang39
### Patch Diff Hash-SHA-256:

a5746faee5de66ae1ac8c4e848cad295dc81e2c4265d76d0a9de3d827b620274

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.StringUtils.startsWith(EMPTY, text); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Lang39
### Patch Diff Hash-SHA-256:

139e3af75000b201479f8370fcdd5a41035f4b5e83f7bddb8bdf8ad441c234ac

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.getClass().isArray(); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Lang39
### Patch Diff Hash-SHA-256:

65a72043d9d6d2b1ba239ec36ba332b43d3c8ec16ed88332fc965f1bf6a91e01

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((increase + 2))) == '-'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Lang39
### Patch Diff Hash-SHA-256:

f8d31d78b8a6023e39c3c2bf7cf7c0a4a0aa947aa750d98119981a370f9a8343

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((INDEX_NOT_FOUND) + 1) < (text.length())) && ((text.charAt(((INDEX_NOT_FOUND) + 1))) == 'u'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Lang39
### Patch Diff Hash-SHA-256:

7b543c99d428e5784a0360462a53b789e62013dbbee0307e81c2a3b7cf2179ab

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength < ((INDEX_NOT_FOUND) + 1)) && repeat; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Lang39
### Patch Diff Hash-SHA-256:

08d140c61da26a785bc10cf715e8c1d721e2d0aed26d5291f7b16b66d1c69c6c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength + start) < (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Lang39
### Patch Diff Hash-SHA-256:

9fec5a1584b67825f9cbe071eaac8921c7242045d46476a1d7074b947152301e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (textIndex > start) || (textIndex < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Lang39
### Patch Diff Hash-SHA-256:

68d8edae1db07d95ce082104cc4673becdd3b6f15cdc4a254a5c07cf4883f97f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replaceIndex < 0) || (textIndex < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Lang39
### Patch Diff Hash-SHA-256:

032c93b0ee6580c4181a157bebbd54b1cf960fcbee04672cf3eb945fe816884e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength >= 0) && ((INDEX_NOT_FOUND) >= 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Lang39
### Patch Diff Hash-SHA-256:

912c03de7f465419879ac2c02fcb4b8ccbeb91fff40b655b0b304a0de56fa8a4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength + replaceIndex) < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Lang39
### Patch Diff Hash-SHA-256:

c33afd807fdb292354b8fda7afa2b3042a67034fa08f778ea22b8126a6a572fd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.ArrayUtils.isEmpty(searchList)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Lang39
### Patch Diff Hash-SHA-256:

f825589fda991294eb252d03914d57550f4295c3d314f89d0b32e527e8853c3b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength == ((EMPTY.length()) - (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Lang39
### Patch Diff Hash-SHA-256:

491ec3e51fdff19b0809bd3a62ccb2a6960c4c935f7afaa49a6f1c0ee42aee2c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.length()) > (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Lang39
### Patch Diff Hash-SHA-256:

2db67e1ba181a4310900387340d4e0c03340b09ed3656dd1681e4e0568fa3a5a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetterOrDigit(text.charAt(replaceIndex))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Lang39
### Patch Diff Hash-SHA-256:

762f2ac8c30a070fbf4b69ac7129c106c8230163444c51f0db231249d0576c78

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList == null) && (replacementList != null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Lang39
### Patch Diff Hash-SHA-256:

a2b860e42930e55b9bd05afec53b3ec5123a2b0d07851acb96a00b997340bb1f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.ArrayUtils.isEmpty(searchList); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Lang39
### Patch Diff Hash-SHA-256:

0df3188c030777d33c303dc7f7d67ab60176751a5196f6b726d3a4a1f38a5b1a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start == (-1)) && (tempIndex != textIndex); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Lang39
### Patch Diff Hash-SHA-256:

b6592e73ec295864ce65efabe7ad30676fc3e64d3483af498c1eb5bb374538be

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength == ((PAD_LIMIT) - 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Lang39
### Patch Diff Hash-SHA-256:

57eefe8f6795ac99431605fa033ea32b93b93589595aab53941f291c3ca1adde

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((searchList == null) && (searchList != null)) && ((INDEX_NOT_FOUND) > 0)) || (((searchList == null) && (searchList != null)) && ((INDEX_NOT_FOUND) > 0)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Lang39
### Patch Diff Hash-SHA-256:

552f96a5b9d7a4f164f88df3a11746ca4cfd53c5a22c22d01fa3317baeb5fb76

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text == "true"; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Lang39
### Patch Diff Hash-SHA-256:

d6af23a0c8e9298fa73e638a38d60d1cea04b26bf07bb7755ef38d58bb236b57

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Lang39
### Patch Diff Hash-SHA-256:

c19faea4f4f4cc5cac45cf8017d3f49af5222f992bd7e4995f774fd4d1238129

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((timeToLive < (searchLength + 1)) && repeat) && (!repeat); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Lang39
### Patch Diff Hash-SHA-256:

357d37ec3201ab2fcc7f844222c3de01af4f5fb764da22e40d607743d7bec350

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; text.startsWith("0x"); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Lang39
### Patch Diff Hash-SHA-256:

d7efdc581476457e61f3bd820450a0086052918262609fcab51f87ea451dbd51

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) && (text == null)) && ((((text.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(text.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(text))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Lang39
### Patch Diff Hash-SHA-256:

685da1182d5ee9ffd6fc0c8c85e9273ad4f73cb0691cf497b912cf67b2975b18

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex > (textIndex + 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Lang39
### Patch Diff Hash-SHA-256:

d91f4e849f890f5350e28a1f5cfdddaa9f07d381a3e1b944821d3838747b2e3d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength == (-1)) || (replacementLength == ((text.length()) - (text.length()))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Lang39
### Patch Diff Hash-SHA-256:

50e7dd221635a53baf569336c157b01c516674caf68820bb36fc1c4f35b2b7b2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase--) != 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Lang39
### Patch Diff Hash-SHA-256:

09b49fb19478cf01bb09ee697201db4184575d47d9a81555cd4540778e05f535

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList == null) && (replacementList != null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Lang39
### Patch Diff Hash-SHA-256:

ee1e105402314ea0ccb692cc18d395a8b7bf2d1a3c68cfb45a18d18ec1e3b9c2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(0)) == '['; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Lang39
### Patch Diff Hash-SHA-256:

6a212c9fec84a92034e676a5f015849dd886bbd290f3f1ace064809cfddcf00f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.indexOf(text)) >= 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Lang39
### Patch Diff Hash-SHA-256:

ad2571345e110a9006dd65eaccc9e5e086311b888c98fef10ae2d573e6fa4618

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((timeToLive >= 4) && ((text.charAt(timeToLive)) == '^')) && ((text.charAt((timeToLive + 2))) == '-'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Lang39
### Patch Diff Hash-SHA-256:

c40d8924cca83888785313fc0e6903c667248eb924537fadc4b6ac5772afc8c3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex > searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Lang39
### Patch Diff Hash-SHA-256:

549b06d94f59dc46aaa1a38d5f587dd6e33b9a5aea8939ab10aa70ee45fc0596

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex > (org.apache.commons.lang3.StringUtils.PAD_LIMIT); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Lang39
### Patch Diff Hash-SHA-256:

e3026dcca6d1b6a419944bed62351cf86d70b500cbf328915444e080c0b757cb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; tempIndex == replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Lang39
### Patch Diff Hash-SHA-256:

de16d471ebd432b4778d6d890086d86ec5fe1b3aa51a0012806da5f3b3b0a376

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= ((INDEX_NOT_FOUND) + start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Lang39
### Patch Diff Hash-SHA-256:

f6c198b698dc6e0b94831b3115050e75b45448ea58ff3fa079dbf754fce68531

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < timeToLive; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Lang39
### Patch Diff Hash-SHA-256:

16074989f14d9e4c090a2be059be9872d61373f2e47dbea6f99bba0d0817ee51

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; repeat && (textIndex == (java.lang.Character.LOWERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Lang39
### Patch Diff Hash-SHA-256:

1519384ba885eb0be64d448a830b806dc2cde3cec2f32899893233e10b71d6c4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Lang39
### Patch Diff Hash-SHA-256:

9ed1a90d7f3dc0f493da93d03b8d9aa7f4218ed8cdaf00bd661ab069ede10539

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase > (PAD_LIMIT); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Lang39
### Patch Diff Hash-SHA-256:

3dbda9a315fb1077f7178cd78f173554242e8d017b22e63cd7602a8e301a0114

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength == (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Lang39
### Patch Diff Hash-SHA-256:

b8bc6e5dec15baed60c2a9580c4ff61fddf27597dda1aebcafd0b134c830d35c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY.length()) - (INDEX_NOT_FOUND)) < (replaceIndex - 3); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Lang39
### Patch Diff Hash-SHA-256:

dca1f4e19ae659460a7fea5cdf7c83af7e39af111301d62c5bcb410693a49024

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase == 1) && (replacementLength <= (org.apache.commons.lang3.StringUtils.PAD_LIMIT)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Lang39
### Patch Diff Hash-SHA-256:

f7a4f8b9e9430ab19c2df146a6e5eee2bdbba26562671cbca016ce272ffd7781

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex == (-1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Lang39
### Patch Diff Hash-SHA-256:

7f25b0db04b4f21aa30c4d7ba17efb73bb5b56861e81239d05828a9c01e7dd18

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Lang39
### Patch Diff Hash-SHA-256:

28131bfc3957a72a8226d6356cd67c5d6278cbaee18971aff419616a5f8b6664

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) < (EMPTY.length())) && ((PAD_LIMIT) < (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Lang39
### Patch Diff Hash-SHA-256:

3bdcac03ed70f935fd1188cdd1284ba250b8b507a8a3c950b470cb56ea215faa

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start != increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Lang39
### Patch Diff Hash-SHA-256:

be59b2cecfff3fdf666c89945b377b441bcefd825a7f390bd7ca34a746e31bae

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLowerCase(text.charAt(textIndex))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Lang39
### Patch Diff Hash-SHA-256:

5ba49168daca7f8c6e6406f45f0c1500abebd903560dd5e26c8c00fa9d00408d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Lang39
### Patch Diff Hash-SHA-256:

6e75b03d83e534c7b8d99cfcc2ab786b1723e444d193f0bc8ae23061aef44ac4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((org.apache.commons.lang3.StringUtils.isEmpty(text)) || (org.apache.commons.lang3.StringUtils.isEmpty(text))) || (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Lang39
### Patch Diff Hash-SHA-256:

1dd8e1830922d07b6b3c6ea9b7add256c8845da813f1d0a49ed8a71e24d74445

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (timeToLive < (text.length())) && (timeToLive < (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Lang39
### Patch Diff Hash-SHA-256:

37f88a2e0fb960b8618c2e9dfa72196a8a835314db95a271dedec55cc1d6dc3a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList[textIndex]) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Lang39
### Patch Diff Hash-SHA-256:

6702e18e6b75ea7c5b319f8313e08c75ee5c2b37fbec5ef9262aaa756bc1d17d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive < (INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Lang39
### Patch Diff Hash-SHA-256:

ad184d05f73f8f37f2a7d69cafba2c2106a7f4dca7a694d203d2ead110bf3652

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Lang39
### Patch Diff Hash-SHA-256:

880df2e4fa6aefff2d069aa8237dca9ca2ef917197d10bc4939198844b36fdcf

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) >= (EMPTY.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Lang39
### Patch Diff Hash-SHA-256:

fbc8425d2d9f609dbfa84b2d1249c82eee677a3e9e2e6abb3efcc458ce01b0cc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY.length()) == 0) && (timeToLive >= (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Lang39
### Patch Diff Hash-SHA-256:

ff014152050d290b44e41a94cbdc028256011a915d16dac99b3c1cba7fd56d42

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive == ((EMPTY.length()) - (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Lang39
### Patch Diff Hash-SHA-256:

b88b66f22b289323157d928169a6d516db20f227e863bfd506b709f3028a6190

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex > 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Lang39
### Patch Diff Hash-SHA-256:

9cb5ed460336ad31ec292ce6a50c519dd5cfa3a47512e57b6e4aad856f6d5d45

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (java.lang.Character.LOWERCASE_LETTER); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Lang39
### Patch Diff Hash-SHA-256:

32d75c5cbce06a73b24670c282791ea4e5e6034d9be779da583e5388f5951362

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) || ((EMPTY) == null)) || (text == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Lang39
### Patch Diff Hash-SHA-256:

e535b508e36bf2401160a70cb931f1d2adc38062f60435f3879b0d8de4069d95

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start = PAD_LIMIT) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Lang39
### Patch Diff Hash-SHA-256:

80e5428b19606579b6c8ff5cfae15fbb415b319fe8853d2294044930f4b69ec3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((EMPTY) == null) || (replacementList == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Lang39
### Patch Diff Hash-SHA-256:

52c17f1cda20f800aac28f9a6e6248b4003df7ba32290acb0e199bbe63e4eaba

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != searchLength) && (java.lang.Character.isWhitespace(text.charAt(start))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Lang39
### Patch Diff Hash-SHA-256:

1cac716c25c960689e144816311e10ad4af841632cbf010bb26acd453299c154

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; repeat && ((INDEX_NOT_FOUND) == (java.lang.Character.LOWERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Lang39
### Patch Diff Hash-SHA-256:

44d73c8f455c47e5b8654583596b26471887d77c98f9f5feb91d528e8c7ebf4b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) < textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Lang39
### Patch Diff Hash-SHA-256:

6353559736901992c588da01c79bf7bd4206441849f25963836bb8746498413b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength > searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Lang39
### Patch Diff Hash-SHA-256:

73bfbd60afe35298754737e2f5abffc6b943cea62b0203dd130f83f3fe32c5d2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) == replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Lang39
### Patch Diff Hash-SHA-256:

2e5a4ffd758ae770ea4486969bf7898d448c843f7503f164c6aef6e558390a7e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replacementLength < searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Lang39
### Patch Diff Hash-SHA-256:

0506072317bb561c94fd7bb44eeca8b7a68ec60674426507ddd5206003b9dc07

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase == 1) && ((INDEX_NOT_FOUND) <= (org.apache.commons.lang3.StringUtils.PAD_LIMIT)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 455 of bug id Lang39
### Patch Diff Hash-SHA-256:

6db756b1f292e8efa0ead5be6cbbe4a1d583c392ef0fdaaa96dcf921cebacbb8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetterOrDigit(text.charAt(timeToLive))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 456 of bug id Lang39
### Patch Diff Hash-SHA-256:

242e0523b9b95b930ea2c0837b19f5e9bdd8463411bb64fc49edc84468c7fdb3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLowerCase(text.charAt(timeToLive))) == false; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 457 of bug id Lang39
### Patch Diff Hash-SHA-256:

e3d6a4062d8fa2689749e9cf25c6165c4f8cd25c94155c8303538cb1cf9cafa5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 458 of bug id Lang39
### Patch Diff Hash-SHA-256:

a8230d84b367ab2aab4eea4559d3e0a6e3a5548213d0d1629fab25882c027f96

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.indexOf(text.charAt(start))) < 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 459 of bug id Lang39
### Patch Diff Hash-SHA-256:

24b948ecb6cdc291c8b042986a586d5604d427eb49375aea5196b6def2fda4f3

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (PAD_LIMIT) == timeToLive; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 460 of bug id Lang39
### Patch Diff Hash-SHA-256:

12beae8be15df5c8c17d51d8df7c28e9f54226e055a82c56e5a9f9df7858492f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (repeat && (start == (java.lang.Character.LOWERCASE_LETTER))) && (replaceIndex == (java.lang.Character.UPPERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 461 of bug id Lang39
### Patch Diff Hash-SHA-256:

59dce163e8416a6890a10f544b5a33aaad170eb571b561295efc71c6cf6ac61b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength <= textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 462 of bug id Lang39
### Patch Diff Hash-SHA-256:

cfdd0899b65fb0e9c5d464f23543f107a0b1f117c56bdedbc3517c7349d39fd6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex > searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 463 of bug id Lang39
### Patch Diff Hash-SHA-256:

f1f0c910263e6a20e705c2755588da9e380a9abea7f0ee3809be2eaf555c1a06

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (repeat && (textIndex == (java.lang.Character.LOWERCASE_LETTER))) && (timeToLive == (java.lang.Character.UPPERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 464 of bug id Lang39
### Patch Diff Hash-SHA-256:

495a6ccc32f4062332625622ab6d3c7c666aa13dafddffe144d96f062d7be5a7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) - timeToLive) < (timeToLive - 3); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 465 of bug id Lang39
### Patch Diff Hash-SHA-256:

99e165db4876d4e307a61e917c9a0704de736d2771ae0f869055321f3699623e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase == (java.lang.Character.LOWERCASE_LETTER); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 466 of bug id Lang39
### Patch Diff Hash-SHA-256:

0676f003b1ffabeb9cf0b0359846afbd1bb972d9451fca1828923f8e9abf7255

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < (searchList.length); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 467 of bug id Lang39
### Patch Diff Hash-SHA-256:

c681f35fe97447d07fd3298789837e53512fa1d057df2de91bed12ec9133b30e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementLength < (EMPTY.length())) && (replacementLength < (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 468 of bug id Lang39
### Patch Diff Hash-SHA-256:

033ad998526abe98b1fda7f5b050d10d128b47fb10a0c872cc7ccb5c293398a2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= (textIndex + start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 469 of bug id Lang39
### Patch Diff Hash-SHA-256:

6b00261932304c2ea63f5a9be202ba31c85bf3ff2f6d084b650865f0fdcc5c66

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) < (EMPTY.length())) || ((PAD_LIMIT) < (EMPTY.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 470 of bug id Lang39
### Patch Diff Hash-SHA-256:

de5d821061db5ab0fec907cd6eb8f178224d466eaff04af7c7ec8a47ee296396

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) > increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 471 of bug id Lang39
### Patch Diff Hash-SHA-256:

0fbd8553e2f392f9bf2adb5f3e667f0a14f358fd4e0333398bf9f786f7505963

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) == 0) && (timeToLive >= (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 472 of bug id Lang39
### Patch Diff Hash-SHA-256:

a3d67d0941122ac21e384de53c4d2a29cb274f94096f6d6e35ec887ec13fc4fa

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != textIndex) && (java.lang.Character.isWhitespace(text.charAt(start))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 473 of bug id Lang39
### Patch Diff Hash-SHA-256:

b21c97d228b958a2ee8b5da9fb7e2cdfe6ad70965e028e31bd81184bebdeb011

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchLength == (-1)) || (searchLength == ((text.length()) - (EMPTY.length()))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 474 of bug id Lang39
### Patch Diff Hash-SHA-256:

7da556da8dc5f2fdb23d9379364e87021fc16d90feaaef2135a8a225fa5db25b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (timeToLive == (-1)) && (replaceIndex != (PAD_LIMIT)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 475 of bug id Lang39
### Patch Diff Hash-SHA-256:

287201d07883f7e7036e4ffe85db8fa57e891287e90c29edcfedc98284772bce

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList[textIndex].length()) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 476 of bug id Lang39
### Patch Diff Hash-SHA-256:

97bce3885278b6939c723eae4151bd69bc328ea8f79ff198656f216700d34f71

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; timeToLive < increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 477 of bug id Lang39
### Patch Diff Hash-SHA-256:

9091a24f1faf85bf721240e1ffbf1994bf35e1c6f13b7ff254824493ecc3fab2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (replacementList[increase]) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 478 of bug id Lang39
### Patch Diff Hash-SHA-256:

b0e54e0595cf243b4ff95f214ab2b880200eabd737a30fd44882449264377230

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex == (java.lang.Integer.MAX_VALUE); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 479 of bug id Lang39
### Patch Diff Hash-SHA-256:

b9f9d89c47abbdc5b3c3d13117b9fa07c3493fc8bdb1df9a57388aca06e3a524

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (INDEX_NOT_FOUND) >= (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 480 of bug id Lang39
### Patch Diff Hash-SHA-256:

f90d141991b4b162a35bdfc329001abc7ce46af7b24ba8ddfa3de64a19329798

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex < ((PAD_LIMIT) - (PAD_LIMIT)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 481 of bug id Lang39
### Patch Diff Hash-SHA-256:

57c6cce0fd34ec1c73be368221abaf22beebbf3c8fe73e9adabe91471318eb5a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase >= 4) && ((text.charAt(increase)) == '^'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 482 of bug id Lang39
### Patch Diff Hash-SHA-256:

38bbba3b97bda47db5e8d489124c8420a5558b3314cfcf1c2875503a6a1b30f9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start == 1) && (start <= (org.apache.commons.lang3.StringUtils.PAD_LIMIT)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 483 of bug id Lang39
### Patch Diff Hash-SHA-256:

a1682c58acbff2ded4f42050d9c7145c2426556c39bd4ece794f43d1bcddddb4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; noMoreMatchesForReplIndex == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 484 of bug id Lang39
### Patch Diff Hash-SHA-256:

5e69817534b5223a9d617f82af27096227ef09008a5fcf0f826fc571e0ca5d07

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((org.apache.commons.lang3.SystemUtils.OS_NAME) == null) || ((org.apache.commons.lang3.SystemUtils.OS_VERSION) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 485 of bug id Lang39
### Patch Diff Hash-SHA-256:

6dcb6552c22856dd56015dd262f77562af42f451d3d698cd17884fabbfc5d0ad

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start >= 2; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 486 of bug id Lang39
### Patch Diff Hash-SHA-256:

c3971ac927163568387ba9656a6ff1a4c560db52bb4762996b654723a290660b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase >= (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 487 of bug id Lang39
### Patch Diff Hash-SHA-256:

88c18a3e7b5ec7a6e04950e33611a8dbc5d4a990fbcc07a47b5f177dd87d8651

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((searchList != null) && (searchList != null)) && (start != start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 488 of bug id Lang39
### Patch Diff Hash-SHA-256:

5b9226e0a0b580be10b01b59b21cc38d8d909dd82de6fd766d814b16dd2b5245

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) || ((EMPTY) == null)) || ((EMPTY) == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 489 of bug id Lang39
### Patch Diff Hash-SHA-256:

25aaea63cf91ec83bec38347b0167993733e8cda40e9cd08f8c6d0fff2b1bd19

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (EMPTY.startsWith("0x")) || (EMPTY.startsWith("-0x")); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 490 of bug id Lang39
### Patch Diff Hash-SHA-256:

165dbddbc76a3f78e56c0d801f0f61b1b6a440e672b02923f115945904437a7e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList[start]) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 491 of bug id Lang39
### Patch Diff Hash-SHA-256:

83f5239aeb027cea2fa8321cdd72a59231fb2d2021dd50d806f07aa2804e4640

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != increase) && (java.lang.Character.isWhitespace(text.charAt(start))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 492 of bug id Lang39
### Patch Diff Hash-SHA-256:

76eb9886f03207be5eb5adad810982bff2803070de3137e03a61e7bcedc6989a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < (start - 2); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 493 of bug id Lang39
### Patch Diff Hash-SHA-256:

ea8f6c265c3f4c699a70fb12fac0a7ad7e963186922490db894b32b6dfd0b280

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start > 0 ? -start : start) < (-start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 494 of bug id Lang39
### Patch Diff Hash-SHA-256:

023b3bb88767d5198fbbafc099b1ff3263c4ac782fddc1d4c0041971e4236937

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((searchList == null) && (searchList != null)) && (start > 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 495 of bug id Lang39
### Patch Diff Hash-SHA-256:

014e756630452c7deecb2eee97da68139c1c49149a9071899e203cace4fd806a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start < start) || (((start < (start + 1)) && repeat) && (!repeat)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 496 of bug id Lang39
### Patch Diff Hash-SHA-256:

8b2d51a24f0409da2584915217aa34871340a0daffec79bdd5cb51a0bb91e3e0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase == (-1)) || (increase > (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 497 of bug id Lang39
### Patch Diff Hash-SHA-256:

8497726a29ae5107915042bd9df10853753fd95908789d0bea557eb0d22b5316

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || (replacementList == null); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 498 of bug id Lang39
### Patch Diff Hash-SHA-256:

69ec48fb81024ea398cd016a7dddf702307e92f5a7585dba3bb3bfee4e9ca2b4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase + increase) > (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 499 of bug id Lang39
### Patch Diff Hash-SHA-256:

9ba4be0c45b13cbe9fb261cdc0ae7123bdd2100df5261505f9dc8e5a52c7fa40

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (java.util.Calendar.MILLISECOND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 500 of bug id Lang39
### Patch Diff Hash-SHA-256:

098ec1ce11aee0012ca1362895db33f63a949a0435f09c711f97a6f64329d750

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start >= 4) && ((text.charAt(start)) == '^'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 501 of bug id Lang39
### Patch Diff Hash-SHA-256:

c8e1fa6798e518067be6095c59eae138c0ec74d02661c4d2987bf11984d7b9f9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start++) == start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 502 of bug id Lang39
### Patch Diff Hash-SHA-256:

81e515aa6b4364cbe657a7d0ea200cc5fd54ab89686ee2d032cb82df69a61ee8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; java.lang.Character.isDigit(text.charAt(increase)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 503 of bug id Lang39
### Patch Diff Hash-SHA-256:

62f1ddb9bc771f9e7448231a4795b7643bcbeca1f0c563a6e3d7dc0cb68c53d1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start != start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 504 of bug id Lang39
### Patch Diff Hash-SHA-256:

b35a63a374e957d0fdf6bbc1b1500bcb0139c73c7ca99fdd5fcedbce6b174e75

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((increase + increase))) == '+'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 505 of bug id Lang39
### Patch Diff Hash-SHA-256:

b31797e5b2d4e43d06f99625ff324a960634f29c48246f8b1f4364cdfee83804

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > (java.util.Calendar.SATURDAY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 506 of bug id Lang39
### Patch Diff Hash-SHA-256:

4c78a131bfa1be0c5f13e56151e2f0b62b5153b2a41bb12bfd30629ebe4552a6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase < increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 507 of bug id Lang39
### Patch Diff Hash-SHA-256:

c5b449be8052fc915c15dd21ba49aeb3863cf4370b17ccf0a38ced8439266ca1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; textIndex > textIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 508 of bug id Lang39
### Patch Diff Hash-SHA-256:

19e9510041a9ed464676651db278946b3e3aa0c0899d17674cf53f8f3dd25a65

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase >= 3) && ((text.charAt((increase + 1))) == '-'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 509 of bug id Lang39
### Patch Diff Hash-SHA-256:

9960366a8bf3f081f2010ef9eecebb7b2770aa0e6166916f7385d208ed85e09d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start >= (text.length()); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 510 of bug id Lang39
### Patch Diff Hash-SHA-256:

23c5205859a96ccdbd05d12501a9c9d56654d8199d42e33e84c7d13fea2a32be

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start > 0) && (start <= start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 511 of bug id Lang39
### Patch Diff Hash-SHA-256:

817fa9e938b94e1d45c98b67c839ef17b13a33b71c18642a867567dfaeb43312

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; java.lang.Character.isWhitespace(text.charAt(increase)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 512 of bug id Lang39
### Patch Diff Hash-SHA-256:

708cce26b55a55e3140baf1a35a41a2c861cfb20ec04657ef27c977dd351ff8a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; repeat && ((PAD_LIMIT) == (java.lang.Character.LOWERCASE_LETTER)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 513 of bug id Lang39
### Patch Diff Hash-SHA-256:

314e33ba86edf81ad8671f310a0483856e92e3f280eb39dea8d32c07ee201bfe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; EMPTY.startsWith("-0x"); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 514 of bug id Lang39
### Patch Diff Hash-SHA-256:

eba3889cee4cbc270512712612b18141c234dcf13aed7435dbf744a620d9a170

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) - increase) < (increase - 3); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 515 of bug id Lang39
### Patch Diff Hash-SHA-256:

e6b439d4e3f9594c041d148132336311bb8ee5f7a63bd837f8e32bca7be2fe34

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(increase)) != (text.charAt(increase)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 516 of bug id Lang39
### Patch Diff Hash-SHA-256:

3bfdad2d517dd94ee7aa9f1b538256e40a7e5757da453ae002f90d64c757aa04

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 517 of bug id Lang39
### Patch Diff Hash-SHA-256:

5f8223a0378a904122e2e2450b706ee48be3a38c65d008ae1defea17ba769f26

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start & start) != 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 518 of bug id Lang39
### Patch Diff Hash-SHA-256:

cb073d1cde9ebdda362c439da0393dc969b41d3b9095208d0e6145065d06d5a7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((start > 0) && (start > 0)) && (start >= start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 519 of bug id Lang39
### Patch Diff Hash-SHA-256:

97d6851c307a6dfb9fde1eca7f4e71a2ebbc528d47f1d3985d35c8595a14f2be

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start < start) && repeat; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 520 of bug id Lang39
### Patch Diff Hash-SHA-256:

9ca2ccfe9569a0eb5a3fdecc4a73b36edbdf3333472c1dcd7fe3b0ad95ca3208

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase == 1) && (increase <= (org.apache.commons.lang3.StringUtils.PAD_LIMIT)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 521 of bug id Lang39
### Patch Diff Hash-SHA-256:

4a47447652acf705209aea5e20a8f07b0efd7f8651064d08bdbce72e6de3fdae

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) == (org.apache.commons.lang3.time.DateUtils.MODIFY_CEILING)) || (((PAD_LIMIT) == (org.apache.commons.lang3.time.DateUtils.MODIFY_ROUND)) && repeat); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 522 of bug id Lang39
### Patch Diff Hash-SHA-256:

e64a8aff45697f8527bdfee4c2669638891c5c36b6f7d718d281e0a154df43a0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase < start) || (((increase < (start + 1)) && repeat) && (!repeat)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 523 of bug id Lang39
### Patch Diff Hash-SHA-256:

efb05502f080ce510c1af7a9b7fa6c63d96b1c33d964803655f9fae23000941e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; !(org.apache.commons.lang3.StringUtils.isEmpty(EMPTY)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 524 of bug id Lang39
### Patch Diff Hash-SHA-256:

002ee4ab20d9730013afd99bd147f1bd70aa7d4c92959f5019be7ad8f23a57a4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; replaceIndex < replaceIndex; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 525 of bug id Lang39
### Patch Diff Hash-SHA-256:

c849e145f44b7dd4f739b3075a60ad4a6d164a005c0014a2f7862c6830e711c8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.SystemUtils.IS_OS_HP_UX; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 526 of bug id Lang39
### Patch Diff Hash-SHA-256:

75e0f281be3e4ab766c39ea334215dd1433d96457ebb45f9b28712122c70c897

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start < start) || (start > start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 527 of bug id Lang39
### Patch Diff Hash-SHA-256:

50a82bab2bcd558c710e2ab951f23919c8d2438e0437e7b9111e55f60a674151

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start < (start - 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 528 of bug id Lang39
### Patch Diff Hash-SHA-256:

57c843dc907086929ed95bafa9e8453f9940e2cad2552333f4f43a9f2dc659f9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength < replacementLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 529 of bug id Lang39
### Patch Diff Hash-SHA-256:

5a9fbef13ebafdc752fa64c9327f37a589ebd27f280db1ca6d709babd856568e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((increase + increase) < (text.length())) && ((text.charAt((increase + increase))) == 'u'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 530 of bug id Lang39
### Patch Diff Hash-SHA-256:

221b2c4a8cd764fa785be6b4e388ab3c0c6708aaff8791fbe77eec03a544bb5e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt(increase)) == '^'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 531 of bug id Lang39
### Patch Diff Hash-SHA-256:

991dcde9569a041e904fe33a31f1a8ef8057cb519f7f4aa52cce21122d216eae

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start < start) && (start != 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 532 of bug id Lang39
### Patch Diff Hash-SHA-256:

0c20263e0a17addd892cf311a84f8c637c5080c19e908cc49d6e38c7ba72186b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) == (org.apache.commons.lang3.time.DateUtils.MODIFY_ROUND)) && repeat; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 533 of bug id Lang39
### Patch Diff Hash-SHA-256:

2ef6daf35cfa364af9be36279a954da6fba0e4eba1604361b5a86188216380a1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((start + start) < (text.length())) && ((text.charAt((start + start))) == 'u'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 534 of bug id Lang39
### Patch Diff Hash-SHA-256:

e5842f2f34914ad7f0811ba3a90b00012a5fbd53cdafb4c85cf1ea6b674a198d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start == (java.lang.Integer.MIN_VALUE)) || (start == (java.lang.Integer.MIN_VALUE)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 535 of bug id Lang39
### Patch Diff Hash-SHA-256:

0d7e9faefa3da1817fc8883b1373cc549c486de61939c7e6c2058f0eb3eac319

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (start - 1); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 536 of bug id Lang39
### Patch Diff Hash-SHA-256:

43caf6fc6f0c5ae338914028e880d0e5149ca681f048644781e9f9131afcdd8e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text == null) || ((increase = text.length()) == 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 537 of bug id Lang39
### Patch Diff Hash-SHA-256:

1d6688ce2620556eb9057404e7db3240ee1ef6a890969ad8b52cbf2ed90b0ac2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (!repeat) && (((org.apache.commons.lang3.time.DateUtils.MODIFY_TRUNCATE) == (PAD_LIMIT)) || ((PAD_LIMIT) < 30)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 538 of bug id Lang39
### Patch Diff Hash-SHA-256:

b142514bbbb6ed6e315bd23e4d48e643e6b354a1b399eb5edf648a2c04cc1c74

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; java.lang.Character.isUpperCase(text.charAt(increase)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 539 of bug id Lang39
### Patch Diff Hash-SHA-256:

4b994f0a5f21cbe110c95b81b8cd302ab5937cc865fe79831c564326df8880ef

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((PAD_LIMIT) == 0) && (!repeat); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 540 of bug id Lang39
### Patch Diff Hash-SHA-256:

9f2c0fc5e44445ba7555c1bf5468b13b0ea225acb0220fd5199585ba8cb42a1a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > 65535; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 541 of bug id Lang39
### Patch Diff Hash-SHA-256:

5aa9db84eb8850c0c3f7ce1865403e365b85d71fee06ba1193e14dd7f38c10be

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (org.apache.commons.lang3.time.DateUtils.RANGE_MONTH_MONDAY); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 542 of bug id Lang39
### Patch Diff Hash-SHA-256:

74905d37bad4497bc9ca5b0d112b617bc9bfa3766a1bc2a0fd67892555996a89

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList != null) && (start > 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 543 of bug id Lang39
### Patch Diff Hash-SHA-256:

61f31054afcef49d4c36cb771804c4683ac1dfbf74b40aff4ae8d56b5bc7aebb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; java.lang.Boolean.FALSE; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 544 of bug id Lang39
### Patch Diff Hash-SHA-256:

57f91c8bd5e8a2ac96e962a4a6c7a6a6f9029161c74046557cdb3a2854b1bfcc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start >= 3; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 545 of bug id Lang39
### Patch Diff Hash-SHA-256:

67eca0d1b6df1a81c7b68cc563f0bc5c747f86343c17f106d0c2724a9f0f898b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == 2; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 546 of bug id Lang39
### Patch Diff Hash-SHA-256:

44ae59cdd536d2d1f7a7fec710ab91eed05f6a1777508e2c178c016cb712d64c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((increase + increase) < (text.length())) && ((text.charAt((increase + increase))) == '+'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 547 of bug id Lang39
### Patch Diff Hash-SHA-256:

44a00d6db1ed14115be4071cdc9520e1f1dc0be9736aef11ab872ac2a753ebcd

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((increase >= 4) && ((text.charAt(increase)) == '^')) && ((text.charAt((increase + 2))) == '-'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 548 of bug id Lang39
### Patch Diff Hash-SHA-256:

3b76640475bb04d997a431ba8b8c9ca1cfa5363665e8a21c07c8c240c03e9404

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != increase) && ((text.indexOf(text.charAt(start))) != (-1)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 549 of bug id Lang39
### Patch Diff Hash-SHA-256:

e0ff9abd65bab3bb194fd1f0cdecdd99620270598ccda30750413bfd730ce4e1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start != start) && ((text.indexOf(text.charAt(start))) != (-1)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 550 of bug id Lang39
### Patch Diff Hash-SHA-256:

86336d75c3f687e95a58e715750608b4fc500bdff655eea61221f7ccdbd8e582

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start > 0) && (start > 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 551 of bug id Lang39
### Patch Diff Hash-SHA-256:

76df1ffc218e96a60325e0075e2cb816fb171ea47da7ee87bd52412bd7bbb6f9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.SystemUtils.IS_OS_SUN_OS; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 552 of bug id Lang39
### Patch Diff Hash-SHA-256:

39ba7d9b31e0e34b45f061bfbce38623833630e81f3aa3678c4d3c61ea265475

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((start < (start + 1)) && repeat) && (!repeat); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 553 of bug id Lang39
### Patch Diff Hash-SHA-256:

4ffba17219dbc0d5d99d6efb916b2b7156f787ec9bf9e64ab755fdfe29ed0ff5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((increase + 1))) == '-'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 554 of bug id Lang39
### Patch Diff Hash-SHA-256:

19ea1ea44f07c3df4f1d50f90590f9d23491c115a849636c46823050cc207cef

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((java.lang.Character.isLetter(text.charAt(increase))) == false) && ((text.charAt(increase)) != ' '); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 555 of bug id Lang39
### Patch Diff Hash-SHA-256:

612ccc96aee9c489b03fb5e580f6e963cd22541157e4a622c7cea69b666bce62

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((increase + 1))) == '#'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 556 of bug id Lang39
### Patch Diff Hash-SHA-256:

1c8b49cc8495951a4c4f2236e736883ce95796c0a8abcb3dab8276b942ed7ad1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start < 0) || (start < 0); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 557 of bug id Lang39
### Patch Diff Hash-SHA-256:

e0e7f231230ebd5ecaf217c66605dede41b72cd8a6ca825215af7199f05d4890

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((((text.charAt(1)) == 'r') || ((text.charAt(1)) == 'R')) && (((text.charAt(2)) == 'u') || ((text.charAt(2)) == 'U'))) && (((text.charAt(3)) == 'e') || ((text.charAt(3)) == 'E')); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 558 of bug id Lang39
### Patch Diff Hash-SHA-256:

5063add0c897c2b40c8e5a7bacf051b7cdedcfc19643367229c0ff5c1edb6ffb

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase >= 2) && ((text.charAt(increase)) == '^'); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 559 of bug id Lang39
### Patch Diff Hash-SHA-256:

da503ad5afa8f81e02a5ac18f270f500dcadf29a38c4a1a0219ea0deb6f15679

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; searchLength > searchLength; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 560 of bug id Lang39
### Patch Diff Hash-SHA-256:

b6f4e698c1f40260ec2777dac2c49e00b0c2a768f5ed387bcad4098fe1bfed19

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.SystemUtils.OS_NAME) == null; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 561 of bug id Lang39
### Patch Diff Hash-SHA-256:

795b3941ef5811775f138a31d3bc64cc1184c57972290749ad15926a03280387

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start < 0) || (start > start); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 562 of bug id Lang39
### Patch Diff Hash-SHA-256:

7843212c1fb043cea1ee10a267d96a5cec4c30ba3941d4dd2e4637230fb41cf9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase < 0) || (increase > increase); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 563 of bug id Lang39
### Patch Diff Hash-SHA-256:

7a9002ddeb245b469f96f1726762f4846b441d9b0e61d353cf40b0fa41bc41c9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; org.apache.commons.lang3.SystemUtils.IS_OS_MAC_OSX; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 564 of bug id Lang39
### Patch Diff Hash-SHA-256:

8276e822dda71292547f70b23c5761d70425a4aaffafd6d315b2283b29096369

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((start + 1))) == '-'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 565 of bug id Lang39
### Patch Diff Hash-SHA-256:

4b5690d6ffd31eab0f870c641c0391e8cc53468a5612c8140977172374d210ad

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((searchList == null) && (searchList != null)) && (start > 0)) || (((searchList == null) && (searchList != null)) && (start > 0)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 566 of bug id Lang39
### Patch Diff Hash-SHA-256:

446cf800ad1518362e557f6d888a6a2cce2971db92c5cf4c351f3fb801f37b8a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (java.util.Calendar.SECOND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 567 of bug id Lang39
### Patch Diff Hash-SHA-256:

25eb276a06e4d0b556cd573814fa31bc2f5c040a36e7a9a827265974d004c838

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; null == searchList; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 568 of bug id Lang39
### Patch Diff Hash-SHA-256:

56d4a7604ebd0d86bce6fc2b8bfeb9a75afc78f2afcf76d916ffd5aa7012e106

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (org.apache.commons.lang3.ArrayUtils.indexOf(searchList, text)) != (org.apache.commons.lang3.ArrayUtils.INDEX_NOT_FOUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 569 of bug id Lang39
### Patch Diff Hash-SHA-256:

9fb349504a77b533509935f2f8cf3c28d8cc46bf94dca7cf9f61c0786df83dd4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (java.lang.Integer.MIN_VALUE); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 570 of bug id Lang39
### Patch Diff Hash-SHA-256:

24b4502466cbef9233f4e1ccc617e38e4cabe10de2691db56ea92db41ecb3b20

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.charAt((start + start))) == '+'; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 571 of bug id Lang39
### Patch Diff Hash-SHA-256:

0ab410b993f1024f334484d2a8068ae3b260e643d466dda9e38c6579004d8b32

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; increase != increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 572 of bug id Lang39
### Patch Diff Hash-SHA-256:

7eafce964c775439cedd5227831a1ac321f3c4864581829bd18eae1672645172

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (start - start) > start; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 573 of bug id Lang39
### Patch Diff Hash-SHA-256:

2f1a79e0fa6fcf5f6db87a4c4b8bb7bba9bf4ce3644314c19dfd7eddcfb34ff1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase < 0) || ((increase + increase) > (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 574 of bug id Lang39
### Patch Diff Hash-SHA-256:

fe55e61fd3edc8de8f41e76634d186d00487d970c87be55d10d09ca5b9c00f6f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start == (org.apache.commons.lang3.time.DateUtils.MODIFY_ROUND); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 575 of bug id Lang39
### Patch Diff Hash-SHA-256:

f3662f4093e11c49286e00bdcb2e83402a8ab169dac6e2fb0e9d956645accbc8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= increase; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 576 of bug id Lang39
### Patch Diff Hash-SHA-256:

cb60aab1e97b740f048692cf66056014a0db0c3bce4d92375e341e71d6b01d80

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; java.lang.Character.isWhitespace(text.charAt(start)); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 577 of bug id Lang39
### Patch Diff Hash-SHA-256:

502cb2e95a154f342d70ab891cc359b843326346389989006cbe3a8a55bdd2b5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; start > 255; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 578 of bug id Lang39
### Patch Diff Hash-SHA-256:

635b1b52ee07e9bdb5846d9c64cda857dc36417a8b5b607da4eb4884af52f62e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (((EMPTY) == null) && ((EMPTY) == null)) && ((((EMPTY.charAt(0)) == '-') && (org.apache.commons.lang3.math.NumberUtils.isDigits(EMPTY.substring(1)))) || (org.apache.commons.lang3.math.NumberUtils.isDigits(EMPTY))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 579 of bug id Lang39
### Patch Diff Hash-SHA-256:

b7d7d6100d1fdd6425060347c5a8694cc1733f30cbae1b8e8bc4700e9ba0d730

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (org.apache.commons.lang3.StringUtils.indexOfDifference(EMPTY, EMPTY)) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 580 of bug id Lang39
### Patch Diff Hash-SHA-256:

4ad18271dcb093f71f6a29e95882a67dabef851ed70a4da63e1fab4a91002131

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = text.charAt(increase); i < (searchList.length); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 581 of bug id Lang39
### Patch Diff Hash-SHA-256:

c2f42f0dfe863fd9dd5b9c74fedca030000662c4a8b5d9abe0b427a23fb40ec2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (text.substring(0, increase).length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 582 of bug id Lang39
### Patch Diff Hash-SHA-256:

b15079a4d3deb0eae96e5d1fc59a2bf1b3d4b440af5979f535cb0651ac700327

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = EMPTY.length();
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 583 of bug id Lang39
### Patch Diff Hash-SHA-256:

5daabc770644682645bb87459d38de348e2245183c08924bde6066a65663a0aa

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (org.apache.commons.lang3.StringUtils.indexOfDifference(searchList)) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 584 of bug id Lang39
### Patch Diff Hash-SHA-256:

c9842350974850be90143e82265954405e52c1c4411627af8a04e172d64d593d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (java.lang.Character.isLetter(text.charAt(increase))) == false;) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 585 of bug id Lang39
### Patch Diff Hash-SHA-256:

6a12bb55404db247d2331d3ce3360f5493ff09416723abf898d0cfe96190f0c5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (searchList[start].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 586 of bug id Lang39
### Patch Diff Hash-SHA-256:

42038168e9e86aa46624129364262a4c6aa52bb93cc63e0a3c6cf650f64fd504

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = start - start;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 587 of bug id Lang39
### Patch Diff Hash-SHA-256:

a56de2f388bd6bca1ea8fc1495914884728133d104f8bf771c0c4775a5bbdb93

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = start - 1;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 588 of bug id Lang39
### Patch Diff Hash-SHA-256:

aa669162a86db1af63e701b2de0a71bf8070a8b51d4aeabe4f73108207fc6d0b

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (EMPTY.length()) - 1;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 589 of bug id Lang39
### Patch Diff Hash-SHA-256:

83590b2eed72c7fea404c62387f2fd079a08b9384a5a15308eccbf75083b87b8

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (text.length()) <= (increase + increase); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 590 of bug id Lang39
### Patch Diff Hash-SHA-256:

245f785402860e84dd5d9b8657f3268a537bc87c034effd4409293f45c833111

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (EMPTY.length()) - (EMPTY.length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 591 of bug id Lang39
### Patch Diff Hash-SHA-256:

c52a5a96d45f43f267480a20e6507e1314205e709e21cdba9923d636cbd7af00

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (EMPTY.length()) / 5;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 592 of bug id Lang39
### Patch Diff Hash-SHA-256:

3140df40ceaf7152049ebdbe85770673a7eb5b7142ba53638ed4ff5cd10fc205

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = increase - (text.length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 593 of bug id Lang39
### Patch Diff Hash-SHA-256:

f3658c6f0e19fd697551969ede051112dee8a541ce3972c7f914b0fefb4d9e2d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (start + start) - start;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 594 of bug id Lang39
### Patch Diff Hash-SHA-256:

1112dd85f7b2fbf17e98d83ceced03377b158dc831657bde3e4008c39c80d588

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = start + start;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 595 of bug id Lang39
### Patch Diff Hash-SHA-256:

20a07ec91198590cc708aacb68ccdced68d6dcdca783bf5dcf8f88d2cd872ec7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (searchList[0].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 596 of bug id Lang39
### Patch Diff Hash-SHA-256:

d7d61ad0db714c4f543465b56b5c52941a0e9b1711edcf39bf444a6a3f28d5d9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (replacementList[0].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 597 of bug id Lang39
### Patch Diff Hash-SHA-256:

5c01efc0b16a7a5de2a704d913860cf1ccbecf52985f956b678dc6320bf1ebd6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = ((searchList[start]) == null ? 16 : searchList[start].toString().length()) + 1;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 598 of bug id Lang39
### Patch Diff Hash-SHA-256:

3d2f204c9c03192fc7191f51211aaf408f92139e51c0307c0db89147dd585e03

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = start + (start - 3);
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 599 of bug id Lang39
### Patch Diff Hash-SHA-256:

246956386bae8e02038149c689e1d7c465350bf932054a9c2d534e5703fdbc95

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase != increase) && (java.lang.Character.isWhitespace(text.charAt(increase))); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 600 of bug id Lang39
### Patch Diff Hash-SHA-256:

9b07986c77a917fafef5ce473a696ab5cbf39a76d215ad70e7d3e6d6ba4e331e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = start - 3;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 601 of bug id Lang39
### Patch Diff Hash-SHA-256:

ca5748be259c419825a64e3b750b86344b242346da71d0db447262d42b210a66

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = 3 * start;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 602 of bug id Lang39
### Patch Diff Hash-SHA-256:

b588741bf019a5d5a5cc3764dc6eba23b0a699f1212f8130e89ebc8fe24a5c09

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (start * 2) - 2;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 603 of bug id Lang39
### Patch Diff Hash-SHA-256:

d50c06b9aa716c7c67714744ec682529c9cac33ffa14d4be24c52667d71fdf49

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (text.length()) - increase;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 604 of bug id Lang39
### Patch Diff Hash-SHA-256:

b8a327b402812a6543448109e22a00ea70f6d7306459e331f916d440ed2fbb5d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (searchList[start].length()) == 0; i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 605 of bug id Lang39
### Patch Diff Hash-SHA-256:

7c9de839d815c0e61a9f3980d206247533e755f7606227fd029df8a8ee233b4e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = start * start;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 606 of bug id Lang39
### Patch Diff Hash-SHA-256:

0a8cab78fb7c729f08ec2417bfc2c46caad7237c4bd87885ecb839f382332bcc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (text.length()) - start;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 607 of bug id Lang39
### Patch Diff Hash-SHA-256:

f09b47643ddf2c83d505fc4bbedaaaf1ab363090f9aab631ab5f401bd9464c86

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; (increase < 0) || (increase > (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 608 of bug id Lang39
### Patch Diff Hash-SHA-256:

365ccb18bbc6f228414495c9e3dae81c710ccade65c5eeaa2fc9a8d38c7e0272

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (text.lastIndexOf(text, increase)) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 609 of bug id Lang39
### Patch Diff Hash-SHA-256:

fd133cae37da35b75ed619ff21068b8b22b84a8c8152e9a20047302ba51eacca

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (EMPTY.indexOf(EMPTY)) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 610 of bug id Lang39
### Patch Diff Hash-SHA-256:

47bc98156205e3a9df5feded874e8565995ec25243c9b47c3adcdfd1d06b034e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (text.indexOf(text, (increase + (text.length())))) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 611 of bug id Lang39
### Patch Diff Hash-SHA-256:

6e9ed9ba56f67b2a6763d676a8bec7b512af00ff8ce82cd7bfc52c2d52743092

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,7 +1162,7 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
+		for (int i = 0; ((text.length()) == 0) && (increase >= (text.length())); i++) {
 			int greater = (replacementList[i].length()) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 612 of bug id Lang39
### Patch Diff Hash-SHA-256:

a4bf84c00a1caf7e0d65f81c36a44c8da1af5a29e5e17e97abbcedde7d946c51

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = increase - 1;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 613 of bug id Lang39
### Patch Diff Hash-SHA-256:

7046f3650659bd91ca30f9e61cf5cd5b80e05b3fb51d219af196ff462f6b55ae

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = ((start + start) - start) + (text.length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 614 of bug id Lang39
### Patch Diff Hash-SHA-256:

145d7b71fada61938a0f4d3088359fb34467d6718656dc06d5b588d92d6da9d6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = textIndex + (searchList[start].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 615 of bug id Lang39
### Patch Diff Hash-SHA-256:

2ea25264ffd552edb6e79d6fb79c2db612096b55b38c41dabb2724b7f47f09fe

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (increase * 2) - 2;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 616 of bug id Lang39
### Patch Diff Hash-SHA-256:

18620a89bac8b53ccc223b0263db63a40f0fe441323457997ce6a80dc4909ff7

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = start / 2;
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 617 of bug id Lang39
### Patch Diff Hash-SHA-256:

3ca569cd0c64847cdcc3de9f71644c7d2c70300cca411bb51588b616a9bacb3d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1163,7 +1163,7 @@
 		int start = 0;
 		int increase = 0;
 		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
+			int greater = (text.indexOf(text, increase)) - (searchList[i].length());
 			if (greater > 0) {
 				increase += 3 * greater;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Lang7
### Patch Diff Hash-SHA-256:

422a1e32952078df7c0a2b326dec0b9a934ab49a9b21cf450b8d42d947aa8b7d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang7
### Patch Diff Hash-SHA-256:

cb310fe9bb973751c887b4a93bdd889d786f90501d8454e433b99ac6348062b2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (org.apache.commons.lang3.StringUtils.isEmpty(str)) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang7
### Patch Diff Hash-SHA-256:

f06f711c0283be221901c9b298616bd8ee534e39e6d473ae0cb03f13b7fa3ba6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (DOUBLE_MINUS_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang7
### Patch Diff Hash-SHA-256:

0bb4420c2faf1dfd297173cde4c3900b5654313ae6b72371fc686c06d1b5318a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (FLOAT_ZERO.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang7
### Patch Diff Hash-SHA-256:

41c32a545a90330fe051a75426a75aec86e36a1ace1cd65a1ceb7e70c66a826c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (DOUBLE_ZERO.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang7
### Patch Diff Hash-SHA-256:

f3735bfce803616b6eb8bf34d0f690b3e1fbd5b82a1f453092d1cd6cfa175c61

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (FLOAT_MINUS_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang7
### Patch Diff Hash-SHA-256:

522fe9b9895f93f46cc6817208d2b163c1b3687c6d0bc9b79a037703d17a2d12

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (DOUBLE_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang7
### Patch Diff Hash-SHA-256:

79b6cbdf4a5dd1a8c51f9c9fdedcb643b96c7353c373edc9f135826d6d096402

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (FLOAT_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Lang10
### Patch Diff Hash-SHA-256:

02ea9d87e2ac5d5f5bb31bc2b746a3392e5c64de3ca758646c8f91a85375fa4e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -154,7 +154,7 @@
 		boolean wasWhite = false;
 		for (int i = 0; i < (value.length()); ++i) {
 			char c = value.charAt(i);
-			if (java.lang.Character.isWhitespace(c)) {
+			if (value.startsWith("GMT")) {
 				if (!wasWhite) {
 					wasWhite = true;
 					regex.append("\\s*+");
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang10
### Patch Diff Hash-SHA-256:

de27c689ecfb582289152433a27ed3e6b1e29e941f521265dc4f387d338a7b04

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -154,7 +154,7 @@
 		boolean wasWhite = false;
 		for (int i = 0; i < (value.length()); ++i) {
 			char c = value.charAt(i);
-			if (java.lang.Character.isWhitespace(c)) {
+			if (value.endsWith("ZZ")) {
 				if (!wasWhite) {
 					wasWhite = true;
 					regex.append("\\s*+");
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang10
### Patch Diff Hash-SHA-256:

c547c479cba98e61f4ea9c69a5fdc421650f857315fad3739c9612373a1761e6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -213,7 +213,7 @@
 	org.apache.commons.lang3.time.FastDateParser.KeyValue[] getDisplayNames(int field) {
 		java.lang.Integer fieldInt = java.lang.Integer.valueOf(field);
 		org.apache.commons.lang3.time.FastDateParser.KeyValue[] fieldKeyValues = nameValues.get(fieldInt);
-		if (fieldKeyValues == null) {
+		if (field < (pattern.length())) {
 			java.text.DateFormatSymbols symbols = java.text.DateFormatSymbols.getInstance(locale);
 			switch (field) {
 				case java.util.Calendar.ERA :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang10
### Patch Diff Hash-SHA-256:

f8292abc01025ab526ac9fd419e83d63faa230c2820f7a490a8e33d356b8a36d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -154,7 +154,7 @@
 		boolean wasWhite = false;
 		for (int i = 0; i < (value.length()); ++i) {
 			char c = value.charAt(i);
-			if (java.lang.Character.isWhitespace(c)) {
+			if ((value.charAt(0)) == '+') {
 				if (!wasWhite) {
 					wasWhite = true;
 					regex.append("\\s*+");
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Lang24
### Patch Diff Hash-SHA-256:

8a1b0f0b8536705f69a30260c54f6f3170ac5cc8f01aa05b82d1bd99a39818d4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -715,7 +715,7 @@
 				return foundDigit;
 			}
 			if (((chars[i]) == 'l') || ((chars[i]) == 'L')) {
-				return foundDigit && (!hasExp);
+				return (!hasDecPoint) && (!hasExp);
 			}
 			return false;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang24
### Patch Diff Hash-SHA-256:

40950540b1d13b6e7f6da1144d2dc2a154ef25df01eaa96e61d1f1cb38e797ca

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -714,7 +714,7 @@
 			if ((!allowSigns) && (((((chars[i]) == 'd') || ((chars[i]) == 'D')) || ((chars[i]) == 'f')) || ((chars[i]) == 'F'))) {
 				return foundDigit;
 			}
-			if (((chars[i]) == 'l') || ((chars[i]) == 'L')) {
+			if (i == 5) {
 				return foundDigit && (!hasExp);
 			}
 			return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---