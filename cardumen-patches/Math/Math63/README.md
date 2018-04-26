
# Patches of Math63 from Defects4J 
Total patches 33
## Patch 1 of bug id Math63
### Patch Diff Hash-SHA-256:

3d685b1a50971bcd7dd205b57edb5302ca01f24f2d2bb3bad220a49820f44e10

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (org.apache.commons.math.util.MathUtils.equals(x, y, 1)) || ((org.apache.commons.math.util.FastMath.abs((y - x))) <= (SAFE_MIN));
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math63
### Patch Diff Hash-SHA-256:

090f8095648a285c8348f8b1e54ed0311f4cc1fdc4891251840e190768148ae5

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return x == y;
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math63
### Patch Diff Hash-SHA-256:

cd76b15c44b8cc8fda36cf74ab6bdc55c51aedea9973b21e2f01f5eb8e231f5e

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (org.apache.commons.math.util.MathUtils.equals(x, y, 1)) || ((org.apache.commons.math.util.FastMath.abs((y - x))) <= (EPSILON));
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math63
### Patch Diff Hash-SHA-256:

fab0ceeac14d389852e7762c4be270b954873ff9b11931bfcf80d01644f1c586

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(SAFE_MIN)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math63
### Patch Diff Hash-SHA-256:

f1a9c91c091003808bc4bee265fbb89b3dd35d23a052cf453dffd2ef6c5ef6c2

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(SAFE_MIN))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math63
### Patch Diff Hash-SHA-256:

63a56274535bdf5f05f21e4f8de53af64e478f3fbe521ad89f2227e75da63e07

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((EPSILON) == 0.0) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math63
### Patch Diff Hash-SHA-256:

d0f76bd772185f0fd527e0597eb141655b4d44dee75f4bc723e7e01cfdbf6b26

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((NAN_GAP) < 0) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math63
### Patch Diff Hash-SHA-256:

0d10027eeed915ef9b0cef59ef8dcfe879e4d13f90caf71db7aa663e640e772c

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -226,7 +226,7 @@
 				return false;
 			}
 		}
-		return true;
+		return (EPSILON) < (x[0]);
 	}
 
 	public static boolean equalsIncludingNaN(double[] x, double[] y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math63
### Patch Diff Hash-SHA-256:

fc3995ffbecb83fccce11eb18aafe6afda218c9dd55a2902642940dfaf3ce74f

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(TWO_PI))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math63
### Patch Diff Hash-SHA-256:

961baec66e82310909bad1f3abeef6fdb599330d73a212e9a67e0628042c04dc

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((org.apache.commons.math.util.MathUtils.equals(y, SAFE_MIN, x)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math63
### Patch Diff Hash-SHA-256:

6fa850d8d1cea70cdfd20bd5e4f56eeaad62e613b1ba623f1f3760f71a2de638

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isInfinite(TWO_PI)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math63
### Patch Diff Hash-SHA-256:

3725555f411d33588f29c2c082499c7b6e714433ea4791d9b84daaf0d28e439e

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((NAN_GAP) == (-1)) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math63
### Patch Diff Hash-SHA-256:

eeca2711eedac4b563f4049637ed8a9ac4fd33500ae9f1a70c25f2593509e505

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return org.apache.commons.math.util.MathUtils.equals(y, x, EPSILON);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math63
### Patch Diff Hash-SHA-256:

19a903a68ad0a163abf9e549ab75946cb84885f217d8f12106153195169d2cf8

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return y == x;
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math63
### Patch Diff Hash-SHA-256:

c26f3def72fa1fa03fd3abeb1b16a27ff0f7332f6babf02a76170d7994f40b27

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isInfinite(x))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math63
### Patch Diff Hash-SHA-256:

26257dfbae78eac823681f128d9de2f38fcccf7db107fc201c408eb9bb7c0e46

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (y >= x) && (y <= x);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math63
### Patch Diff Hash-SHA-256:

34a0f8befadc93c844ba205f4fcc3527c4796bf2ecaaa6699321be975e5284c7

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return org.apache.commons.math.util.MathUtils.equals(x, y, 1);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math63
### Patch Diff Hash-SHA-256:

0043d8f5e7e70df877771511a8ed5dc6fe4e05a9a05b444c7dd27310317e4266

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return false || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math63
### Patch Diff Hash-SHA-256:

1d4bb980caf78991931f500ea9d000189b13792a76c0345de63b6308166788bf

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(x)) && (org.apache.commons.math.util.MathUtils.equals(x, y, 1))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math63
### Patch Diff Hash-SHA-256:

7e83201ad9c13f4ca16ebdb34bfdb628acd58d4656170042eaa869f329a1a3fa

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isInfinite(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math63
### Patch Diff Hash-SHA-256:

ab3d213ce9031854dfa3280706f9e2f6ff2692dc2c30b88175b60e289f2c1fed

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isInfinite(TWO_PI))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math63
### Patch Diff Hash-SHA-256:

2c3ac0b81898024c3ce49b8c7bebf6b839a329151bf08a7f763ce8c988827671

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((x > 0.5) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math63
### Patch Diff Hash-SHA-256:

cc5fc58e72c4ebdb4b2f9f73f27efac8ff4355604597ad49baa1e0cacb849d20

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((org.apache.commons.math.util.MathUtils.equals(x, x, x)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math63
### Patch Diff Hash-SHA-256:

90a9263f07aa92734626da1fcebf14620fba74dab200d3d30afbbb3bfcf80b09

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((((SGN_MASK) / (SGN_MASK)) <= (SGN_MASK)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math63
### Patch Diff Hash-SHA-256:

54b01da1d68fa5517dd1dcde7fefb8eea5e133674a285bf9d4aeb81e49490036

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((java.lang.Double.isNaN(x)) && (x == 0.0)) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math63
### Patch Diff Hash-SHA-256:

8a43d5a9f700405e0330729c4d39ef87329e124babfc4f14b483506259fb7860

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((NAN_GAP) <= 66) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math63
### Patch Diff Hash-SHA-256:

4024d0369d1c24f507033d43401b534954b5a66ac22ed75013018891fb2633fc

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (org.apache.commons.math.util.MathUtils.equals(y, x, 1)) || ((org.apache.commons.math.util.FastMath.abs((x - y))) <= (EPSILON));
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math63
### Patch Diff Hash-SHA-256:

c37a0754693fedc47fb41030ad5a566221ec986458eb257e408ff5bdba21072e

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (org.apache.commons.math.util.MathUtils.equals(y, x, 1)) || ((org.apache.commons.math.util.FastMath.abs((x - y))) <= (SAFE_MIN));
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math63
### Patch Diff Hash-SHA-256:

c524fe4ac9e7efadd91ef722960d04d875d45963072febe36e2f179942cea284

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (x == (-1)) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math63
### Patch Diff Hash-SHA-256:

fff435026e0e9d598d29031492ce958e2abad809708df3724e3264e2d3651313

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((org.apache.commons.math.util.MathUtils.equals(x, x, 1)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math63
### Patch Diff Hash-SHA-256:

05d20c6eaa295cc118d0f91d9b42b910371da2a03d6dc9eea3c269510b1b4252

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return ((SGN_MASK) == 0L) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math63
### Patch Diff Hash-SHA-256:

f48a78b687009d45284ea35e3c3b4082bf1c1e99b1345fbe00efe09673183cb4

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (((1 / x) < 0.0) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math63
### Patch Diff Hash-SHA-256:

e053130681b2b6efeb5fedd93f0ad84097eb07ace670e8a20437a9fe985d6af5

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -181,7 +181,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (((NS) >= (org.apache.commons.math.util.MathUtils.ZS)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---