
# Patches of Math46 from Defects4J 
Total patches 15
## Patch 1 of bug id Math46
### Patch Diff Hash-SHA-256:

f1778c450f40505aeba8becacb56447b5573d2888ea0051f1525bafa7e3132ee

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return (((((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(imaginary))) || (java.lang.Double.isNaN(imaginary))) || ((imaginary) < 0)) || ((imaginary) > 1)) || ((imaginary) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math46
### Patch Diff Hash-SHA-256:

4227610ab0d4a4e27cf10706224d4a9a2490cb30eaa91e75c552cf019d66dc18

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((real) - 1) != 0 ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math46
### Patch Diff Hash-SHA-256:

7be576e8dd3ca643a6ee251ba6b8d7b999d75379563f52570ddbddd28447400d

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((((((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(real))) || ((real) < 0)) || ((real) > 1)) || ((real) <= 0.0)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math46
### Patch Diff Hash-SHA-256:

360c17aab61a87634c7c15e47e2ed916d51c983130a8be5b24092aec53f38479

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return (((((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(real))) || ((real) < 0)) || ((real) > 1)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math46
### Patch Diff Hash-SHA-256:

a73c352750697557a3f540a48de1cecb974c28699db255b63d5267f13fad0008

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((((((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(imaginary))) || ((imaginary) < 0)) || ((imaginary) > 1)) || ((real) <= 0.0)) || ((imaginary) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math46
### Patch Diff Hash-SHA-256:

4cea0c7bba88685b8b8971eb135324ad5ddea236315fedcff38a32df7c53cf2c

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((org.apache.commons.math.util.FastMath.floor(imaginary)) / 2.0) == (org.apache.commons.math.util.FastMath.floor(((java.lang.Math.floor(imaginary)) / 2.0))) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math46
### Patch Diff Hash-SHA-256:

84fc53c2c94cb215f5b35ae683b779b89524146374e1f18301927b20a528400f

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((((((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(imaginary))) || ((real) < 0)) || ((real) > 1)) || ((real) <= 0.0)) || ((imaginary) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math46
### Patch Diff Hash-SHA-256:

c24f32e194c6d2001cbf514fabae78201d300fe148ae5a7a4862425711e83890

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return (((((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(real))) || ((imaginary) < 0)) || ((imaginary) > 1)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math46
### Patch Diff Hash-SHA-256:

467b7a6e7a6bb89dc25d25adfbe60f8ea02d0dc16a3b0fc6fbbf03d5528522ec

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((imaginary) - 1) != 0 ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math46
### Patch Diff Hash-SHA-256:

509a84e7e48edf52d2780bdc119107e1edb02145b6c97f2e69e21de961c386e8

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((((((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(real))) || ((imaginary) < 0)) || ((imaginary) > 1)) || ((real) <= 0.0)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math46
### Patch Diff Hash-SHA-256:

15803bf483b03b1d503cbf57055ff0470c117a2af8e9c3e81ff4721cd7d31f33

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((((((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(imaginary))) || (java.lang.Double.isNaN(real))) || ((imaginary) < 0)) || ((imaginary) > 1)) || ((imaginary) <= 0.0)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math46
### Patch Diff Hash-SHA-256:

718b79ffbd9649ec372f21b4c648d15a705ee51bd96b0112ca7df70fb5fbffdb

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return (((((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(imaginary))) || (java.lang.Double.isNaN(real))) || ((imaginary) < 0)) || ((imaginary) > 1)) || ((imaginary) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math46
### Patch Diff Hash-SHA-256:

7020b0bd4e5a55fed7412ff7ec3a3f911554bd735b0e81d7eb3ff551c9d55a82

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return (((((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(imaginary))) || ((real) < 0)) || ((real) > 1)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math46
### Patch Diff Hash-SHA-256:

0bb07b080ef6563546ae091c8538be0ac60ae38301486e178f203466f13ecd91

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return (((((java.lang.Double.isNaN(imaginary)) || (java.lang.Double.isNaN(real))) || (java.lang.Double.isNaN(imaginary))) || ((imaginary) < 0)) || ((imaginary) > 1)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math46
### Patch Diff Hash-SHA-256:

148745e50977d1bd0184bf1995c71e0d274c6a7b3427ca7c063c992a2ab9b9ec

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -88,7 +88,7 @@
 			return org.apache.commons.math.complex.Complex.NaN;
 		}
 		if (divisor.isZero) {
-			return isZero ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
+			return ((((((java.lang.Double.isNaN(real)) || (java.lang.Double.isNaN(imaginary))) || (java.lang.Double.isNaN(real))) || ((real) < 0)) || ((real) > 1)) || ((imaginary) <= 0.0)) || ((real) <= 0.0) ? org.apache.commons.math.complex.Complex.NaN : org.apache.commons.math.complex.Complex.INF;
 		}
 		if ((divisor.isInfinite()) && (!(isInfinite()))) {
 			return org.apache.commons.math.complex.Complex.ZERO;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---