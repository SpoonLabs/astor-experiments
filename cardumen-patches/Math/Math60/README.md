
# Patches of Math60 from Defects4J 
Total patches 17
## Patch 1 of bug id Math60
### Patch Diff Hash-SHA-256:

f0497d4918d14ac6f6dbb437469e1c5d4ca83843c9f942b20fdae550a98639b6

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -50,11 +50,11 @@
 					throw new org.apache.commons.math.ConvergenceException(org.apache.commons.math.exception.util.LocalizedFormats.CONTINUED_FRACTION_INFINITY_DIVERGENCE, x);
 				}
 				infinite = true;
-				for (int i = 0; i < maxPower; i++) {
+				for (int i = 0; i < maxPower;) {
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = -((b - b) - b);
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math60
### Patch Diff Hash-SHA-256:

7fe2a62224e3d79e996f6b73e3303470b6d1469e1a355bfbe26de0670362260c

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -50,11 +50,11 @@
 					throw new org.apache.commons.math.ConvergenceException(org.apache.commons.math.exception.util.LocalizedFormats.CONTINUED_FRACTION_INFINITY_DIVERGENCE, x);
 				}
 				infinite = true;
-				for (int i = 0; i < maxPower; i++) {
+				for (int i = 0; i < maxPower;) {
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = (1.0 / 15.0) - (((b * (1.0 / 17.0)) * 15.0) / 16.0);
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math60
### Patch Diff Hash-SHA-256:

e317338401d73cf119251a37dc6bd0e2e3182364b0227ae770febef42a609d61

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -50,11 +50,11 @@
 					throw new org.apache.commons.math.ConvergenceException(org.apache.commons.math.exception.util.LocalizedFormats.CONTINUED_FRACTION_INFINITY_DIVERGENCE, x);
 				}
 				infinite = true;
-				for (int i = 0; i < maxPower; i++) {
+				for (int i = 0; i < maxPower;) {
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = (b * ((1.0 / 11.0) - (((b * ((1.0 / 13.0) - (((b * ((1.0 / 15.0) - (((b * (1.0 / 17.0)) * 15.0) / 16.0))) * 13.0) / 14.0))) * 11.0) / 12.0))) * 9.0;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math60
### Patch Diff Hash-SHA-256:

0b5b506abafb445f7e0e5c397dec5aabfe55789a29a79f5bd6210de859d81f7f

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -50,11 +50,11 @@
 					throw new org.apache.commons.math.ConvergenceException(org.apache.commons.math.exception.util.LocalizedFormats.CONTINUED_FRACTION_INFINITY_DIVERGENCE, x);
 				}
 				infinite = true;
-				for (int i = 0; i < maxPower; i++) {
+				for (int i = 0; i < maxPower;) {
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = b + 0.5;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math60
### Patch Diff Hash-SHA-256:

d3df6722a6810817854601a5cef5b0142b9ef9a627707977add722738617b239

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -50,11 +50,11 @@
 					throw new org.apache.commons.math.ConvergenceException(org.apache.commons.math.exception.util.LocalizedFormats.CONTINUED_FRACTION_INFINITY_DIVERGENCE, x);
 				}
 				infinite = true;
-				for (int i = 0; i < maxPower; i++) {
+				for (int i = 0; i < maxPower;) {
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = (b * b) + (-3.940510424527919E-20);
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math60
### Patch Diff Hash-SHA-256:

63762dfc8af60281bf7f9cac545d6a8587bfc451889b0a79321f78277726c2f5

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = b + 1.0;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math60
### Patch Diff Hash-SHA-256:

1e876daf74cc03bef1dec6e9dd466b7fe142ea7c7ed0fba436a2deb6b5d79d5f

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = b * b;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math60
### Patch Diff Hash-SHA-256:

bd7cc3a62c8f2176ab7dca569d0ba6a97493604ee72d2381aa24404b996eb704

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = (b - (b * b)) - ((2 * b) * b);
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math60
### Patch Diff Hash-SHA-256:

c695db4eadbd29ec439b91e8800a8d72afeede28ee08ff887b0ced27f601c72a

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = b * (1 / 5.0);
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math60
### Patch Diff Hash-SHA-256:

1948a9629fe876d21e5df6d62840339134b0b7507d2e951e2ee200634471027f

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = b * 8.0;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math60
### Patch Diff Hash-SHA-256:

26c0f85fe5be4160221335871b62e188cbe7665bc004da56d87c7e2a57aa352b

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = (b - (b * b)) - (b * b);
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math60
### Patch Diff Hash-SHA-256:

261cdd091398d43dd5408d6f34a7a90e8ad556a37feac263569d1b6acd97f74e

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = b * ((1 / 7.0) - (((b * (1 / 9.0)) * 7.0) / 8.0));
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math60
### Patch Diff Hash-SHA-256:

9b95dbfd7da0c864cbdff6fa26cf79eb430085292dfbc8b8659f3a5224694fbb

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = b - (b * b);
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math60
### Patch Diff Hash-SHA-256:

4b3346da50482937d304307205faf59e7a9282840d1e12a3d77c7d180586cc71

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = (b - b) - b;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math60
### Patch Diff Hash-SHA-256:

9a2c252f0bc279521103ce23b93d7795e7a7c6e2a23b70cec5ebc0697853f8e0

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = (b * b) * 2.0;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math60
### Patch Diff Hash-SHA-256:

fea230d4426a77007bb97c6c9e381ff4065b6b3e6debb2e91bb79578f49016fc

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = 1 - b;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math60
### Patch Diff Hash-SHA-256:

256ec27ebbcf68d40ed8036cf1f624d68f0b50e14483ff66714f3452188e668a

### Patch Diff:
```
--- /original/org/apache/commons/math/util/ContinuedFraction.java	
+++ /fixed/org/apache/commons/math/util/ContinuedFraction.java	
@@ -54,7 +54,7 @@
 					lastScaleFactor = scaleFactor;
 					scaleFactor *= scale;
 					if ((a != 0.0) && (a > b)) {
-						p2 = (p1 / lastScaleFactor) + ((b / scaleFactor) * p0);
+						p2 = 2.0 * b;
 						q2 = (q1 / lastScaleFactor) + ((b / scaleFactor) * q0);
 					}else
 						if (b != 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---