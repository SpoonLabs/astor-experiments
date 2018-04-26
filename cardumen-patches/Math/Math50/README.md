
# Patches of Math50 from Defects4J 
Total patches 722
## Patch 1 of bug id Math50
### Patch Diff Hash-SHA-256:

2310b6a8dfe459f8a49f95e6fd98592c198ad32ae81cfdda5c57388044c9e4b3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(f1)) <= ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math50
### Patch Diff Hash-SHA-256:

a84818a6f4eaa6991e2977e01de8aa7e32e6a6922a80d082d87e7a920d09926a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 < f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math50
### Patch Diff Hash-SHA-256:

ce2aae3f36f21582db63acd84aa4f671808f697ec59f56494320d20c31fdc8ba

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x1 >= 0) && (x <= 0)) || ((x1 <= 0) && (x >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math50
### Patch Diff Hash-SHA-256:

c433433c4e956ebb4744aa736f2fe77d6169d7603bce0dd9b3de5bc94aba8cd9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math50
### Patch Diff Hash-SHA-256:

54f4a532ad549dcfe6a71992ad279eedd8f0cd7329509eb176fe49ba36ea536b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math50
### Patch Diff Hash-SHA-256:

2f4b8a9d912f4880dd55bca930db97dd2db5c9e3c638540900d74f6612b670ba

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 >= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math50
### Patch Diff Hash-SHA-256:

3b3982f9abeb24306231838b105e266d12781e0898e52b4418993fa4e0eec67d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math50
### Patch Diff Hash-SHA-256:

38ea529cca19ae02452357889be08e263e209295d2d8388c48973dac21128106

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math50
### Patch Diff Hash-SHA-256:

21d7e7b428e6db2103ddf2a2f244ba37f6b5eac2d8d213faeb41fa129bef37db

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((ftol <= 0) && (x >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math50
### Patch Diff Hash-SHA-256:

715eab4fcb066ef93a6137ce883049dd6680b4214930cd0c57baad84148264a8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 <= 0) && ((DEFAULT_ABSOLUTE_ACCURACY) >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math50
### Patch Diff Hash-SHA-256:

62bdf08acd5950ecfe5b004f313f2810ac3be75bb0158a17f6439305c6e1c57f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((rtol <= 0) && (f1 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math50
### Patch Diff Hash-SHA-256:

92ada221ca68c6e7c3982ebb86af5c8617f249686b4f7d8544711c5367c356aa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol < (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math50
### Patch Diff Hash-SHA-256:

2b4d81ee47c2953b865df25b828d6563d80a826bd79e840e95c589d631349286

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math50
### Patch Diff Hash-SHA-256:

ef899b84525f62606f21686d28faf5af89cb54c4f8ecefa06ac4ebd94dbfadad

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math50
### Patch Diff Hash-SHA-256:

9254e04899c025a0d0f4b8c9157451f8c5e5efc1e7c1553a95fe8c85922f9e16

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math50
### Patch Diff Hash-SHA-256:

8eb433e9ae3470a97f518e1a382cd76c2c621dcdc8a1655b472dcd7c5dbbd3dd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x >= 0) && (rtol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math50
### Patch Diff Hash-SHA-256:

51cf8e09ee7b556c410d3bf61a70d019b993bc1d730d195667b6acee657777a3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f0 >= 0) && (x <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math50
### Patch Diff Hash-SHA-256:

0ced211d2296a7841e2443515ecffd72534dca3956155e407a6659cf369f8cf9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math50
### Patch Diff Hash-SHA-256:

2a8d94e6e833f8dc5c9becc86b0a0cdb99cde8375c36672589b4e4b69dadbc17

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((x1 - x0))) < (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math50
### Patch Diff Hash-SHA-256:

6e0bc0609b93f66c766def1d72457d1fc0ef5b2182b1f5394a23c73831eadb5b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 * fx) < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math50
### Patch Diff Hash-SHA-256:

2397f3dadc2cf93d7958c95d98c5fb01b1d6d83de523109f66b16c6a181591d5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math50
### Patch Diff Hash-SHA-256:

bb85c3aeed23204bc543dfecd40f5ee29709fbf889d4b8a5aa27f3e04fe24fc2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 >= x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math50
### Patch Diff Hash-SHA-256:

8c7c4502d0f1c95b2db9d5e57c57f229d9a6d23906f0fc955f7c4441d00bb306

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 <= 0) && (atol >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math50
### Patch Diff Hash-SHA-256:

690044824e3d60298f23649bf577136bbb483cc2f48f1763c1bc8013853ce943

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx * x) > 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math50
### Patch Diff Hash-SHA-256:

22172e39b93c084952b3cae98473504fac35b680baeb46aba34b3760ebc88da7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 >= 0) && (x0 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math50
### Patch Diff Hash-SHA-256:

88ace685c3b14d9f2594c5ab66d9c9ab74b77667475808105baaf15d6a2bd223

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math50
### Patch Diff Hash-SHA-256:

d4538f50f268a036ba49b5586cd50051421e0786284b15659757c758cbf95961

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math50
### Patch Diff Hash-SHA-256:

e2aa4e08f4a01d24566020e1a29aa1e97dee036e98d5c38f780d3f93365b373c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math50
### Patch Diff Hash-SHA-256:

225220c5b1b6f37dbafa44b624aada0e5731963afde4f5e4bb219c98ac6fc9e3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x < x1) && (x1 < x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math50
### Patch Diff Hash-SHA-256:

19b86db676087b34a9e904e92876bf6b6a8c28cc942c390f7e5ce7611d9d2346

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((atol <= 0) && (x0 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math50
### Patch Diff Hash-SHA-256:

9cc419ce107a47719d6ec90df782b513ee6a512125377357b45b03125d8e799b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math50
### Patch Diff Hash-SHA-256:

b1beead1a9e171c015aaa9e1e0b7ffe7629ae08465c191cb7f5682be0ea369aa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol >= x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math50
### Patch Diff Hash-SHA-256:

c3b8731d686829d4b57c2341d9b87f15cdb99a9c7c13d74686c850bb88ed9d92

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math50
### Patch Diff Hash-SHA-256:

e441a390c640ff3cdf2ec90bc8f176692331d9be100085aa3278cf5b051b47a4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math50
### Patch Diff Hash-SHA-256:

0a59132e545ecc3c0dd1a1d89bf9a23e74b10bc86ce806083fa278759ea633d3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < f0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math50
### Patch Diff Hash-SHA-256:

839fe1cb347f3ae440863ca01d9d7de5a72881e724a768d6ab6e06cfe97d189f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math50
### Patch Diff Hash-SHA-256:

8ad8c15bfa445e5ed9b20456f78fb9f72505f4addd830439dd358899e9ed3be9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x < (DEFAULT_ABSOLUTE_ACCURACY)) && ((DEFAULT_ABSOLUTE_ACCURACY) < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math50
### Patch Diff Hash-SHA-256:

2cceb650dcf8cf57672a2a7f58b48bb8745d3363eae3bb62b4cfae0d92f60149

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math50
### Patch Diff Hash-SHA-256:

599d878e9b5d0f0569df9acee6c4976dca59c57bf87666d451d02c0b8bc5681c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math50
### Patch Diff Hash-SHA-256:

77f23e782a8f7a6733fad0ec7187f41c9ad4f9859abb73ebe34a74fb8d878f81

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 <= 0) && (x >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math50
### Patch Diff Hash-SHA-256:

5006dc8ea89bcf0c4e7750dfc66960259efc55f2f801d1dfa9d0ad30313d4e51

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math50
### Patch Diff Hash-SHA-256:

670a536c89271ca98a87e56d52d36941556b8bcc4ead630ec4b3799355b93a63

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math50
### Patch Diff Hash-SHA-256:

a4d26a4b0a98c2f9f42da528a3595cda4b9e300f6ef9d58cc09177aff7154db9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math50
### Patch Diff Hash-SHA-256:

11812e8ef58ada5593b5da56a4fa61d6b137e0ec9f25c557a91b2e865e50efa2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 >= rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math50
### Patch Diff Hash-SHA-256:

2a26abe0457357f5d958e9d6cd77bd6b50a73f17d16925e3d15e0462f11b1d0e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((fx >= 0) && (fx <= 0)) || ((fx <= 0) && (fx >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math50
### Patch Diff Hash-SHA-256:

510a5dbeec1a1e16d3745300526347e788f501f268edc2abc578f88090c8c79e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 <= 0) && (f1 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math50
### Patch Diff Hash-SHA-256:

c0dfac731a43124d1fb4dc99b116784eae2cd34d546d446ff37728b653217d00

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx < f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math50
### Patch Diff Hash-SHA-256:

31c865ce020ae8d5b354ea88c7148282016aee24a141e7137e0eb8d301847788

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 >= 0) && (f1 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math50
### Patch Diff Hash-SHA-256:

ea597c47ace8bbd067640ec39f259be216c1f319cab8d8a479a5b0458b4e1219

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < x1) && (x1 < x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math50
### Patch Diff Hash-SHA-256:

fee07b31b3d9c87e85f839798c6201facef85f639f60894f2a6d7bc0892011fe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math50
### Patch Diff Hash-SHA-256:

14a9041ad8dddb09bd3616b969ec43bb0b80f84cf182b0b4781110b2fdc0df12

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math50
### Patch Diff Hash-SHA-256:

30c3da744d435f89f4ab1784c741ddddb14343d214eda7c040075fa3d8a09e3a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx < x1) && (x1 < x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math50
### Patch Diff Hash-SHA-256:

d7d74fa4b8d06fc4f9e77e9dbc355c9ed7d02dc64f1e897e1ed19049f6b106cc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math50
### Patch Diff Hash-SHA-256:

63d203b1bc166f7884445e9540cf87d3ee6c2cd29ab7708351cb73da960e051c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol < rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math50
### Patch Diff Hash-SHA-256:

2df7b371ff2b87c6f0b22dcaea96b7140cd91825ecae428561df130e5bf72975

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math50
### Patch Diff Hash-SHA-256:

4d227bf54a66d95e526376c50ae399600545f581aa04e5e3a4d1e9238a8f0576

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x < x) && (x < x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math50
### Patch Diff Hash-SHA-256:

0279654957e73de05c7102e42e9847be97cd3e06ecf920039850a9f5504d693e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((rtol >= 0) && (atol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math50
### Patch Diff Hash-SHA-256:

bc47298e7faf3122ec8083c90bca7a1cd8f3d0fdc06db85b3424c95695b3b3b5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x * fx) > 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math50
### Patch Diff Hash-SHA-256:

2c0f2404fd2c84d4ea5c8f222bafd72d7582511783306035a558f0d75de8ecfd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.isSequence(DEFAULT_ABSOLUTE_ACCURACY, f0, fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math50
### Patch Diff Hash-SHA-256:

d3fa7c7c20d47edc27adc2ec7b6580d7f43e9b5351e566f416f4fe89baaf5f45

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math50
### Patch Diff Hash-SHA-256:

85d4607fe39b85c275e7140f36ffb38158345de78d1872fd69308efd1ddcb0a5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol < (-1.0E-10)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math50
### Patch Diff Hash-SHA-256:

005fd92e0d8e35e80d1a656f58b3031c19d0251bc1121a9cd0de60d056c3d390

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((getEvaluations()) == 1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math50
### Patch Diff Hash-SHA-256:

6dc9e9a24ac942f17669e4d32fd203eb6971a11192d909d88e3e5e4f1dd13b89

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol > 100) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math50
### Patch Diff Hash-SHA-256:

f96348b048e80b72a1acf16f32e67d7a4fa397b5fdba7d5aa071341379a21eb7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(rtol)) > (org.apache.commons.math.util.FastMath.abs(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math50
### Patch Diff Hash-SHA-256:

e33b3031d7616f7dbacbb349a418e3b88467c18d3004225440d1a7d9ecbcaec4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > 0.167) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math50
### Patch Diff Hash-SHA-256:

e722a678b4c6ab7cd87af98365d6796f2f386b5f2c114c05bffc4859711318ed

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 1.0E-10) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math50
### Patch Diff Hash-SHA-256:

c88baf76dd7d5afae00e48bc0173fef2333dffaa22d40bca8b4f20895975d91f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math50
### Patch Diff Hash-SHA-256:

c4368dce1edf61c63f1961740cc968a3cb5599fcbdd5733159af6c1914ec2772

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math50
### Patch Diff Hash-SHA-256:

605a858db5f1709113fd72b57fba0ae28a028076e1ae0f3db07434f59ab34fab

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (false) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math50
### Patch Diff Hash-SHA-256:

124282aab0491ee3c6693390da1dc519323e6336cc87e4397ecceb7fafc9f032

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) <= 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math50
### Patch Diff Hash-SHA-256:

542371abfd48058a505f50d823a8ed0302f34af7aca259d4f1c47d41decc5d5e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > 1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math50
### Patch Diff Hash-SHA-256:

ea564df2d8b10ff72632581874d57ebcfc845395b41a7725ff3fa2ba38cbf96e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol < 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math50
### Patch Diff Hash-SHA-256:

037bdbecd0829ed8b7f04499c08d9652387f2998c305554980f198cef9ec84a1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math50
### Patch Diff Hash-SHA-256:

6d0bb80b5a783360856f8900a4276911372abeeef93fefc7f6359314ed26bfd6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math50
### Patch Diff Hash-SHA-256:

235f3313530c825b26da003cbcb01fd321d2537033201ea766995fe34976c4a8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math50
### Patch Diff Hash-SHA-256:

43efb48655a8d6ce20eb184df6d2292c1a4f5c1688c5b167652ebc273054a5e1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x == (-1.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math50
### Patch Diff Hash-SHA-256:

885f2dd0c5f2e1d47598e6ce833b1e602401df279d702162bdc555eacd48ae24

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math50
### Patch Diff Hash-SHA-256:

d3fd9fff775b93223f277d2e59a5f585beba1675bb6d7d89f542e13ff509f55b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math50
### Patch Diff Hash-SHA-256:

f4895a43784eea24f4131c0c93c7622ed42fe42f7b9d93d521f5443e411fb60c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 > 100) || (x0 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math50
### Patch Diff Hash-SHA-256:

40cb080c93f82ead28100f14de8000436db944fca071de2beb90771366338167

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < (DEFAULT_ABSOLUTE_ACCURACY)) || (x1 > x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math50
### Patch Diff Hash-SHA-256:

410e4555c36b73b44d85c00e93c53691e0b2b21e236a5f729788adda196106c3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 < 1.0E-15) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math50
### Patch Diff Hash-SHA-256:

ecfc31c415bd0499541645093849deb9af601f6ad55473bb169e4f598c8b3079

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 >= 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math50
### Patch Diff Hash-SHA-256:

82a59e3a843dad8c62cfb3c73c197eb6f009d9589beb2348e2a8b610046b5c02

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(rtol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math50
### Patch Diff Hash-SHA-256:

43c6664337b188312bb8d08e834d6d4bd77d4c5aa127d7d2ab2ef4d2e27251a9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math50
### Patch Diff Hash-SHA-256:

8ce4fc094c02c48c91346f68a8f270ea7011dae200269825715f27d4706c41bd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((inverted || inverted) && (!inverted)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math50
### Patch Diff Hash-SHA-256:

b38b8dd28bb8a953747ae46b01323deaab244ed224d5f996d0395bdbdfd15141

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math50
### Patch Diff Hash-SHA-256:

d7603c0fc4ea8e3538cb2220ae6d60f998b341b8c033767427ef575dfd8e3911

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > f0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math50
### Patch Diff Hash-SHA-256:

f9252de79a67128bb70d588b5966f48390d76760388449023d5e6bae5fbd6c8f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > 1.633123935319537E16) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math50
### Patch Diff Hash-SHA-256:

ce6028470895b46e9f68fa587672f4476134f92d110d298571f89eefbb1a3974

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 > 1.5707963267948966) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math50
### Patch Diff Hash-SHA-256:

30f2ef817ab6ff67a213b750d33df83ce8b16551d11604a8555a36204236d7e8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx - x0) > (0.95 * (fx - x))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math50
### Patch Diff Hash-SHA-256:

fead869d5aec0f6681b2884d900e984c48bb05e04e41bef1f2ebd846ce89ede7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > 1.633123935319537E16) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math50
### Patch Diff Hash-SHA-256:

2c01c3337621375e8e583414b49badb714f4f342a4b19236f8e9c106efa9a813

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 <= (-1.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math50
### Patch Diff Hash-SHA-256:

c250012fbde29724d2f88042591244a67705c8e21fdbad1c542dc12695613c41

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math50
### Patch Diff Hash-SHA-256:

60b19dda5935187eabf99bbb371386b49d56830e5616137b3e050e7e5f9bfac0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math50
### Patch Diff Hash-SHA-256:

ae6042acce145c9812efab59ad16827bdda717baa201f3e414df26eb4dad463f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((ftol != 0.0) && (ftol > x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math50
### Patch Diff Hash-SHA-256:

6fd4f46fdf48eb37038adccab89cd228f2bee67f5e86bcd2bfe6bc8dc32c3f19

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(ftol)) && (ftol < 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math50
### Patch Diff Hash-SHA-256:

ebc7968af48677872f56b2946757b23c014008eddd1710198c167dd4d7c463b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 == (-1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math50
### Patch Diff Hash-SHA-256:

69cab917900d1fa1a31010c434f2839ea5222528981ed5bb29ca0b4fbcbaa011

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 == 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math50
### Patch Diff Hash-SHA-256:

41927d41e76c083d679dcaefa8699c1584cf1ceaee34b015f83d90ad7f44020c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol > 0.9999) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math50
### Patch Diff Hash-SHA-256:

7c7fa9b50270ff899ae0396a2fb855dddba975593942c14346b149840b8c12d5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol == ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math50
### Patch Diff Hash-SHA-256:

875921241977be88793429a4848498a2a3e12a87e505b27f97b50600402b7100

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((atol < 0.0) || ((1 / atol) < 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math50
### Patch Diff Hash-SHA-256:

d109290583801802decc0ab594626506d886c4d8a4eae46587c242514bf00a6e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x <= ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math50
### Patch Diff Hash-SHA-256:

9539569731ea4129361506e5aa89d2282e0db4dbaf34da0c35d24d05043b821b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx < fx) && (fx < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math50
### Patch Diff Hash-SHA-256:

cae702ecf5739b6f8ef4a91a582b04e7d7b5bb866a628b91b795cee90f3c327b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math50
### Patch Diff Hash-SHA-256:

ade96102a566dd17d30929dd865b65a3cab82fc679576d48ff75f7d4ffa4f07a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > 3294198.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math50
### Patch Diff Hash-SHA-256:

1f06cc5ed8863bcfad4fb9e3b629b25f7a7b3ad1d3800c230ccadcac7d7f24e2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.util.MathUtils.equals(x1, x0, 1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math50
### Patch Diff Hash-SHA-256:

d02518224e22ba89da104868233624b4ffcdf96c740d341c656f1b72c16f9b3b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx - fx) > (0.95 * (x - fx))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math50
### Patch Diff Hash-SHA-256:

77ce17afcb251e277c9648c843abefe74143255b826d9c65da58e9f6039ce9c7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 * x0) <= ((x0 * 1.0E-4) * x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math50
### Patch Diff Hash-SHA-256:

af77b5109c3d2fd19ee4ff334a2d87e6886b51061e6e2e29d4ee4662477e20ff

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Math50
### Patch Diff Hash-SHA-256:

69a57e1a9cf95b813dea605296185690cfe4beebfbd7e8aa1f042c6f4f256b7c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Math50
### Patch Diff Hash-SHA-256:

e86d472defea663a825c94e09583599baad4abe22aaf27217bb4da94e0751da1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (inverted ^ inverted) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Math50
### Patch Diff Hash-SHA-256:

f5c9f2f0a59850b9be3767a9795ce070a32f179379171dcd8e42c4ab14bd22b6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((org.apache.commons.math.util.FastMath.abs(f1)) <= (1.0E-6 * fx)) && (x >= 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Math50
### Patch Diff Hash-SHA-256:

1510bad0e234af31dda5d36e8a33849bccc9ef12f29c97c58584fa82375945db

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Math50
### Patch Diff Hash-SHA-256:

93eb91f915aafa820d1fa1614e272b2fa40cb7da006e0cfd539b9b1bbbf9cbcc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Math50
### Patch Diff Hash-SHA-256:

60ee236f6b0003944682b4a4c490c33572d2fcc468d48afa1c4a632b8b825863

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > 4) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Math50
### Patch Diff Hash-SHA-256:

58303ed119f5bfdd1e18d9ef95773c290187a37af4cbecc31ae1a4b8dcd73a93

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x != x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Math50
### Patch Diff Hash-SHA-256:

d86e4f7e7dab81366cb0c4df8802bcd6cd469058e516ea6ecac672dacd69e9e1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 >= 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Math50
### Patch Diff Hash-SHA-256:

af2fd0e0e5b45d7d0adf1d659ae4928b531224b020c5618b2273215233467fd9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 - x) > (0.95 * (x0 - fx))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Math50
### Patch Diff Hash-SHA-256:

f0161a91c47861e3f00483c1f6588b7bdbaf54ee9521f593117faceddd43b15b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((x - ftol))) <= (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Math50
### Patch Diff Hash-SHA-256:

446b9be19e92ef51cd77e0345647bd65a7d6c8003bcbabb9af3f014b7925a9fe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isNaN(x0)) || (java.lang.Double.isNaN(ftol))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Math50
### Patch Diff Hash-SHA-256:

16f1db694a0713c53d099daab92aa80eafe98346108813d00885637e5526676a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isNaN(x1)) || (java.lang.Double.isNaN(x0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Math50
### Patch Diff Hash-SHA-256:

bc07512e813ac42cad8509403c288d8c39609a1e1ca516e0d2c8aeef54f3de2f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(f1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Math50
### Patch Diff Hash-SHA-256:

427b47208f09147e4d26f235ba6162849f4049c49530be85a78ce6b36c6aa7b3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x <= (0.1 * x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Math50
### Patch Diff Hash-SHA-256:

aeef1a270ca6af96798edc61ee4f02a880f8fea8bd9066f485b990d148f8beff

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((org.apache.commons.math.util.FastMath.abs(x1)) <= (DEFAULT_ABSOLUTE_ACCURACY)) || (org.apache.commons.math.util.MathUtils.equals(f1, 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Math50
### Patch Diff Hash-SHA-256:

d571893a0a677b7d952d9a505d4b5ebb768983d8044c9fb913f31ca4fb8e73a8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(rtol)) > (0.001 * (org.apache.commons.math.util.FastMath.abs(f0)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Math50
### Patch Diff Hash-SHA-256:

1326e91b9deb117818fe562a84faa64437221c2eda0f6f1a514ce45bdef42a83

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > 1.0E-10) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Math50
### Patch Diff Hash-SHA-256:

ec85058194089645216eda9e260ae4e1c95ed35933eb5a91ff0c886af0426410

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx > 0) && (atol > 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Math50
### Patch Diff Hash-SHA-256:

0c167bf0974c87a31790584975c5751d0ae298241af2775baaf03281b8e689c3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol != ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Math50
### Patch Diff Hash-SHA-256:

a947d51ef3fb4942a56ab1120217724932127f2b931ed4bdb481b499747219c2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((((DEFAULT_ABSOLUTE_ACCURACY) < (DEFAULT_ABSOLUTE_ACCURACY)) && (((DEFAULT_ABSOLUTE_ACCURACY) - (DEFAULT_ABSOLUTE_ACCURACY)) > (0.95 * ((DEFAULT_ABSOLUTE_ACCURACY) - (DEFAULT_ABSOLUTE_ACCURACY))))) || (((DEFAULT_ABSOLUTE_ACCURACY) > (DEFAULT_ABSOLUTE_ACCURACY)) && (((DEFAULT_ABSOLUTE_ACCURACY) - (DEFAULT_ABSOLUTE_ACCURACY)) > (0.95 * ((DEFAULT_ABSOLUTE_ACCURACY) - (DEFAULT_ABSOLUTE_ACCURACY)))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Math50
### Patch Diff Hash-SHA-256:

b378259d98afa11fdaeafd19d322e1285ebb19094b34f2f9a41a1f508bdb1427

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) < (DEFAULT_ABSOLUTE_ACCURACY)) && (((DEFAULT_ABSOLUTE_ACCURACY) - (DEFAULT_ABSOLUTE_ACCURACY)) > (0.95 * (fx - (DEFAULT_ABSOLUTE_ACCURACY))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Math50
### Patch Diff Hash-SHA-256:

6c96d2650a150676a1433637c421b436d32ce75f36e5428342276e434406e4b0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 <= 2) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Math50
### Patch Diff Hash-SHA-256:

39a71b22ce0701f19ff5bb74fb016b3fba5736edf880c04ae0b3742f5c9a34de

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < ((DEFAULT_ABSOLUTE_ACCURACY) + 1.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Math50
### Patch Diff Hash-SHA-256:

ed7c647429db50565a4648a8e0017dd24c07130f20f8f2536092c769d8c3e64d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) >= (((1.5 * x) * x) - (org.apache.commons.math.util.FastMath.abs((x * x))))) || ((DEFAULT_ABSOLUTE_ACCURACY) >= (org.apache.commons.math.util.FastMath.abs(((0.5 * x) * x))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Math50
### Patch Diff Hash-SHA-256:

aa556b88b8b3f5519cc4b400ee0e583db46abb7c0f31af32ec21fabbeae85ffb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(f1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Math50
### Patch Diff Hash-SHA-256:

5469aaaf0e63e83be40cce004171113bff714234ff7219d895cf31059a7aa318

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((method) == null) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Math50
### Patch Diff Hash-SHA-256:

4592ede5a0c2419f8fa68e195192f23efdfc44697f43eb162b823a7d1f14055b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((x - fx))) < (0.1 * (x + fx))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Math50
### Patch Diff Hash-SHA-256:

b1554e7cd8b51efdab06187acbb1a5b874db7353393e2e3073d1aa83084d094b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Math50
### Patch Diff Hash-SHA-256:

6026e126a7c1a8b8c1536ceb4f5830908f21dddb3ac3b5f36e9a5300a35ef23f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > 0.5) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Math50
### Patch Diff Hash-SHA-256:

b3163600b2af570e7e46df612e3613970a37faba0f7be96c97f815cee6dd4d73

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Math50
### Patch Diff Hash-SHA-256:

aae48eced4b11116b1185650c85984a063cb11bb3f1b88aff91519be84a29993

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(atol)) < 1.0E-10) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Math50
### Patch Diff Hash-SHA-256:

ee626c78395e603e54f3b1609764bdfce9e665d29b826635294cb5dc1edd3be9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((fx - x))) <= ((DEFAULT_ABSOLUTE_ACCURACY) - (0.5 * (fx - (DEFAULT_ABSOLUTE_ACCURACY))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Math50
### Patch Diff Hash-SHA-256:

60be9c3d7d0df0f3bc91767c7c95df0e017b3dc9db19127cc5f3997e4efb2798

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol >= f0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Math50
### Patch Diff Hash-SHA-256:

35dd14c48ab1f9566ae64b70d4cf1154064592801c94475f5c7cc0d5d2bea9a1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Math50
### Patch Diff Hash-SHA-256:

dfee19fb9486e8353c78d33fd20da1210cf5f6261dfef277739c4b0eacb04de8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol > (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Math50
### Patch Diff Hash-SHA-256:

8ff54084bfa05998b2f2f6f5adabc12f93b13e90e621d10e77764d51f649b429

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isNaN(f0)) || (java.lang.Double.isNaN(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Math50
### Patch Diff Hash-SHA-256:

cd42d341dd3a89d1dad351f632dd7ac4addaa59e64c07a88b59dc765e7c5e8c2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Math50
### Patch Diff Hash-SHA-256:

c8b9b175e9f9f64a7f8989f3629c971be3c87cd9429c6e4db95328158d10452e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Math50
### Patch Diff Hash-SHA-256:

b897c63280ac54fbc750fe5db63c0678b93388c4132c740ebec84034f87753ad

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(DEFAULT_ABSOLUTE_ACCURACY)) < 1.0E-10) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Math50
### Patch Diff Hash-SHA-256:

99b1608cd3668c2b364c45b766b3e144415512ed23449e939f68a0fd61546fa9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 * x0) <= (((DEFAULT_ABSOLUTE_ACCURACY) * 1.0E-4) * (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Math50
### Patch Diff Hash-SHA-256:

d972a0c846f887a58da817461d48fb48916bc1f5adea83d0ace61878ca82a2ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Math50
### Patch Diff Hash-SHA-256:

8963a74a002bc0cee7d41152fe68e0869a37c92e449f2895a53a8767a1496c71

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 > 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Math50
### Patch Diff Hash-SHA-256:

d3db6d67c046bbafbc254e5c5f61b4793f4b8af3f10454f7fdffe9b0ce0f067a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x <= (0.1 * ftol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Math50
### Patch Diff Hash-SHA-256:

74fecc1e3c5e3ba04ac2abe07b190b79d899668382271a8e9afb23ded7d20f21

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < (-1.0E-10)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Math50
### Patch Diff Hash-SHA-256:

0fb34e4eb0f9295f206fd5b22db9c51720e429d1e14a16018bf8ee9b5d5fe690

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 <= 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Math50
### Patch Diff Hash-SHA-256:

3b8858349e61acee774271f1597bb37eec9e4e958c1490d3b48ed7ad929b40ab

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Math50
### Patch Diff Hash-SHA-256:

f9b936b96f6b77b2deb81e5657905fe6e9a1f5d131b6aeaac3fecdb754979826

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 == 0.0) && ((DEFAULT_ABSOLUTE_ACCURACY) == 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Math50
### Patch Diff Hash-SHA-256:

95f8ab4c33e678894d3ea828934244c2100c2a85bdc571c177f97f8accf7917e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > 2) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Math50
### Patch Diff Hash-SHA-256:

697bbbe4ea427f122c0d3ed68005050b3b694b7da7ae1516c83deb114eb2f851

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol > 100) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Math50
### Patch Diff Hash-SHA-256:

3ad7ac98ff28558167d328f3e4a073629025b873956b81a7baeccc5c3dda44ff

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > 1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Math50
### Patch Diff Hash-SHA-256:

a0426ef9a8116c2c1b5a4a1b9b3d166c89df90c5504ff718c4af70e2a3e89a8d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Math50
### Patch Diff Hash-SHA-256:

788afd597456f3ec17d21a46090ec4ff6ad86d3715ca95f5c4b844d57cbb2f2f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol > 0.5) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Math50
### Patch Diff Hash-SHA-256:

f58718d0cb3f26bdae379a4f89c86a06114ee8115b604bd3f15f355f996effcb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 > 3294198.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Math50
### Patch Diff Hash-SHA-256:

576b007c7152eeb89f67ee996e9748bbcf71c97d8fcb24d7abc884e682b2b942

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol <= f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Math50
### Patch Diff Hash-SHA-256:

cbdfd9fb414239742a7381bc3c5013c7b12db309dfb95eda9972a80552fd944f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(atol)) < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Math50
### Patch Diff Hash-SHA-256:

3a3d6380c18ff599789de07890df22a9a31e5c7e0b674b55e967019641e1ae1b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 > x) && (x0 < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Math50
### Patch Diff Hash-SHA-256:

c621e138f8d01b2fe13266c814ee9dfe27c532dc0b8210a2ccae579dd95b9db7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 != x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Math50
### Patch Diff Hash-SHA-256:

49511fe68d46f1b5737c84d028689fdcf8a40efeaf33d1325380e37f7ea44daa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx < (x1 * (fx - x0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Math50
### Patch Diff Hash-SHA-256:

729f3d8b9ccf90e09014ab73e11e882e3a73965486e7a2f79d7e7ea40c30acdb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 <= 2.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Math50
### Patch Diff Hash-SHA-256:

bb5f5abd3e85539bf9ffba1cf59b379845dd6a9f408dcb005f7346fbfa0ce2c1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x1 == 0) || (f1 == 0)) || (ftol == 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Math50
### Patch Diff Hash-SHA-256:

5c995a7a7531f10a4a0cc1c07bc9f6f82e899f55acdaf753ea07dd54c404c4f9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 <= ((x1 * 1.0E-4) * x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Math50
### Patch Diff Hash-SHA-256:

cee5101df9ae4dc809204919aae2fc3c2aa56f9eb24ff2b3e2d92a63f81de294

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > (org.apache.commons.math.util.FastMath.exp((-ftol)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Math50
### Patch Diff Hash-SHA-256:

59d2d27ccaedbb69c8caa14f9ba76dc2fc200e78cb816714b377c888b65e8768

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 == (-1.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Math50
### Patch Diff Hash-SHA-256:

ec624666b6b177f7fa7615a0f380cc777bc38951805349b3be06df2f0f576a00

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < 1.0E-10) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Math50
### Patch Diff Hash-SHA-256:

f41f9a7d2e6a44431d0de8fc82e28aef8dbddd74a270078219a3de5b8502366b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > 0.9999) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Math50
### Patch Diff Hash-SHA-256:

9765adab7e6e33dcea4e3d96349b3c31d11e07a5c806b9241fe1b5aa3613c60d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x1 == 0) || (x0 == 0)) || (fx == 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Math50
### Patch Diff Hash-SHA-256:

4e9ece94a834b1410ca96f7c9a9c56a388c7a1a1cbde46eae5e221fea8ecd6f0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((ftol <= (-1.0)) || (ftol >= 1.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Math50
### Patch Diff Hash-SHA-256:

8d0fd0096fac289cf7e86d3d9f00f0b73023f46c6144abd05e3792193fcfad0a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(rtol)) > 40) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Math50
### Patch Diff Hash-SHA-256:

49e47515b9f363cd110b2772ec9e61bb9bbd0ce2b00074bf27a94d450253649d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx == 0) || (x == 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Math50
### Patch Diff Hash-SHA-256:

db1fdb95104f9712ca081dbfe6217b5585b887a0af6f69af9232a76b90337d89

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(rtol)) <= 2.2204E-16) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Math50
### Patch Diff Hash-SHA-256:

1cc1294b0fa6fb164774d8b6aa965563560a34468f8bb04f323374d0922be669

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(((DEFAULT_ABSOLUTE_ACCURACY) - fx))) <= (1.0E-12 * (org.apache.commons.math.util.FastMath.max(org.apache.commons.math.util.FastMath.abs(fx), org.apache.commons.math.util.FastMath.abs(DEFAULT_ABSOLUTE_ACCURACY))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Math50
### Patch Diff Hash-SHA-256:

c9fdc9d2b1b66cdb8fc36b4835d4fc8ced5ac0532f025b4439b53e99b52ea484

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Math50
### Patch Diff Hash-SHA-256:

c51d5c8643190d636184b5e064f0e684b28026fa2b56d9f99ba39c63cdd76035

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 <= (atol * 0.01)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Math50
### Patch Diff Hash-SHA-256:

d7abe6461b73ec974b5c3317b4a220c5db8c8b424a4992f1401c9f268389c34d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x > x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Math50
### Patch Diff Hash-SHA-256:

cc7bba039709ad6a1a1e42aabbc28f5b764559613cc70a37664935dc153323eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 < 0.0) || (ftol < 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Math50
### Patch Diff Hash-SHA-256:

9665b3618c80ae8a686460cff1935718492435ee19edf6ddbf67b9f11bc3d07d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol >= 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Math50
### Patch Diff Hash-SHA-256:

13690cf94b7ec12a41edf211f62b9fd2d067383c5c8c64207ef8ff879fffafd5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Math50
### Patch Diff Hash-SHA-256:

f07a9c46cc4b06224ab03cb225a56a25747a349a58def504b07c45ac55393d5b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((1 - atol) <= x1) && (x1 < 1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Math50
### Patch Diff Hash-SHA-256:

506f7409d787398c2fcc576b99c66c9474496e11d033b366471ce7acecbff5c1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > (x * 0.01)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Math50
### Patch Diff Hash-SHA-256:

459c64c7f7604c9b8e5c616a264ed51fda9d899dbe4d272bec634d505793204a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 > 0.5) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Math50
### Patch Diff Hash-SHA-256:

4d73b7659bf70f625ca4145e5ad3e9ab416544609c1be5053075ce72f7fe95a8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x1 == 0) && (x <= x1)) && (x1 < 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Math50
### Patch Diff Hash-SHA-256:

1a10d4bc5d11d06f882e5c378682f54e3f0ab156d315c55e2d2fc38e02e34aa2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((rtol < 0) || (rtol > 1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Math50
### Patch Diff Hash-SHA-256:

3d0fbfdf346ed2381976cd0625ffd3a0c9d42406edb9285e1177829e045f7521

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < ((-(DEFAULT_ABSOLUTE_ACCURACY)) * x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Math50
### Patch Diff Hash-SHA-256:

a7757703ee406ac2af357e34ab6658ba3a29ed4734a02c592885991d650d7007

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((fx - x))) <= (1.0E-12 * (org.apache.commons.math.util.FastMath.max(org.apache.commons.math.util.FastMath.abs(x), org.apache.commons.math.util.FastMath.abs(fx))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Math50
### Patch Diff Hash-SHA-256:

09e510da92fc26d59e33cf2171e22b59993ebec3e6b8a91bdf5011a0f5b994e3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) <= fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Math50
### Patch Diff Hash-SHA-256:

68bd2bbd18ebea5bfe4cb6ff4a9f05c3364c11fee84c3e2ba80014fe33f7ae22

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(atol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Math50
### Patch Diff Hash-SHA-256:

acae8de1245083d8a88e84e36d34092fa474ffa9b400de47dc124d17b549c55a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((((java.lang.Double.isNaN(x1)) || (java.lang.Double.isNaN(x))) || (java.lang.Double.isNaN(x0))) || (x1 < 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Math50
### Patch Diff Hash-SHA-256:

848fb58cda9565826fa6fcaa3f5d41c2b979b73dda640be10b6caab22303a906

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(atol)) || (java.lang.Double.isInfinite(x0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Math50
### Patch Diff Hash-SHA-256:

e6a6c471170aa9b46d2a826d37ce1dd1805c3beca488580f7553b221a87d601f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((ftol * x1) > atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Math50
### Patch Diff Hash-SHA-256:

46b5c4b12157fe3a1a55869e2d3facb24051b2c21196b906a3682b4a7d3840df

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < (-20)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Math50
### Patch Diff Hash-SHA-256:

5ca24e505a536c7a4daacb9538ce6b9f4e61c6a84fd4b07d5d05716cc1a3d498

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x / x0) < 0) || ((x0 / x0) < 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Math50
### Patch Diff Hash-SHA-256:

b4c65e14fdc0c39c9e61bb1fd79baf74c3128d043a3dbc5cd424be5aba157849

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < 1.0E-15) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Math50
### Patch Diff Hash-SHA-256:

44ecb3ad3ce9f2a316450d52a74aeaa2abdda07e462066ffb68b55bf37c9ce4b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Math50
### Patch Diff Hash-SHA-256:

1307c6125d4c1f6d933fbd9d846ba6302d45209e61c403a62a6fbdf44c72a38f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((org.apache.commons.math.util.FastMath.abs(f1)) <= 2.2204E-16) && (ftol <= 2.2204E-16)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Math50
### Patch Diff Hash-SHA-256:

9d9aa8e931706848c2832544cf49bd515519bf5bee63e26d47962945df4dc29d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(ftol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Math50
### Patch Diff Hash-SHA-256:

67ac0dc13646a63b0d8c5ec12a901453d186ef030b1c86abfa86c07afcff1ebc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 0.5) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Math50
### Patch Diff Hash-SHA-256:

7191de97ed6f70c982095ef243cc76ddc1d65edd5d0f8bc04bd8848a2ffa022c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((atol * x) < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Math50
### Patch Diff Hash-SHA-256:

beb9b5ce944717888f55410915253988376c773e8bba1db0975ca25448fc92e9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx >= x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Math50
### Patch Diff Hash-SHA-256:

b7f3377c10b3bc3e98df3d4c79f3a5871d910471ee96c610653e556e4e4fde31

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) < fx) || ((DEFAULT_ABSOLUTE_ACCURACY) > x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Math50
### Patch Diff Hash-SHA-256:

9accf489aba1e71a975135c3e6fa9eb978ac7b6873d05a3ad2da9974b49b24e2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(x0)) || (java.lang.Double.isNaN(x0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Math50
### Patch Diff Hash-SHA-256:

7532672d5981fa9999dbfe7c5a099e634b45e62642dbf83091922822bdc21804

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((org.apache.commons.math.util.FastMath.abs(x)) <= 2.2204E-16) && (x <= 2.2204E-16)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Math50
### Patch Diff Hash-SHA-256:

55feb22bd389188c40e6f3a52acb5b4f3b6b73ab003458c94fdecb5305cfbc2a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Math50
### Patch Diff Hash-SHA-256:

900a38c1603c0627d17af8c3c986d2f8ffcdfa119b8b75b9e1b7eb9c88867634

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Math50
### Patch Diff Hash-SHA-256:

da45d608dea0d2237fc99b119f7e091efcf90179ea31d5f671bca542c0390bf4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.log(DEFAULT_ABSOLUTE_ACCURACY)) < ((0.5 * fx) + (x * ((1 - (DEFAULT_ABSOLUTE_ACCURACY)) + (org.apache.commons.math.util.FastMath.log(DEFAULT_ABSOLUTE_ACCURACY)))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Math50
### Patch Diff Hash-SHA-256:

7d6f7865bd681d3b5cec98d6363d1c0bc0ecfe292205fdd5eeec92d5dc7193d2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.util.MathUtils.equals(fx, x0, 1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Math50
### Patch Diff Hash-SHA-256:

ceba4c52d5e56989528f74491bcddeb00532db5d51eeece9cf7fad4e09e8c6b0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((((DEFAULT_ABSOLUTE_ACCURACY) == 0) || (fx == 0)) || ((DEFAULT_ABSOLUTE_ACCURACY) == 0)) || (x == 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Math50
### Patch Diff Hash-SHA-256:

9f22c91823cba4f11837b5043abfd7c2e6c1ababf48701c280c56f2e4b463f37

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Math50
### Patch Diff Hash-SHA-256:

274c89ff558f85cf3b533a5cc23883a10b750688d8c568b668dfbb96bae947c8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Math50
### Patch Diff Hash-SHA-256:

1301f0c245a5205c03566e687daf6e431c6fea3b693ff703689243236b65cac5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((!inverted) && inverted) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Math50
### Patch Diff Hash-SHA-256:

f185b9445b6897e6625b3af827488a852b353efc65e07d41ed8d9ebb10c775b8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((java.lang.Double.isNaN(atol)) || (java.lang.Double.isNaN(DEFAULT_ABSOLUTE_ACCURACY))) || (java.lang.Double.isNaN(ftol))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Math50
### Patch Diff Hash-SHA-256:

480c6579cbecded8fc2fd2e0742dbd5f27912624c8ea2ce9960cfc7f17d70622

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) > 1.0) || ((DEFAULT_ABSOLUTE_ACCURACY) < (-1.0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Math50
### Patch Diff Hash-SHA-256:

2d48c1dfcdad104ed30a5adc8d5b4619ec68e3c6f2f2e1174e4e6316f13c5376

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Math.abs(fx)) > (java.lang.Math.abs(f1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Math50
### Patch Diff Hash-SHA-256:

eb03fb258c5c7b53b836f55a8315619a31e5c7ee91ee5837c7436fe884973cb6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(x1)) <= (0.1 * x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Math50
### Patch Diff Hash-SHA-256:

af48a9cb4cd7e6cff5a54b2af0f1c8afc936fc9e18f05dec78b22782c2bc43ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Math50
### Patch Diff Hash-SHA-256:

8364a03d53497f0ac10f0ea661629586c789347ea4025ac73f61acad8af9dfb5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.max(rtol, f0)) < (getFunctionValueAccuracy())) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Math50
### Patch Diff Hash-SHA-256:

2441c51dc69bde1f24b115084af11116d41ee1931f2270d5908c044f37d100a3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Math50
### Patch Diff Hash-SHA-256:

d9e62d81f32ca6f5ebc9fa68de23fab1aece4e4449787ed8a81685abf1d77f28

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx > fx) && ((fx - fx) > (0.95 * (fx - fx)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Math50
### Patch Diff Hash-SHA-256:

f9643304836eebf91a0f99e98a8b9567f7f0ef12203043d638f3c4e52c80f98b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Math50
### Patch Diff Hash-SHA-256:

edfe6b7ae8b250f5208e3d0a5409c184dcf1e5985fb09eb0ff28459dbef52435

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(x)) || (java.lang.Double.isInfinite(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Math50
### Patch Diff Hash-SHA-256:

fd6ba7875ed29c40842aa04f6cf60ed80f0d715f83219b462ea10ff19fb7d0b0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx * x) > 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Math50
### Patch Diff Hash-SHA-256:

cbd27efcadb12258508d0285280d575e3b398120e15c8f3a76de08b43844fb89

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 <= (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Math50
### Patch Diff Hash-SHA-256:

8db1b1c5fc1b26828ee1132f52c814726b751f439e4c4a9337e4f5049645c78b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < (1 - ((0.0331 * atol) * atol))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Math50
### Patch Diff Hash-SHA-256:

101a63680ab0091f13d8c88c7d0fa8d9ff22f538e4441b7e3eb99091fe18c756

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((atol >= 1) || (atol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Math50
### Patch Diff Hash-SHA-256:

e62b5a3e20cfb6053f760cdb7869b2ee256a3c979e155dd56ad72d1cadfa2c9e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(ftol)) < (org.apache.commons.math.util.FastMath.ulp(1.0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Math50
### Patch Diff Hash-SHA-256:

cc8600892aab1a76345410ffc8f314fdd6497b476160514a0076cff9a234c265

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(rtol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Math50
### Patch Diff Hash-SHA-256:

a895ec7ad94f8a39608e6bfde7087c4c1758f1cc0a70e98b5405d2083badb628

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Math.abs(x)) < 0.25) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Math50
### Patch Diff Hash-SHA-256:

636e709aa81879f4bf499614f5ca5a4e7091b252cf1dd08024b16933da178253

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((rtol * (DEFAULT_ABSOLUTE_ACCURACY)) <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Math50
### Patch Diff Hash-SHA-256:

f3c02cd3ed84a48a11092ebf020d6743b30ef3b261d834ba7c755561f8106e35

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Math50
### Patch Diff Hash-SHA-256:

e4cd2a2f870ff884cdd8639ed4a0a7ba5baca6ee19debe402b4b85654ad606eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((java.lang.Double.isNaN(x1)) && (java.lang.Double.isNaN(x0))) || (org.apache.commons.math.util.MathUtils.equals(x1, x0, 1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Math50
### Patch Diff Hash-SHA-256:

e48d7c28d4ca1a33ffdc7df566c1d39f8052cb5b368637d66527d6dbcec6b8a2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < (-f0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Math50
### Patch Diff Hash-SHA-256:

a3a26a5fd4ee06b3b4a08da3fe376c3f0899f7d952c592a4ff4dd80ddcf87907

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol > 0.0036) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Math50
### Patch Diff Hash-SHA-256:

72d50893289bec814dee8a209c6a394406653db2d95d64183d691cac119f4a6b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((allowed) == null) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Math50
### Patch Diff Hash-SHA-256:

1ddc9df65a1444ef4fbcd2fa9ac9e088cb1ca3b40a6e4c916b7af72bf12a3eaa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Math50
### Patch Diff Hash-SHA-256:

74f8803f7a6a78dd457a52abcab8fd4edb5c075e8cb21ccb8e54e023070516c7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < (-1.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Math50
### Patch Diff Hash-SHA-256:

6a4385cec330e1c3a169db7c0e7ff1d834a9f01ffd1900cd08c58adf2fc7e5f7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(DEFAULT_ABSOLUTE_ACCURACY)) <= (0.1 * ftol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Math50
### Patch Diff Hash-SHA-256:

0c5a6c555627bd8067f9fcd4bedc4994c23052bc46fc1dd97265f5fd4b0ccdeb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 <= (2.2204E-16 * x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Math50
### Patch Diff Hash-SHA-256:

e5ac362edc0b8aa4fe4d8714f48ff3a94a5e7c12aabfd56f58558d473c6fdde0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > f0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Math50
### Patch Diff Hash-SHA-256:

3168bd44a07fee05649cbc9de6b4e92236becc0a256991445a8935fdf9f84fc6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (isBracketing(rtol, rtol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Math50
### Patch Diff Hash-SHA-256:

813f8ced3d26b96299eaa0ee823130fa394a9f33155f4c800e0bc960ae2164bd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx >= 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Math50
### Patch Diff Hash-SHA-256:

43dc912ea1fb37d6872462f0113c47f5666fea13a6a4f533cb7c81816df789e0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 == (DEFAULT_ABSOLUTE_ACCURACY)) || (x0 == fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Math50
### Patch Diff Hash-SHA-256:

0775018a5e1312d7718efbfaa5a9b1743783c43f2e87615b75afea7acac6737c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx == (-1.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Math50
### Patch Diff Hash-SHA-256:

66482a29960123c4937d994b3acfb5846a533dd692653f321ce397319ae10c9c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Math50
### Patch Diff Hash-SHA-256:

15a12db9569c5daa36ae1ab8e56ed0368c5c8be05365f7e8e588c988c3fc5550

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Math50
### Patch Diff Hash-SHA-256:

a871c058ec29fce33b48cd4588c17b0332fc09a126437028aa36cf8b843ddcf5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Math50
### Patch Diff Hash-SHA-256:

9c43e1009ab173f6b45a770c69b7cb5bf93fa14dcecce2401595bff742127900

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < ((2.0E-15 - 1.0) * ftol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Math50
### Patch Diff Hash-SHA-256:

3ffd8788b33372eefef746b12120305ea943831b4dcee4b91dfbf36efc50264d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(ftol)) > ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Math50
### Patch Diff Hash-SHA-256:

9a8f3e84d81d82326e78d817fb46a1e47f637c3083e4104367bf1621fecd8900

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx * fx) > 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Math50
### Patch Diff Hash-SHA-256:

75c66dc4c8465499a6c50e4f183f0f160dd4eb79876d36913a2b269fd78dbf6a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.max(x, f0)) < (getFunctionValueAccuracy())) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Math50
### Patch Diff Hash-SHA-256:

a73c0bd4ef896779759a457cef8066d557f957f4a2049f8dca944f55dbc4811a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Math50
### Patch Diff Hash-SHA-256:

9eb4c601397d91f5d544d13bfd8415001f1dc7806b66e8fb31ea37279630b881

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 > 100) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Math50
### Patch Diff Hash-SHA-256:

5c45c12bdb8f83d846024dae5155ea0784f2d4cfcc4a0fd2baf6abae512cf364

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Math50
### Patch Diff Hash-SHA-256:

6ffec4d3e5185040feadb8aad95b2093050e74fa1de3dac8814e94282cbf97cf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Math50
### Patch Diff Hash-SHA-256:

4e515cc8dc765027c06aa81d9cf78c4408c00e1fb24a2958c582328f81a77d17

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < ((2.0E-15 - 1.0) * f0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Math50
### Patch Diff Hash-SHA-256:

6f24db3a9421a36ac22b92e8969df0db978440d214886db0652726a68a4a224b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(atol)) < (org.apache.commons.math.util.FastMath.abs(((0.5 * atol) * ftol)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Math50
### Patch Diff Hash-SHA-256:

bdaf15e5f5b08b01a7fd950ce24a828d4a178dbf763398587ed0b5a0ae7b423c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol < (-1.0E-10)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Math50
### Patch Diff Hash-SHA-256:

5dea2c75dc62de6211f9f7fc0f2a6f8775a9a2205ee0842afaf1118c02f449f3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < 1.0E-10) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Math50
### Patch Diff Hash-SHA-256:

982b00bbe84f21fed7a125a026eee0e515a4f961b7a6f329a37140b6c2e2b9b0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < 0.1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Math50
### Patch Diff Hash-SHA-256:

b090365d087c29bee5254714dda6ba1bec86b4166d209c96fcccf2073b9adfa7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Math50
### Patch Diff Hash-SHA-256:

75118dc652d8c0e009cbce6a41a949cc66d4ca4187c5a7a5f79671badf4b94b6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > 0.0036) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Math50
### Patch Diff Hash-SHA-256:

d91ee6ac09473ee7eeb11decd328091c50279f3ccf774d96ce6626765601ab03

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.log(fx)) < ((0.5 * fx) + (x * ((1 - (DEFAULT_ABSOLUTE_ACCURACY)) + (org.apache.commons.math.util.FastMath.log(DEFAULT_ABSOLUTE_ACCURACY)))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Math50
### Patch Diff Hash-SHA-256:

c66ab1cd4d7f14d176c486962ea906f3aa3b1f047e7cb94afadfb82278735c34

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol <= (2.2204E-16 * f0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Math50
### Patch Diff Hash-SHA-256:

bbeffc9ade41d24ceb52e3b19e570ce97362b00f6ae5f76274d058da4f6768f3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (super.equals(allowed)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Math50
### Patch Diff Hash-SHA-256:

e9dd7eca279b33722274a2a74f84b5a70290adea2e1376c3b8af48cd60cb4457

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Math50
### Patch Diff Hash-SHA-256:

9ea42fe58e5b697addcd474e7cb4f6a61282b341b07dce201d8573ca68ffcc60

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(rtol)) && (rtol > 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Math50
### Patch Diff Hash-SHA-256:

cd809c30493166993b8b1866675ed14ed00db4121bc8554c40e04f3e248cab51

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((java.lang.Math.max(x1, DEFAULT_ABSOLUTE_ACCURACY)) - (java.lang.Math.min(fx, DEFAULT_ABSOLUTE_ACCURACY))) == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Math50
### Patch Diff Hash-SHA-256:

08613edc546c10837bd9894c94473e0460074400e36f802764e042b0476fdcc3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f0 != 0.0) && (f0 > x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Math50
### Patch Diff Hash-SHA-256:

9f4c82cd6c98de983b10cddebebf596fc7e794017faa26a5ceed202a24aac98c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Math50
### Patch Diff Hash-SHA-256:

8b04cf9e5bf541f6a623747c2afe1c7cdb36fd8a16a2ad931c55a7e4ca36f7b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.util.MathUtils.equals(f0, 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Math50
### Patch Diff Hash-SHA-256:

a9da78290c2dc412e09c511a0a2dd5ddca2af8148e19144bba90a4be5825c306

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 > x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Math50
### Patch Diff Hash-SHA-256:

301c783934e718ea5c4636d620ac06d591b7b208abecbb4c51bbe9f63ddcb02d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((org.apache.commons.math.util.MathUtils.sign(x)) + (org.apache.commons.math.util.MathUtils.sign(rtol))) == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Math50
### Patch Diff Hash-SHA-256:

99b9bee0e5e6f4dacdd7f7d44c482b8c241cc700910158a288d9f7bde0e702eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 > (org.apache.commons.math.util.FastMath.exp((-f0)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Math50
### Patch Diff Hash-SHA-256:

442f679a9969da616db722c041fdedf7fa55bb85a22116f75909a7aea72e3a2e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((((java.lang.Double.isNaN(DEFAULT_ABSOLUTE_ACCURACY)) || (java.lang.Double.isNaN(x1))) || (java.lang.Double.isNaN(x))) || ((DEFAULT_ABSOLUTE_ACCURACY) < 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Math50
### Patch Diff Hash-SHA-256:

1a06feaa74c04f75cbd15bb59dc943506dd3961ffe7381abe36b1f13608bf07b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > 3294198.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Math50
### Patch Diff Hash-SHA-256:

27e7330113b947eb908fffbeaa29d894e3a5728cccf0edf7e78fd82055b06f55

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 <= rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Math50
### Patch Diff Hash-SHA-256:

46da84d74ba9bd0b73a56778ef62c63d8c7b2ef1bf75bc44c9789637adc98e5e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(rtol)) < rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Math50
### Patch Diff Hash-SHA-256:

b7151b1053c3b162365cb3daf39513c57b7bf55ff2c2aca1696940c19d2bd027

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x != x) || (x == 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Math50
### Patch Diff Hash-SHA-256:

4e2b7935128c8cd9c1c7ebd2ee10758ec8a20923fb53465127701ad7ef1db668

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > 0.003) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Math50
### Patch Diff Hash-SHA-256:

e067d36af19b7ff19e2f963f2179f1212b57eb0572147e13b146c37a466b8e7a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(ftol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Math50
### Patch Diff Hash-SHA-256:

719ffc40739e2d02b5b5b62464c1d18b75e70494722bbd98e65d71e0c5443056

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(atol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Math50
### Patch Diff Hash-SHA-256:

903e0f0df195a79b037d3e817a185dd7099e2844c2a372344919adf2592b22e4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f0 <= 0) || (f0 > 0.5)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Math50
### Patch Diff Hash-SHA-256:

7274596f456d2d60f28fdc6cb8ebcb702b40ce8c78f2912fef11a9d301f762fd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((((java.lang.Double.isNaN(DEFAULT_ABSOLUTE_ACCURACY)) || (java.lang.Double.isNaN(x))) || (java.lang.Double.isNaN(DEFAULT_ABSOLUTE_ACCURACY))) || ((DEFAULT_ABSOLUTE_ACCURACY) < 0)) || ((DEFAULT_ABSOLUTE_ACCURACY) > 1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Math50
### Patch Diff Hash-SHA-256:

6c4b5a1541a61e414e8f5b5ae2cac5d14b520f8c8b37086cf7cf0f7893d884ce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 > x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Math50
### Patch Diff Hash-SHA-256:

f95c8254f0205832b8e2df15d41cb213384ec08b134df0f8aa041750b4f60766

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx > (4 * (org.apache.commons.math.util.FastMath.max(1.0E-15, f1)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Math50
### Patch Diff Hash-SHA-256:

7ed3493f07d189822333f17960debfce4b7c04c5a5d6e2733a72985df95c3bab

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > 1.0E-10) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Math50
### Patch Diff Hash-SHA-256:

3c4952080531791bf00e35e81575851344860b50914d2a07ecef0abb09e0a38c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) > (DEFAULT_ABSOLUTE_ACCURACY)) && (((DEFAULT_ABSOLUTE_ACCURACY) - (DEFAULT_ABSOLUTE_ACCURACY)) > (0.95 * ((DEFAULT_ABSOLUTE_ACCURACY) - x)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Math50
### Patch Diff Hash-SHA-256:

9bb48e494f2240481731f4d8ebc83048f1da37f5cdb58dd315082a6ec64ae28e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol <= 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Math50
### Patch Diff Hash-SHA-256:

219696e94e38fdc376bad4d94acb848b756e9e46123e0b1c7bc8fe92fde99745

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol > 1.5) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Math50
### Patch Diff Hash-SHA-256:

f1c8d3b1830ef18bd4a2a4d64d1f7a71894b04644410bf8c0d08e2f9594af70d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol < 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Math50
### Patch Diff Hash-SHA-256:

0f883346d42e11a5ddd68e642464f890acd4e480529d4115ecfec2a19ab35c55

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 >= 0.75) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Math50
### Patch Diff Hash-SHA-256:

6f7c5b1850ef10d6f937197aaa056f07cfe7e1850eb158d41b33da1b462a7ba8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 * f1) == 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Math50
### Patch Diff Hash-SHA-256:

4a0d8ddc4b8514b67ba54148b3878bcafa59cf062248cb736b829493a22ae5a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > 20.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Math50
### Patch Diff Hash-SHA-256:

a60ba63443cfb28523605e192b8d14ba28174c0cdc93c2118f8978a65ecc4880

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Math50
### Patch Diff Hash-SHA-256:

96e4841b0372bcaf709990bfb550158c8a75336e8408119dae05cc166208da9e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol == 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Math50
### Patch Diff Hash-SHA-256:

4509e87ce3c8f33013fbfea00cfd547bcef94c16802f6db55ae85818a764df3e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((x - f0))) > x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Math50
### Patch Diff Hash-SHA-256:

99856c12e767522994c396600d520a4afee41432b36e68b52b4832119646cabd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) < fx) && (fx <= x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Math50
### Patch Diff Hash-SHA-256:

fa03b087b66182e8f263a03507a58b5eeddb80dcb589acf603b41d5c92a064fa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < x0) && (x0 < fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Math50
### Patch Diff Hash-SHA-256:

2ffad78feb6a5ec0d47ee594b438ea5cb251952cebd87dd825aa753b29801fea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Math50
### Patch Diff Hash-SHA-256:

c1345183cb5a79941923ecb83776fc1ba4e3ca5d0d5a497dc1ce29b3feda236a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f0 != f0) || (f0 == 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Math50
### Patch Diff Hash-SHA-256:

db3af5bc9cf6fb0958ba503a2a1e20d869246607815cb85eaca112915eb238cb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((atol - ftol))) <= ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Math50
### Patch Diff Hash-SHA-256:

61392b1a215c9119b4ff0e1deb8d31b13f93d9a74b60ed664235e2d9a38ca0bd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(DEFAULT_ABSOLUTE_ACCURACY)) && ((DEFAULT_ABSOLUTE_ACCURACY) > 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Math50
### Patch Diff Hash-SHA-256:

75a69f98cb0b66183951bf7bcea5fab36b607f6916b3204b432f1671e40270ce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x <= ((atol * 1.0E-4) * atol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Math50
### Patch Diff Hash-SHA-256:

3c3e910a82d3edfbbc2f905f5514f7696a7c5559d087fdd92c2904d2aa137cc5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol > 0.003) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Math50
### Patch Diff Hash-SHA-256:

f12988d32266fa125150027989b0a75638f3cb4a4127dd797df22594d4c5f6c2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(fx)) || (fx == 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Math50
### Patch Diff Hash-SHA-256:

ab3dc8f00ef2f3674d34f47b1252daf0b7417f73bca4475a3f1fe0beb961abcc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 > x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Math50
### Patch Diff Hash-SHA-256:

61121fc60045433f2d25d10b44f7ffd9b7325e69d43636c27728f68d518dd617

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((x1 - ftol))) < 1.0E-6) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Math50
### Patch Diff Hash-SHA-256:

6ebfee51edae89695cb2734ad6792e76654df2c33a01e325a2e7976331912f88

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((fx - (DEFAULT_ABSOLUTE_ACCURACY)))) < (0.1 * (fx + (DEFAULT_ABSOLUTE_ACCURACY)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Math50
### Patch Diff Hash-SHA-256:

47afa0179f46023221919cac5fe32329bb26d6a1b3ceccc5d09d63d30534fce2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.floor(atol)) == atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Math50
### Patch Diff Hash-SHA-256:

473926de4745496659aadba4f26b9f773d6364cd3c228cd51584a64c13913ebd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol <= f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Math50
### Patch Diff Hash-SHA-256:

882bf6400273ee3c926b7aebacc1ad23fa3261767bd296012de426a5ec02663d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.isSequence(fx, f1, ftol)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Math50
### Patch Diff Hash-SHA-256:

3bc809f8c3ff10db651746417a37a536fa7d3c9bf7e947755b915cda90af3f84

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 == 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Math50
### Patch Diff Hash-SHA-256:

01e0daaa1ad0f58e4ce19b6e4613e10801360455c54484529a6cd2e0da05f265

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 >= 1.0E-4) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Math50
### Patch Diff Hash-SHA-256:

7e42adbeee476d89e61ce5771a5794fce0b398730a19ea1b0b509d02a10c393d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.util.MathUtils.equals(fx, x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Math50
### Patch Diff Hash-SHA-256:

3bff1ad5dff7eb775ea619a5b718cf703d339b0d31f4ca56838d56dbf8700eaa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((((DEFAULT_ABSOLUTE_ACCURACY) == 0) && (fx <= x0)) && (x0 < 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Math50
### Patch Diff Hash-SHA-256:

0c107c8d54570a92313a17c4ace825b8dc0c40d831e285c5f2549375650086d5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.util.MathUtils.equals(x1, DEFAULT_ABSOLUTE_ACCURACY, 1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Math50
### Patch Diff Hash-SHA-256:

48cd31d39cb2406bcac94bbb505f8f7c94e15be36628062ec69573416b682b75

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx < fx) || (fx > fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Math50
### Patch Diff Hash-SHA-256:

fad2686a030bf01dd43c2b94f83cab39ad2234a79ba8b6e7f173c3f3f9ab2b23

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 > 0.99) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Math50
### Patch Diff Hash-SHA-256:

4aa8b1c81eae98e91b825c998430760b7b5b7283de96b008c211824a92055f15

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Math50
### Patch Diff Hash-SHA-256:

a7add305d5be0737490b234a83859938900fad9eeccb96df1f04906bcd12af46

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol < f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Math50
### Patch Diff Hash-SHA-256:

e1df824dce8179df21f99d7479a5a5de765cff0a791d0fc1976f0f3913481fbe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 * f1) > 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Math50
### Patch Diff Hash-SHA-256:

e0e7ebebe24b96815f5cdd7d664c004431b54d8e824a0fbe25a4896c60962736

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Math.abs(ftol)) > (java.lang.Math.abs(f1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Math50
### Patch Diff Hash-SHA-256:

c6321f527c706d632c068d70a4f3bbd2c7422cc7b42e0b70b73149f36dbc98ca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x < fx) && (fx < fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Math50
### Patch Diff Hash-SHA-256:

15d30e5cdf8c1096eb6b9df8263af51ddfe858c44e86aabf4b781afe567d21ed

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx < (DEFAULT_ABSOLUTE_ACCURACY)) && ((DEFAULT_ABSOLUTE_ACCURACY) < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Math50
### Patch Diff Hash-SHA-256:

10deb11520cfb2f571d63b56f2eb22807fb03a4133ab98afe86aa84ba1c93e99

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f0 >= 0) && (x1 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Math50
### Patch Diff Hash-SHA-256:

94ddc65cceea8a68fbcede4d9488a01fbac6232113dd3f59934da3a365b5dd84

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol > x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Math50
### Patch Diff Hash-SHA-256:

c45e0402b8c5e37ca9c81b825e2b31dd81e2e5b3c5ae16b6b6dc33e8863200de

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx > fx) || (x0 < x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Math50
### Patch Diff Hash-SHA-256:

447e892aaea81a1e937f9bccfe0945109e34f45e26afd5c61fcbbbb7771d284a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 >= 0) && (x0 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Math50
### Patch Diff Hash-SHA-256:

298f8263515559f33d887acb025d032ecd93359de85e49bec1c2c28dba78eb40

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx >= (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Math50
### Patch Diff Hash-SHA-256:

2b5385708d3ef864cbb62748d02867c8c58ed14e1847247260dadd24ee949e6c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Math50
### Patch Diff Hash-SHA-256:

6b300b2e09bcba6907c0b04777751e2aba78781ceeb3b7f2831676d95fbcce71

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) >= 0) && ((DEFAULT_ABSOLUTE_ACCURACY) <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Math50
### Patch Diff Hash-SHA-256:

640f8f59c7ec64d74886f57fb13bb012805e35f5af0c1c441be9df4dc295afd8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < f0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Math50
### Patch Diff Hash-SHA-256:

bf1238674f1e73223128f1b5fa59b92c0d290720120d5007209cd6fd425d51c4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 < x1) && (x1 < x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Math50
### Patch Diff Hash-SHA-256:

673f5c721ec811c42af262eea8a5517669e2a5073cb67c2ef365e1a0c1366d36

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx >= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Math50
### Patch Diff Hash-SHA-256:

287de8fbebf93cf5a0f9ab9a3647ab94523613148177547a10aed26bb3673acd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol < f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Math50
### Patch Diff Hash-SHA-256:

54feb68a5152f4f749b4e6ab4e8964aab290b09a173c17f60a1ca1339d08f4e3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Math50
### Patch Diff Hash-SHA-256:

f8434ed9d29b2dc0dbfd5f2c325bf4b8929552856062050fe58782da05cf2eea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Math50
### Patch Diff Hash-SHA-256:

315fc745db977c1b28bc3fd5545c165be261c2e4f4e83e18582a6f135f852b85

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Math50
### Patch Diff Hash-SHA-256:

34a19947aa599e1ef3962c8986c8e94902bad33a2533d4881d236c1ab3d5bb57

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx > fx) || (x < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Math50
### Patch Diff Hash-SHA-256:

1e0fa5b894b789a3dc0094f5ebc5229ebef4b775ac7eb6971c7f33a8f0c4269e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 >= 0) && (ftol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Math50
### Patch Diff Hash-SHA-256:

b571594b5049142f806435e0b00bbd067303cfcf186fdd2619752762215b0ce2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) >= 0) && (ftol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Math50
### Patch Diff Hash-SHA-256:

e2670591af47d199cfa9b53096d01f990a8b46b7d579e169f4b0a5f962cace54

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x0 >= 0) && (x0 <= 0)) || ((x0 <= 0) && (x0 >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Math50
### Patch Diff Hash-SHA-256:

c1883e76c8ba34b3449a0a255c7598c50cf077118b818a4fd857d57f791ceee1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol > ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Math50
### Patch Diff Hash-SHA-256:

8167a3c42d6e5b7469c5bf3fef880e61ead692356c203e437f83557d03e87ba7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx < x1) && (x1 < fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Math50
### Patch Diff Hash-SHA-256:

b4cfac4f85affab54972da0a1ff2ba35f5f377fdd242b4b163083994e0cbd093

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Math50
### Patch Diff Hash-SHA-256:

8d3974d82d2c6e5a8e8e599adca1bac4a0e689c58556cadc270693c51d033a27

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 <= 0) && (ftol >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Math50
### Patch Diff Hash-SHA-256:

ff88ef0263d642df87f23752a8295d978001171c3a7f3fce8e2e6fc9e3f8ed54

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) < x) && (x < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Math50
### Patch Diff Hash-SHA-256:

c192fbe6767a79879824cee43a67b6007fbc2d11272bd12d0528caf747a03a27

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 * ftol) > 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Math50
### Patch Diff Hash-SHA-256:

0250a8ea2b4f339862d9461a5de79d20b3144beeac8adb54c5008e313971ab2e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 > x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Math50
### Patch Diff Hash-SHA-256:

f4af862fbe94cae4f0c5a8cc9000baef8759dca0d1b5c28659d6d74adc3f618b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) < fx) && (fx < fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Math50
### Patch Diff Hash-SHA-256:

287f5634cf2b19c0a9a89c59646525264c602dddc107dd1bdf3fcc8e155117f7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 < atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Math50
### Patch Diff Hash-SHA-256:

af55fffd6ea5b0dc67927befba565e0352bf1bb42ddea229bd19940c8599e3ee

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 * atol) > 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Math50
### Patch Diff Hash-SHA-256:

a78f5c3d94ad1cd9f129fac2870f8abc943d72c306262dc78d3fd71a371aebfd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 >= (((1.5 * x1) * x1) - (org.apache.commons.math.util.FastMath.abs((x1 * x1))))) || (x1 >= (org.apache.commons.math.util.FastMath.abs(((0.5 * x1) * x1))))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Math50
### Patch Diff Hash-SHA-256:

38e4477ef9e673ed128a8df3615e4a9c06dcd84921482239850d832380545cd7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 > (4 * (org.apache.commons.math.util.FastMath.max(1.0E-15, x1)))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Math50
### Patch Diff Hash-SHA-256:

7e669894d6172ab7410d8fdfbd995f8cc9d8231937d7f68e4928d24c8711ca4e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((((java.lang.Double.isNaN(x1)) || (java.lang.Double.isNaN(x))) || (x1 <= 0.0)) || (x < 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Math50
### Patch Diff Hash-SHA-256:

c40ef4b950f48cdbf11f6c8628758ab79825b6b58b1d8d26e3b123fb88315593

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(x1)) < x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Math50
### Patch Diff Hash-SHA-256:

793d4241216328f896c1b046332e89c08a7d389d1b185f219ce281481efd6bdf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Math50
### Patch Diff Hash-SHA-256:

d0416413faf05ba1f970f61452b8357a9785e15ce2629bde659332435292ce90

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 == 0.0) && (x1 == 0.0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Math50
### Patch Diff Hash-SHA-256:

7f0d892692e08c2e70e6e40166d3d74b2f7b5a357ffe6041e247a2d06b62ba2a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x > x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Math50
### Patch Diff Hash-SHA-256:

9eb855d34eb1aee762a990f7a689950da77ffd330a0a34ce750a2cbb2ca39247

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 1.0001) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Math50
### Patch Diff Hash-SHA-256:

9f38d8afd8946ff4cc75b714123d16f3f0a2791c617b1d81f5a98ed0e106b6c3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x1 == 0) || (x1 == 0)) || (x1 == 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Math50
### Patch Diff Hash-SHA-256:

f426ea4dc23094d17a3b9d387b0362193fb4d7deb77adc81ec3e259ff0fdd960

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(x1)) > x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Math50
### Patch Diff Hash-SHA-256:

5d82426d98a3959604c355ea93faa25fadbe7848d1e9b2fb2ee85cc7126903bf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Math50
### Patch Diff Hash-SHA-256:

0c1d707794195fff08afbf3107e65ce843fb76eec462beb6bdfd91c1e40be7af

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < (-1.0E-10)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Math50
### Patch Diff Hash-SHA-256:

4f8a218a2d3aadbdfc60f796b71d7723c209f92c07670e2a81c34dd8341df0b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Math50
### Patch Diff Hash-SHA-256:

de41a79a5e7bee58c053389b6fdf9190946ed85b1e29701aed783229e2e80e62

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x == (java.lang.Double.NEGATIVE_INFINITY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Math50
### Patch Diff Hash-SHA-256:

a2acf5c5bfba8355b061d576527be41c0493b5467419436c451d2c11f50f328a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x0 == 0) || (x0 == 0)) || (x0 == 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Math50
### Patch Diff Hash-SHA-256:

d57182eb22e6e1c81e27baccda4c5fa9f5b2c947f647772c515bae61ff176a5d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x <= 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Math50
### Patch Diff Hash-SHA-256:

ea2db40b98414b195e2c9dbae7ae95fc3f5445f1bfd78a181a8a27593f3ae7ed

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (super.equals(method)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Math50
### Patch Diff Hash-SHA-256:

726e65be230c4576c51a709728c67836caad3371f19df888a4c30e866211c42a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 != x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Math50
### Patch Diff Hash-SHA-256:

9060dc1cefbef0644f091cc96aba572725eb412636e4093c758f7b71fa02f92a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((java.lang.Double.isInfinite(x1)) || (java.lang.Double.isInfinite(x1))) || (java.lang.Double.isInfinite(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Math50
### Patch Diff Hash-SHA-256:

ab22f0d2e8a4edabd9a1908b9303b220daf33078b85d03a2ee8158484540f58b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 1.0E-4) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Math50
### Patch Diff Hash-SHA-256:

396122278ac2327abf6821db170dd5ba573018ef21bcb117bd46f58021c921f5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(x0)) < x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Math50
### Patch Diff Hash-SHA-256:

0a589ce47e03b95753a6ed0bbea5d385a82ed51705d4475fec345f01d3c1c8d2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 > 999.9) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Math50
### Patch Diff Hash-SHA-256:

aaa1e0f4446baf778aca1afa1a0695e9382a7f4f38638a79e7bd6e2540daffec

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((org.apache.commons.math.util.MathUtils.sign(x1)) + (org.apache.commons.math.util.MathUtils.sign(x1))) == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Math50
### Patch Diff Hash-SHA-256:

da00fad1f270d182c91d1822ad86abf468051eb7b4f43cd829e68d96342f47f7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(x1))) || (java.lang.Double.isNaN(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Math50
### Patch Diff Hash-SHA-256:

ee4533dd8d6b6cb5816d9b4556b6835a437f052e864a7fa6cad1656a62684e11

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 > 1.633123935319537E16) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Math50
### Patch Diff Hash-SHA-256:

9695e8ab6b7b0c0c76632ac13729947da27f84aad5ea7711b696665135f68202

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 * x1) <= 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Math50
### Patch Diff Hash-SHA-256:

4b71cfa6174802b1762d602dc80174a68a8f5383df52cad877f5b7fedfb48916

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isNaN(x1)) || (java.lang.Double.isInfinite(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Math50
### Patch Diff Hash-SHA-256:

1074833fa07f99c6e5614a9d3f870ad45950b14f7b966510d7ac7b59440bf23f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < (java.lang.Double.MIN_VALUE)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Math50
### Patch Diff Hash-SHA-256:

e1fa7cc8973c7233ba48ca509b886933c804eadabf3e1b1f61aa6adc09a9a19e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Math50
### Patch Diff Hash-SHA-256:

8d9d32325dedb03e4c4e1cca840320b079d0d3d4fe8c895aab50a489b4e560b5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 > 1.633123935319537E16) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Math50
### Patch Diff Hash-SHA-256:

fb543658e1596c84ed5cefc8e0cb7191cf32a36ca32d9dbfa0a2ebdac6b3860f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 <= 0.25) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Math50
### Patch Diff Hash-SHA-256:

615e87dede3a7d38585e38cc630cbe9f627746207f9520ded22695fdfcb0ac84

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 == (java.lang.Double.MIN_VALUE)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Math50
### Patch Diff Hash-SHA-256:

c8d18d8f61fbf1c92dc31098b7b0d1ce267e772dbca4f3276caaaa9c9ec45b7c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.util.MathUtils.equals(x1, 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Math50
### Patch Diff Hash-SHA-256:

4a01167f98a5a5a5c4712e098db6af1d6d7b2af2776e69ff4711fdbc6cb30e2b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x > 20.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Math50
### Patch Diff Hash-SHA-256:

be1e182c42c874e8fa96b7b20ad20edcfdb625f339b92be0dd7e1d82af6c1d6d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(x1)) < (org.apache.commons.math.util.FastMath.abs(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Math50
### Patch Diff Hash-SHA-256:

6cf6b4398fb612221ad34a0108a64d51ec67a156aebe6b3f1a681abe3896cacc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(x1)) > (40 * x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Math50
### Patch Diff Hash-SHA-256:

57a8da0cc63f8d40f65c50198113c3fb521dade3b4ae4f5cd312d67ae43ee157

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(x1)) > (org.apache.commons.math.util.FastMath.abs(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Math50
### Patch Diff Hash-SHA-256:

be44c8249497f80bf57ef414e1effb084005d40190efbee4036dc8ef49ad5728

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (isBracketing(x1, x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Math50
### Patch Diff Hash-SHA-256:

9151efbb81b5a113f8d3cd7a0e8ab3d5ad7098075fc0db5603121d5773450498

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 > (x1 * x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Math50
### Patch Diff Hash-SHA-256:

0d6fc022e93f2ff6342d1a4f1dc82208695aea99e4635b0d5cf4f5a3993b335b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 == 1.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Math50
### Patch Diff Hash-SHA-256:

9d6077cb3ea095e7bb634cf7cbf628ec1364ce756ee5bc55ef098308d321aa40

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Double.isInfinite(x1)) || (java.lang.Double.isInfinite(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Math50
### Patch Diff Hash-SHA-256:

7ed61e7e810a61e19c3b1590c456870e22552609574ccd6edcd1b51ce33dd421

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs((x1 - x1))) > x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Math50
### Patch Diff Hash-SHA-256:

8f9e5c737346d9ce29e103b3d13daf9b7d7520a2e6662a83ad941cd8efb81545

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 + x1) < x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Math50
### Patch Diff Hash-SHA-256:

63905cae5c48d161ed55f266c9a41eef12c4498c6e01856dd99903caa6757b27

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x == 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Math50
### Patch Diff Hash-SHA-256:

89cb0e6a82cfaa7b55f194a2c34a7f34398a5066688b55c37e71ca57df5873fd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 <= 0) && (x1 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Math50
### Patch Diff Hash-SHA-256:

7cbdb41f4d9c232ce6d92b6c4338303e5ba046667ef79cde45bda3e98bc5dde0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 > (x0 * x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Math50
### Patch Diff Hash-SHA-256:

b3fcc435b9bd7ffb6c77628d58aa0f1952773b00603399bfad8d88097cef302d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isNaN(f0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Math50
### Patch Diff Hash-SHA-256:

f0322bae21e3b1cfce34f5b735f4a2a30d805cb96f833fea47f65f3ac2333aa2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (java.lang.Double.isInfinite(x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Math50
### Patch Diff Hash-SHA-256:

61bd325d2dda87a8bacaa8c4fc8da1ef014177800a59cf8e86564dc3ceaca86c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.max(x1, x1)) < (getFunctionValueAccuracy())) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Math50
### Patch Diff Hash-SHA-256:

3cb8c1f4a463d2acb54bc06ad8b4ac3d1b9272146e302fdc9ffe85623dd1a1a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((java.lang.Math.abs(x1)) > x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Math50
### Patch Diff Hash-SHA-256:

379d99f4f195615b3df564f3575ea1fd73c5e9d5487fe159b59a6f44b0a1b302

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 > 1.0E15) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Math50
### Patch Diff Hash-SHA-256:

7ab9e9e8da40a7646e1f0892cfaae2f40e83c9718f9c52eca6abe03f2f00abe2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 * x1) < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Math50
### Patch Diff Hash-SHA-256:

8a70de27a5895f00898bb5e3ecd86443c17f9dcbaa8f202a4801d5e4451da3d8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 == 0) && (x1 <= x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Math50
### Patch Diff Hash-SHA-256:

8457157309c87db3ad994dd665478f07c16b0d466d311a7e0c4295e07b9a642e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 <= 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Math50
### Patch Diff Hash-SHA-256:

719213b40d506b31942f61f563fbbc646ce0765249f17e75d4aba8e3145a080e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < x1) || (java.lang.Double.isNaN(x1))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Math50
### Patch Diff Hash-SHA-256:

4de55f3904096f5747502f564ded317d308a855aa235bc354784934c33b00849

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < 1.0E-19) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Math50
### Patch Diff Hash-SHA-256:

aa2324979140f77aa4bbae0000974b98fb662aaf7c5f4e0238a9c29693e546c4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < 1.0E-19) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Math50
### Patch Diff Hash-SHA-256:

3e5e5c46466c7d695339929d33189c06861e7da12c62b200d5922786bcd32339

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((((java.lang.Double.isNaN(x)) || (java.lang.Double.isNaN(x1))) || (java.lang.Double.isNaN(x1))) || (x < 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Math50
### Patch Diff Hash-SHA-256:

0972446b3cfcf006f72f20fd14a95d121140c4e550fd6dad42e3bf60850d2958

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol > atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Math50
### Patch Diff Hash-SHA-256:

c0a96dcdbbf54039dc0e2617c23f11abce764c348085abe820177982e58cb723

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 >= 0) && (rtol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Math50
### Patch Diff Hash-SHA-256:

9df5a7d583a6ec9f76ffc142b7a398386fc7886116d50e2de984b514febaad36

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f0 <= 0) && (fx >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Math50
### Patch Diff Hash-SHA-256:

7c94c2c6df6685af268c39356e08745acab5633f987124403332ddb288868396

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((atol <= 0) && (rtol >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Math50
### Patch Diff Hash-SHA-256:

4bb74feecf49cabffed0d81df151bd07c9cf60501d33caaec5b05e01c2e0fe01

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 <= 0) && (fx >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Math50
### Patch Diff Hash-SHA-256:

a7acfe0468c23de46adcf3435f774178a1bd71f78f64da85be9e02815889358b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx >= 0) && (x <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Math50
### Patch Diff Hash-SHA-256:

f869d191da425993faf97bb61f3e5fadde69f907218e92cfbbf6d186ac095044

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((ftol <= 0) && (f0 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Math50
### Patch Diff Hash-SHA-256:

63c186f91f3d221e44e449696d6ccd3d89aca29d277a4e652dcf747cc4d5ff83

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Math50
### Patch Diff Hash-SHA-256:

837f464c8e99780e7cfb25bc97ec18f2c3d61a50695e9449b379614d06d9f332

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x < fx) && (fx < x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Math50
### Patch Diff Hash-SHA-256:

e657dd65a0a9b667f7ddd8a298596d978ee833045898801acf9854271cfc83dd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Math50
### Patch Diff Hash-SHA-256:

72baf0604305cc07ba01f8ab2111748e2eb0d1b0579b995d395ebbfcbf7b6f5a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((((DEFAULT_ABSOLUTE_ACCURACY) >= 0) && (x0 <= 0)) || (((DEFAULT_ABSOLUTE_ACCURACY) <= 0) && (x0 >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Math50
### Patch Diff Hash-SHA-256:

cb8728a178e7defdcc11e0d37fb005aaeb14cf73bd6e35bc3ec2a551ce326c17

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 <= 0) && (f0 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Math50
### Patch Diff Hash-SHA-256:

92b29c67190caed869687206cb3f124c3fca5b6beea49af17a2a39fcf9bab882

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol >= x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Math50
### Patch Diff Hash-SHA-256:

d7de717a036e0b9237fbd514f1d7b87ab85b6e3270b6d9268f13521af6351f39

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol >= x) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Math50
### Patch Diff Hash-SHA-256:

caf4594bb1950671ce103ab2a1b77e640a8e4fe7bfbe7c704eedd1e69566911f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx > (DEFAULT_ABSOLUTE_ACCURACY)) || ((DEFAULT_ABSOLUTE_ACCURACY) < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Math50
### Patch Diff Hash-SHA-256:

ee726a09e272f84fd62b6572f8aab1197f535ddcf6546dc0734595faa7ee61a2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Math50
### Patch Diff Hash-SHA-256:

1ce1a8c17a188b1d5b7a1897295acd4e8763fb648d020168ae303cb21be528ea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((rtol >= 0) && (x1 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Math50
### Patch Diff Hash-SHA-256:

e9b6f0c9e99f8698f29358cc4305b64ddf6b722e30c27997efd05590d70c9990

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x0 >= 0) && ((DEFAULT_ABSOLUTE_ACCURACY) <= 0)) || ((x0 <= 0) && ((DEFAULT_ABSOLUTE_ACCURACY) >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Math50
### Patch Diff Hash-SHA-256:

30499bd28a23ea6e4f9c7d19597fa8a80ae3636f6fd2a044a82e3bd8f342ab5a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Math50
### Patch Diff Hash-SHA-256:

74db3709bb7c8b76adbaeb0ded0180708f1553feb6106f90b60c8d02eac9eee8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x < x0) && (x0 < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Math50
### Patch Diff Hash-SHA-256:

fa09847d823a69ffcdfd0fd4c8fe9bb59e324262b98c0029ff60419eaaf82dcf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Math50
### Patch Diff Hash-SHA-256:

90e2db35d5aab0279e67d7e052c714e726ada604b29edf1e8ab382a4ff919bf6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx * x1) > 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Math50
### Patch Diff Hash-SHA-256:

8bc03c8d1275bd51e52904149e855fddfaffe4b76f6ba21add9b588d96fc614e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((DEFAULT_ABSOLUTE_ACCURACY) >= 0) && (x0 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Math50
### Patch Diff Hash-SHA-256:

3eabcc0097ec62bf77e7b26bc735dc7de327202d8abe7dab08685fb6646d3f80

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) > atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Math50
### Patch Diff Hash-SHA-256:

e17b8ace464b56a34f4036ee24e4e173a3885f03834214674359a140cfaf9120

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (fx < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Math50
### Patch Diff Hash-SHA-256:

6cbbe16938026f452aa52f5b4a66ea3d21cbc11e2babb742a81334e816410cfb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x < x0) && (x0 < fx)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Math50
### Patch Diff Hash-SHA-256:

a72db45495e53f304d6f6170421bc7f9d753716e60c10f975303efa9cdb95daf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (atol < atol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Math50
### Patch Diff Hash-SHA-256:

0d065b871b03eb235cfe41837d2299ea380aabd9fcc7e81718e056c4fd6e8048

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((((x1 * ((4 * x1) - 5)) + 1) + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Math50
### Patch Diff Hash-SHA-256:

21f5cd2c3635b398ae351baa314dcef06eca93ea3b7cd9daaeb34b1015c65e3a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = (x1 < x1) ? x1 : x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Math50
### Patch Diff Hash-SHA-256:

6ccb8384b3b9361e8846fba0a7fefb41770b927370ab53753fb5bcff9569720d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.util.FastMath.max((x1 - 1.0), x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Math50
### Patch Diff Hash-SHA-256:

2cb19da84fe5c3df2e180e90017c57c76b3baf36c41f6cebb830c8d9f08f342a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x1 * ((((2 * x1) * x1) * (x1 - x1)) - ((x1 - x1) * (x1 - 1)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Math50
### Patch Diff Hash-SHA-256:

943b6a16b0bce49a9959bf762dd1dc48c8d6646f7084345c1605abc4e472a1e8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(x1, x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Math50
### Patch Diff Hash-SHA-256:

0a41a4e3c86d2fdebfbae6460d086af82ad98336361fb032c8d55fcabadb7840

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(x0, x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Math50
### Patch Diff Hash-SHA-256:

13742bbe241dbda3a7057cc9f069978b09f2419475ec394f6546e526b3336065

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 < x0) ? x0 : x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Math50
### Patch Diff Hash-SHA-256:

4e824caa88cd648aa27d12811b6e3dfb1cbfd10bc1f2e2dc5233e91efd33868b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = 1 - x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Math50
### Patch Diff Hash-SHA-256:

78a4732460bb1a96b1c7b35985ac0e43297e6c6e534bc3da7246475bf445f49a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.util.FastMath.min((x1 + 1.0), x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Math50
### Patch Diff Hash-SHA-256:

a71f9207a0c3ef75215a6f70d84addce630fce34579d724cf70d77d8bdc719ce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.util.FastMath.max(x1, (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 455 of bug id Math50
### Patch Diff Hash-SHA-256:

0b8ae6b3b75c5152c2c66fbd5ffe750c20dce8754664a380ae8fb78630b2704a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = (2 * x1) * x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 456 of bug id Math50
### Patch Diff Hash-SHA-256:

4c87616631e6cda2afdd39eb3d09ae4368fe9f4ed30e247146792bfa1f36655e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = (x1 > x1) ? x1 : x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 457 of bug id Math50
### Patch Diff Hash-SHA-256:

da56c92baaf0f50c784762b99b0e66780b6b99836bbfa62ab7ef6aeeba444035

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.util.FastMath.sqrt(((x1 * x1) - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 458 of bug id Math50
### Patch Diff Hash-SHA-256:

6272d4fc41c435dbce29f55df1aaaef25d3c3629a61980760a168fd8a7909ff3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = ((org.apache.commons.math.util.FastMath.abs(x1)) > (org.apache.commons.math.util.FastMath.abs(x1))) ? x1 : x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 459 of bug id Math50
### Patch Diff Hash-SHA-256:

222e34c4fab288a36160c8b06d4d0c6e50c07166e29bc4c33264d1bfce11fb70

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x1 / x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 460 of bug id Math50
### Patch Diff Hash-SHA-256:

62d08b51580979cb58b1da5a1b4e606702751917adf6110b8314fb8435ee5918

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = 1 - x0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 461 of bug id Math50
### Patch Diff Hash-SHA-256:

ffda7e1ce2c78eb231ce78b8981cad201b8e4acbe5aba6024976b1785ddc8be3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = (x0 < x1) ? x1 : x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 462 of bug id Math50
### Patch Diff Hash-SHA-256:

294fb9f81e3db4ff5f36a9989e295e92e9f56ed68dfcaa78901d7e336f3d5308

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 > x0) ? x0 : x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 463 of bug id Math50
### Patch Diff Hash-SHA-256:

0957ed2d27fd1d788b031e43071d792c9f52761c79b31b83ab7150471f188757

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.util.FastMath.abs(x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 464 of bug id Math50
### Patch Diff Hash-SHA-256:

75fe979833d068938edf41fa4d44e9bcab0bdd0afeae523e9579894c551d1fb7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = computeObjectiveValue(x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 465 of bug id Math50
### Patch Diff Hash-SHA-256:

da738affafe1329dc53e7e58e5be7fd7c1b3f0ccf5af9d822df242456cdd5e0d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x1 + (0.5 * (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 466 of bug id Math50
### Patch Diff Hash-SHA-256:

32e40e6cebad1c0467bab11214a39a28e7f90db146ea9b8717dd9b2ea039d24f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = x0 / x0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 467 of bug id Math50
### Patch Diff Hash-SHA-256:

e339d569e635f1ae1960fe0e4217af564399fcac6828c3b2e575c576e2d52c39

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = x1 / x1;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 468 of bug id Math50
### Patch Diff Hash-SHA-256:

36cb96a8969e9388207fe24539067066ea363694f5252eee394f8c0ba01048d0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 + (0.5 * (x0 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 469 of bug id Math50
### Patch Diff Hash-SHA-256:

5be4b5a422ddc8cd3bd6635c12019063c7d5769739c406ab10a52d4b5172cff5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.min((x0 + 1.0), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 470 of bug id Math50
### Patch Diff Hash-SHA-256:

6f419700da58cf4a77a8cdca6b1c0707c1d03d8cc756f10c40ab9445ad9a3059

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = x0 - x0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 471 of bug id Math50
### Patch Diff Hash-SHA-256:

25a79b77bac29fd6868457f11d3675d0af173de2537bc22cb3fbe64d81e0b5a4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x1 + (0.5 * (x0 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 472 of bug id Math50
### Patch Diff Hash-SHA-256:

145810d98a99a394afc24fb27ef1d514aa91946368ac84e92af4b4debc1b0e63

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = (x1 < x1) ? x1 : x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 473 of bug id Math50
### Patch Diff Hash-SHA-256:

002b5afb48c5017fbe8d3cc1657623956bddcd27a15fd4c3b708cbf5acd35f96

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (2 * x0) * x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 474 of bug id Math50
### Patch Diff Hash-SHA-256:

798f577a62b7eaf2b8a84c4f135f4f82a238646019e27fb0487f805dca5e8c93

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = 0.5 * (x1 + x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 475 of bug id Math50
### Patch Diff Hash-SHA-256:

fe62ba517a8cd605a583685d90a74346993ba696796e40270e31069567c74232

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = computeObjectiveValue(x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 476 of bug id Math50
### Patch Diff Hash-SHA-256:

40dd9ac5a4e0f8dcddf470fc557fa1a4ecd1f5d4305e73ad3626e7bc84119576

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = org.apache.commons.math.util.FastMath.sqrt(((x0 * x0) - x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 477 of bug id Math50
### Patch Diff Hash-SHA-256:

e48a1024809b68f3973caced132a9060312eb48173a6e7402bd13fb2f29d897c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x1 - (((2.0 * x1) * (x1 - x1)) / x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 478 of bug id Math50
### Patch Diff Hash-SHA-256:

48f7724f8da90ceb51ad5bdc309f75bd9ccdb46b31a87e0087d3bc609c2a754b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(x1, x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 479 of bug id Math50
### Patch Diff Hash-SHA-256:

2feabee491c5afdff115b563bf53125773ff7662061a1729d9ebe97f267d469f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = 0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 480 of bug id Math50
### Patch Diff Hash-SHA-256:

ff485f521c412f88c97e1b7b4d3555a6429ae3fa2e9898f9f172d399716f7050

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = 1 - x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 481 of bug id Math50
### Patch Diff Hash-SHA-256:

de2c9eb18e4eb4609723efbf7991e7e39bad0be91196ffb7f2a69b7b681d0ee1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = x1 / x0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 482 of bug id Math50
### Patch Diff Hash-SHA-256:

1f5fc20eb7e39a2249a8512b80e4b5684678172eeaa24a11c64fd237df5df048

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x1 + ((org.apache.commons.math.util.FastMath.random()) * (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 483 of bug id Math50
### Patch Diff Hash-SHA-256:

11e99fde08f28ac65b955d55445bca9377bf54ba971ac19cf864c932d5cd54ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.sqrt(((x0 * x0) - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 484 of bug id Math50
### Patch Diff Hash-SHA-256:

f2361fe941d805345bcc945f4341fee0265f3cb322072d27d97f0ca7e5b286cd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(x1, x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 485 of bug id Math50
### Patch Diff Hash-SHA-256:

36c1c179923fae5473f5cb7fb74deff72c88df5b9612d1cf8dc5b4e4f563e3a3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = org.apache.commons.math.util.FastMath.min((x1 + 1.0), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 486 of bug id Math50
### Patch Diff Hash-SHA-256:

6f07c7143d91ba5ce2cd44f8ed7e5c86f67f65206421b52d82a24de177830ce3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = 0.5 * ((x0 + x0) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x0)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 487 of bug id Math50
### Patch Diff Hash-SHA-256:

419d28777a56f2517c8d982b17d1a54b24ae2021f3ff461c84e817dd0a90a3f0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x1 * ((((2 * x0) * x1) * (x1 - x1)) - ((x1 - x1) * (x1 - 1)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 488 of bug id Math50
### Patch Diff Hash-SHA-256:

4aa8e4fb7b2e16fa446ad01a02bfac76a679edbd98e803890586e2060c82e490

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							x0 = -x0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 489 of bug id Math50
### Patch Diff Hash-SHA-256:

7c0088ecc0c4c72a7550312f6f88ba85773d9645fa619a3c0285d35767fc91df

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 490 of bug id Math50
### Patch Diff Hash-SHA-256:

5b2964b64083f951ad1b4538aa850f999b7c727752f288a82e0c5534964a9df0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((ftol <= 0) && (rtol >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 491 of bug id Math50
### Patch Diff Hash-SHA-256:

80d92adad9fbebe193b263fea3ca27ef2ff246ca76ef7edec265ed4df22788be

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x <= 0) && (f0 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 492 of bug id Math50
### Patch Diff Hash-SHA-256:

d60bddaa249da7c802c08d4d88af9c925f15bb97afa2572f7e61bb78c5e56b19

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 < f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 493 of bug id Math50
### Patch Diff Hash-SHA-256:

3513d664b3646b17352cee73a790e09fb3ec373c3fb2479da701ef9b08fa82a8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < ftol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 494 of bug id Math50
### Patch Diff Hash-SHA-256:

b1b2d938aeac003eb05ffcc3028327ce97b31cfc8efd2986f3add1fd5cf046a6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (rtol > (DEFAULT_ABSOLUTE_ACCURACY)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 495 of bug id Math50
### Patch Diff Hash-SHA-256:

3f7dc0ff3b81a4442a12d63979d95effa6caa334f4472e9baab05467cee3d31b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x >= 0) && (x0 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 496 of bug id Math50
### Patch Diff Hash-SHA-256:

3c7e7dd17e23769516a426ad409d2a3796e44e96bab3d916829ae69b65124c4e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (ftol > rtol) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 497 of bug id Math50
### Patch Diff Hash-SHA-256:

4946902e8a4760f2d2039af2ac614f3cc46449d1fb3fd0d14eb75c37e304e347

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x0 >= 0) && (x <= 0)) || ((x0 <= 0) && (x >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 498 of bug id Math50
### Patch Diff Hash-SHA-256:

86cc8288d9681ed2f3cfc9377ce0a78ab80c5166a76e9b5430d174ef4fa08f01

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((DEFAULT_ABSOLUTE_ACCURACY) < fx) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 499 of bug id Math50
### Patch Diff Hash-SHA-256:

1d8d404affb2f5169ba9ad6c52a6d44659c196dc8685d85b35f9e06068bb9283

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 < (DEFAULT_ABSOLUTE_ACCURACY)) && ((DEFAULT_ABSOLUTE_ACCURACY) < x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 500 of bug id Math50
### Patch Diff Hash-SHA-256:

a55d659308ccc1a5a58f035ab5571c1c854a4c41b5b48d2c0003ab6ffc74bb89

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx >= 0) && (atol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 501 of bug id Math50
### Patch Diff Hash-SHA-256:

76fdb97e7ecca72fd11c59e9d626ff4dda01e4ea08148343bd0d5ac580cbf28d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx * rtol) > 0.0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 502 of bug id Math50
### Patch Diff Hash-SHA-256:

24f86cf6e8304f759639b93ff59994572a272c6bd2c6d97d1e812b8b3003c5ea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x >= 0) && (x1 <= 0)) || ((x <= 0) && (x1 >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 503 of bug id Math50
### Patch Diff Hash-SHA-256:

f24b0310ff0e3afb0b63c222d99d592328497ca3ef3513326c0269e6d7b1b9a2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < fx) && (fx < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 504 of bug id Math50
### Patch Diff Hash-SHA-256:

c6472eb849393a7c67d31a285f17153a32f8746f3323a9be5bcb18159f490326

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 <= 0) && (fx >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 505 of bug id Math50
### Patch Diff Hash-SHA-256:

d7e78712670ee4eee6ec60a5236fafadca607756a726deb7336e88db48fc9221

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f0 >= 0) && (x0 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 506 of bug id Math50
### Patch Diff Hash-SHA-256:

d1c8d76733afb58ef571696645a3b93a9c201c26b1b111c78a1d873276b3907e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < x0) && (x0 < x)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 507 of bug id Math50
### Patch Diff Hash-SHA-256:

046a9798d5541ca69a63f52d136663348f6b72857e78d790b4f6695a777054f1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 < x0) && (x0 < (DEFAULT_ABSOLUTE_ACCURACY))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 508 of bug id Math50
### Patch Diff Hash-SHA-256:

600a990aadeb32114ec58b0998581223ac26ac6d4c834aab9df9d11751b0071a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((fx >= 0) && (rtol <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 509 of bug id Math50
### Patch Diff Hash-SHA-256:

b609664ae3a66d959303ba061dd86c60d386c666d180fbfb338ca1289b23dafc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 * (x1 - x1)) / (x1 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 510 of bug id Math50
### Patch Diff Hash-SHA-256:

bf8e5243383aec28b94cbd407e8ddeeae9b94199c123119faae5b1bf60f6147b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x0 * (x0 - x0)) / (x0 - x0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 511 of bug id Math50
### Patch Diff Hash-SHA-256:

602f284f9fac18d14629b23dd98c13fb6754ce46c2dbc0521957933e186fe898

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x1 - ((x1 * (x1 - x1)) / (x1 - x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 512 of bug id Math50
### Patch Diff Hash-SHA-256:

436e84dec2c18acc77ef775a4a7fbd79d6c913f91cb05ecda51e63d0622810f8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((x1 - x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 513 of bug id Math50
### Patch Diff Hash-SHA-256:

073ace886fb18d065c29c1c513e9d27728ff591a215513b4079f667431e3cbd9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 * x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 514 of bug id Math50
### Patch Diff Hash-SHA-256:

22e3b3abc77a8781749bf0aba7644a47da55e3114ad4099633edb4dd12e7b208

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = doSolve();
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 515 of bug id Math50
### Patch Diff Hash-SHA-256:

3126d246c343fbde3d66a64529946560873c0f305d30396a3669bca318085caf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x0 - ((x0 * (x0 - x0)) / (x0 - x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 516 of bug id Math50
### Patch Diff Hash-SHA-256:

466be629d0fbfa0e0faf8e3cccf67e5cd8842691afca0962ba4ad564ef6e5710

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x1) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x1)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 517 of bug id Math50
### Patch Diff Hash-SHA-256:

b6ac3f5b3688af610e7cfc50d91c9b812f461e2bbdd6960e0bebe7ba3361047b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = getMax();
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 518 of bug id Math50
### Patch Diff Hash-SHA-256:

2fd9952f0327262612e507bdd7f475c57cab7a593e13fb23a784032857387bf6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.isSequence(x1, x1, x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 519 of bug id Math50
### Patch Diff Hash-SHA-256:

d1f03c154c1de46eacfbcbff3b82f12d177548a07715289ee4ed494a1ac2711e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x1 * (x1 - x1)) / (x1 - x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 520 of bug id Math50
### Patch Diff Hash-SHA-256:

0c9d41f8e620cda63e0dd4b82f37f3fcfc84eab4509007097e5b79ed7a107df9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 521 of bug id Math50
### Patch Diff Hash-SHA-256:

2b4eb6d2a957faf1113e8ba5e76856c372dd01396b5f0b322b529a0d7e2bc821

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 522 of bug id Math50
### Patch Diff Hash-SHA-256:

fe32678e975910f90114154669b1499a264a53cfb3ff8bc4b75368041c862edf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 * x0) < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 523 of bug id Math50
### Patch Diff Hash-SHA-256:

5dd67af1ad1c5fedff369454c86f026b48e254eb2145ed5330997a611a5c216b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x1 * (x1 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 524 of bug id Math50
### Patch Diff Hash-SHA-256:

77f5971257ae80b26656eaaca3203e0c4890d9236759ffb8458585a43197d118

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 525 of bug id Math50
### Patch Diff Hash-SHA-256:

b3ae28e788cb1e0a3d62955db3da438d2db6c51709499bef33a932786913cc61

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 + x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 526 of bug id Math50
### Patch Diff Hash-SHA-256:

f9919654c265a0bf932e880a6fb59534dd565a3c92c17df395f7f67f98305ce9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 527 of bug id Math50
### Patch Diff Hash-SHA-256:

e90d9264c7b0961a22e71282932d884c0a3e34acebbe5f66716956818d847ace

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 - ((x1 * (x1 - x1)) / (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 528 of bug id Math50
### Patch Diff Hash-SHA-256:

5f973818fb39165449e86aee9ac035305bee9fc4412e088c9936e1da754a50d4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 + 1.0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 529 of bug id Math50
### Patch Diff Hash-SHA-256:

3b76b7c12ba41c14039e7d71596924589fdcffa5db6a4b965e494a997ad73eb5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = doSolve();
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 530 of bug id Math50
### Patch Diff Hash-SHA-256:

63f014a4cc01b3fec3876c51ac73c9ac35dd5e640be1798cb25b6e8f96b12af3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((x0 - x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 531 of bug id Math50
### Patch Diff Hash-SHA-256:

e4250caf9fc1464b9d1d0430bc5da4bd247b0f49a1aeb44a869e458b81ac5cae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x1 - x1;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 532 of bug id Math50
### Patch Diff Hash-SHA-256:

290911b18ab28239896ffd170c8ffd7c2e0f68772b0af3e50351443dca136a3b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 533 of bug id Math50
### Patch Diff Hash-SHA-256:

70576dc9d338dc9d23fe5f7ad645b073a77de338266a6fbcce82175c9a831733

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.min(x0, (x0 + x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 534 of bug id Math50
### Patch Diff Hash-SHA-256:

b827711ce169fee1e7692a7b287552244fe97c4283245b2fb0b13e7056b3bee9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * (x1 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 535 of bug id Math50
### Patch Diff Hash-SHA-256:

c0077efb411dec9ad401f6deb57438fd158acf8f7b3f7849a8fa4e97f4509921

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 + x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 536 of bug id Math50
### Patch Diff Hash-SHA-256:

671d8d90dbe0da2ae0a85d84f4a7fe8e4ca91e534591a25d73e2ea869ecbbedf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x0 - x0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 537 of bug id Math50
### Patch Diff Hash-SHA-256:

c5f693951d8351b27a8781a4fabbd3cc5424bfec53c66c1b97f371c08991baf1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 * (x0 - x0)) / (x0 - x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 538 of bug id Math50
### Patch Diff Hash-SHA-256:

1b2ee644bbb4f09ccd5318b7da185f9c8c39740e2323a9f793fc428586e0eba4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 > x1) || (x1 < x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 539 of bug id Math50
### Patch Diff Hash-SHA-256:

977fe3f89de33ffd0081133a87d21a9153cc5dc15ebae8daedcaf0b83d0cadde

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 >= 0) && (x1 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 540 of bug id Math50
### Patch Diff Hash-SHA-256:

dcaffd23114cee693b257c96aa27323b4277321f6a1d7143d1a53f6ef4d2426a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 + x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 541 of bug id Math50
### Patch Diff Hash-SHA-256:

0a6b7ff137ad0cda3fdd1441aac43f7ae4d5cee4ec872d966d7641c612a22849

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = computeObjectiveValue(x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 542 of bug id Math50
### Patch Diff Hash-SHA-256:

0298738eb5298be812ec1466fd08df5d8bc92e3fb189d1f9fb507f008a67f224

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 + 1.0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 543 of bug id Math50
### Patch Diff Hash-SHA-256:

1b770d9490bdc467a58829fa4fdd5b61f435c5add71d6c6f0fe62375603792f8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < x1) && (x1 < x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 544 of bug id Math50
### Patch Diff Hash-SHA-256:

da4d6b3005cce2ed464c576a7ddf013f134ba843267468f6d6c1d734749bd493

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x0 + x0) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x0)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 545 of bug id Math50
### Patch Diff Hash-SHA-256:

90cf20aa42293422a28c303f397d6520f7787a9ca798025db21cf707d0a2512b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.isSequence(x0, x0, x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 546 of bug id Math50
### Patch Diff Hash-SHA-256:

8c8ddbcf97924bf511f0434a93c90bbca8596069c08f143b053142f87374c212

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x1 >= 0) && (x1 <= 0)) || ((x1 <= 0) && (x1 >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 547 of bug id Math50
### Patch Diff Hash-SHA-256:

86cb639f3c15ef74536cc522447f51149e58af761936744c3941e53e246d4082

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x0))), x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 548 of bug id Math50
### Patch Diff Hash-SHA-256:

25b9d7b80d7ab5c1117eabc2a4f7508bb08449fa0f0e4ec67ea11ce36071ef7e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x1 - x0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 549 of bug id Math50
### Patch Diff Hash-SHA-256:

b9d5cf742b336bd1e4b1112d14802f8c1166b6c61975c139b47e59002ca37027

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 * (x1 - x1)) / (x1 - x0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 550 of bug id Math50
### Patch Diff Hash-SHA-256:

4acec2b5b0a914977dd9aac5598a3bbdd3f8008dcb326204592c95f70e5c942e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.min(x0, (x1 + x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 551 of bug id Math50
### Patch Diff Hash-SHA-256:

554329adb53f0786c338e7a913f6fc96773276add82e5157545512f3dbf8bc4a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 * (org.apache.commons.math.util.FastMath.abs(x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 552 of bug id Math50
### Patch Diff Hash-SHA-256:

70b28f1dde00cde1bb9a65d53c59763f5423510d597309fad90d956c9429a7b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max(x0, (x0 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 553 of bug id Math50
### Patch Diff Hash-SHA-256:

3f0847c489101104c195a472938cf6771a5b1bafcc3293209235c951f28c64c6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.min((x1 + 1.0), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 554 of bug id Math50
### Patch Diff Hash-SHA-256:

4c082a6843c629f4bc6ae5c4745c8fbb576641cc0fdc9e403c472109cbd3ee75

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 555 of bug id Math50
### Patch Diff Hash-SHA-256:

926a1a91731150c26d67a2dbddb57986fbfbadca1dde4d8021d091fa74153f2d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 * x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 556 of bug id Math50
### Patch Diff Hash-SHA-256:

f23db429f5c41f878304ec520b1dc6cf754f3d143806808dd344f91c90c04da6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.isSequence(x1, x0, x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 557 of bug id Math50
### Patch Diff Hash-SHA-256:

7ca779bda0206808e4af853a574cd3e0868db0e8d0b853def57e723f749250a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x1)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 558 of bug id Math50
### Patch Diff Hash-SHA-256:

a7bc81d50959d5c7d3ce41c7ca3f543564be9dfb8cd995409c0550add1b32387

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * x1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 559 of bug id Math50
### Patch Diff Hash-SHA-256:

9c339256259490845675f9bb0400577ab749c33301f2ae852ddbc2b9c73ce0a2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * (x0 - x0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 560 of bug id Math50
### Patch Diff Hash-SHA-256:

668289dab2072abd5fe94ab28b6f1ba5ac1c91c68eee5934b7536c1d0f7cbccd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x0 - 1.0), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 561 of bug id Math50
### Patch Diff Hash-SHA-256:

80aff33a22301821a42888804cc7a8549837a1b55854672cb936138759f46a6a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x0 * (x0 - x0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 562 of bug id Math50
### Patch Diff Hash-SHA-256:

453f9d7bdcb1a11f9fe998aef044cff154eb12a5480f603f5cf94499497386a8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 > x0) || (x0 < x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 563 of bug id Math50
### Patch Diff Hash-SHA-256:

fd1e1f196cfc643d901257b425a034920ca07bbeb5b61a265bd0e974194294ea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min((f1 + 1.0), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 564 of bug id Math50
### Patch Diff Hash-SHA-256:

c385259598a7c6eb272f7c7e890366445c9bb2e6be797106e95296febaba779b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 - 1.0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 565 of bug id Math50
### Patch Diff Hash-SHA-256:

118413520b7a1c60ad14c0948c3a0bfe2498cfb21cb0048db57c144c94e080df

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 - ((x0 * (x0 - x0)) / (x0 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 566 of bug id Math50
### Patch Diff Hash-SHA-256:

7aab2e90bc8c77a636a758772c3f9dbc98fbeb976996d9205b91d1107fbeee6a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x0))), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 567 of bug id Math50
### Patch Diff Hash-SHA-256:

9ab05e54210d57047480acda67057821ef4cabde40e686e2fe7668201369de97

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x1 - 1.0), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 568 of bug id Math50
### Patch Diff Hash-SHA-256:

9a02ba7f2244925a6d91d740c04e25c1ed7261032b1e003dd2f3ea701dc456e2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x0 * (x1 - x1)) / (x0 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 569 of bug id Math50
### Patch Diff Hash-SHA-256:

0c61c1a3405fce6ee0088e9e846574800c06775d7bcced93fbe38aff1f2a48a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 + x1) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 570 of bug id Math50
### Patch Diff Hash-SHA-256:

1dd99c59019faa18db9986e1316b5e96f0db1689f081efd24f9e51a13182b2ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = getFunctionValueAccuracy();
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 571 of bug id Math50
### Patch Diff Hash-SHA-256:

75178d99ff6d698881841c251488968bcad1b429aec0ce58dfdc7c3c62cd8807

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 + x0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 572 of bug id Math50
### Patch Diff Hash-SHA-256:

553431f979483e6afaadfaf7b27462cd87617919340a88f169ae1e3f3df63172

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * (org.apache.commons.math.util.FastMath.abs(x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 573 of bug id Math50
### Patch Diff Hash-SHA-256:

51f7fe66ab505b1592352ea8fd7a215a8a0235558c07e7d8328260bbfd8092c1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x0 - 1.0), x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 574 of bug id Math50
### Patch Diff Hash-SHA-256:

1ef1fb829de72c560e65805a02c51e098fe6bcf26846de4a0f59084cfae346b7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = f0 + f0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 575 of bug id Math50
### Patch Diff Hash-SHA-256:

472cf3781840d8482b5d12e06f02e19c9140a494b61c66a4238534599d66be56

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x0 + x0) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 576 of bug id Math50
### Patch Diff Hash-SHA-256:

ebbb915d3d7bbda601f257bd98743519265cac0a9e0a2803a5389cccb12a39ec

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x + x;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 577 of bug id Math50
### Patch Diff Hash-SHA-256:

252da36c4545c4282b35e691261408853bc731f76cb5d4663dd4953a1f4c8597

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * (org.apache.commons.math.util.FastMath.abs(x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 578 of bug id Math50
### Patch Diff Hash-SHA-256:

3f2e988f0c1fcff266fbc10e27994e04bb2385975724326189831860a0322747

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 <= 0) && (x1 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 579 of bug id Math50
### Patch Diff Hash-SHA-256:

413c1d1c252f216a5ab44eba8fed828384be00bc6dac52b7ac2d5e382c2f725a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x0 * (x1 - x0)) / (x0 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 580 of bug id Math50
### Patch Diff Hash-SHA-256:

1ca4034e103ed24357b97c8d207a8a321054c2cb6a5b045876a030841f1b6377

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 <= 0) && (x0 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 581 of bug id Math50
### Patch Diff Hash-SHA-256:

39e53bc950ff9b00e24b9dd4b9ae434ab5c768e4b44997c56c09ca80d422920a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 * (x0 - x0)) / (x1 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 582 of bug id Math50
### Patch Diff Hash-SHA-256:

7896f92b69cdf64c041c137abbcbd457b9ca8890648b2034fda26db33c8ec970

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 <= 0) && (x0 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 583 of bug id Math50
### Patch Diff Hash-SHA-256:

331bfcb170a54db127d2638ce67efd0896bc0a95fdb1efab07efc18a198dda53

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 <= 0) && (x1 >= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 584 of bug id Math50
### Patch Diff Hash-SHA-256:

c7b49b6e4abef4ce34654c2f9511ac21c7c7ddf3f5e453b152c2285074902346

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x0 * (x0 - x0)) / (x0 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 585 of bug id Math50
### Patch Diff Hash-SHA-256:

64902508de988e5945218c3ae1b691895b07d4eb9891aa3a4f4e81a502a03e60

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.max((f1 - 1.0), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 586 of bug id Math50
### Patch Diff Hash-SHA-256:

a5a1c84a30c8c05aef33f7a289759455b2bce24bbba9117578a79a3f3a7bcfc8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 < x0) && (x0 < x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 587 of bug id Math50
### Patch Diff Hash-SHA-256:

d73d6bb59aa4ab40fde941339f4660d7339012c47b8b8fa41650d2252c61a872

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = f0 * f0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 588 of bug id Math50
### Patch Diff Hash-SHA-256:

93c4b7434f7a0ac8161420ba0ed4e5fbfab7fa797a125ee378afa7561e0718de

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x1))), x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 589 of bug id Math50
### Patch Diff Hash-SHA-256:

695b131efd87d50b4be8c0035d80f0e24b5c7a0dd802dd6cbb823cd2d73c1e7a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1 * f1;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 590 of bug id Math50
### Patch Diff Hash-SHA-256:

1692766e4226f42110e845d5a8e575c2c52191d885298fb3aa71fad06dd39089

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 + x0) * 0.5;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 591 of bug id Math50
### Patch Diff Hash-SHA-256:

a77b895b2c7c1cfded20e3907dfbe105f18d7430a64c641d1325be2682620fe8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 + x1) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x1))), x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 592 of bug id Math50
### Patch Diff Hash-SHA-256:

d9a6139433b71c8a34d66e4039703ed5013c8f97e0d7e6cdb5dcfd0d7cedce64

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1 - 1.0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 593 of bug id Math50
### Patch Diff Hash-SHA-256:

ee2a894b01953452911618882fd68f7336b6b64853f33d4db279219ca1d852a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 + x1) * 0.5;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 594 of bug id Math50
### Patch Diff Hash-SHA-256:

e67798dd29e813cc670d61437cd56abf8be17c4c42e5a2fd34af28a5e0556468

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x1 + x0) * 0.5;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 595 of bug id Math50
### Patch Diff Hash-SHA-256:

5a03fdb1101d4213f0f5c03ad8f338db612a8c56f1258dafedb656ca933245b3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 + (0.5 * (x1 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 596 of bug id Math50
### Patch Diff Hash-SHA-256:

8668efd0cd870a1b1ff21aaf41af0fda3cd7865dbcbd748bed9a13bd10504d36

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x1) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x1))), x1)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 597 of bug id Math50
### Patch Diff Hash-SHA-256:

163a92bdfc3cd38dedfc8e550b6e55326565941a879038b322c6b5348883f8e0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * (x1 - x0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 598 of bug id Math50
### Patch Diff Hash-SHA-256:

fb323f3d24f8aed1dcbfac03a7469c2f6e1f703011f327899355077916e22ea2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 + (0.5 * (x0 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 599 of bug id Math50
### Patch Diff Hash-SHA-256:

3231e194eeb30ab515552b58755c1214ff1f54f123b5ea59cc217e8267dbab21

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x0 * (x1 - x1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 600 of bug id Math50
### Patch Diff Hash-SHA-256:

6bebac3cf0955d6c64687116475df8b435d12a99e0febba98a6bf08adf8661e8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max(x0, (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 601 of bug id Math50
### Patch Diff Hash-SHA-256:

f305ac32b9bedb850980e5d792adf2f917205d4f4eb99b6d33df1e894adc94f6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = fx - 1.0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 602 of bug id Math50
### Patch Diff Hash-SHA-256:

8e4422323bd4e4bcf5e85fbee8cf04537e50038ae42ba24a8b12031cf96f3700

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = atol - 1.0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 603 of bug id Math50
### Patch Diff Hash-SHA-256:

34570f1176dde1a39ace59a3c837d2a28e9ca80e36b0996023e6a377cc228c2d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = f0 + 1.0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 604 of bug id Math50
### Patch Diff Hash-SHA-256:

510fd4f7a41e903b35ccd5c6676a2a972e0e54803d80b65fb0234b1f1a9eb95f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.abs(x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 605 of bug id Math50
### Patch Diff Hash-SHA-256:

44c68a3f819f39af744d97b81111c927a5653f84fff52734ce991c6719c78d8b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 * (org.apache.commons.math.util.FastMath.abs(x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 606 of bug id Math50
### Patch Diff Hash-SHA-256:

205675a9296bca7438302d81e721c69a6b870303566878f7b97d060aa157be76

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (f1 + f1) * 0.5;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 607 of bug id Math50
### Patch Diff Hash-SHA-256:

f06ff20b41a480b5fa610577fa639ed68e404310c5c98e9709db7a9e62e20c7f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x + 1.0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 608 of bug id Math50
### Patch Diff Hash-SHA-256:

d337c0a95b8f0338a5c1bc8fd91b4286128839a9b5e1eed37bfab8e2acfc3115

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = rtol - 1.0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 609 of bug id Math50
### Patch Diff Hash-SHA-256:

4ec9d22f0ff485e12486d5fece4a10a318a42ec11fbd6438a0021557a429cc74

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = computeObjectiveValue(f0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 610 of bug id Math50
### Patch Diff Hash-SHA-256:

a2d5a9ecbd220681818467a58b956c2f978dc39e78fd39bdf7d7804631fdeb3c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1 * (org.apache.commons.math.util.FastMath.abs(f1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 611 of bug id Math50
### Patch Diff Hash-SHA-256:

f79dd156a01dc93cd395b41f55d4c88e2b4b381deea2a2e6ab9bda061e866679

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.abs(f0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 612 of bug id Math50
### Patch Diff Hash-SHA-256:

5b82dd1b76e827b5829cf867a7b3952535d581e6dab2d88f2f2e7240ec6e3df4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x1 * (x0 - x1)) / (x1 - x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 613 of bug id Math50
### Patch Diff Hash-SHA-256:

d45426c0c0680e30a3dccfe280b6b0eec8ee3af3874d5469017acb2f88ffd46d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = f0 * (org.apache.commons.math.util.FastMath.abs(f0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 614 of bug id Math50
### Patch Diff Hash-SHA-256:

0fd71699a09859ebbd6becec51f9e5766c67db78de52d46aac86d6b46c3cd792

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x1))), x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 615 of bug id Math50
### Patch Diff Hash-SHA-256:

cf0aa09a52e93e9d7140c7c8acbea5bb81d0e34e1c04d7c525b8f24d7ec7a279

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(x);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 616 of bug id Math50
### Patch Diff Hash-SHA-256:

3ca585731b6efbe0f2d5e83cf56103ffc1d74b55a05282034d1590010af94abb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 * x1) < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 617 of bug id Math50
### Patch Diff Hash-SHA-256:

8641b2c6f61462a64824d134cd3de01e27bfbd64c6b8b0b2e36fd9b8e5e173ea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1 - f1;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 618 of bug id Math50
### Patch Diff Hash-SHA-256:

6ea7fe6dc2d34b11a0dccbc979880647970355daf672fbfef6d7b20524e42ddd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = ftol - 1.0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 619 of bug id Math50
### Patch Diff Hash-SHA-256:

8840d60acf4f222e56da2af8be018a34fb74ef936a61e8e0c0fe67070c9ea910

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x0 == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 620 of bug id Math50
### Patch Diff Hash-SHA-256:

e5af88bc892d34613724eb7ece32d35e8266acf1525ffebaee55385a6c07cc08

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x0 - ((x0 * (x0 - x1)) / (x0 - x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 621 of bug id Math50
### Patch Diff Hash-SHA-256:

2c90475da22f80c888d1bfa927d59a39c5df5a6e58c918d8b6c235e0dd7982d5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = f0 - 1.0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 622 of bug id Math50
### Patch Diff Hash-SHA-256:

7ff739121575960dcc0e76f0223586dc620424cd738d9ea90d38da47fc7d85ed

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f0 - f0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 623 of bug id Math50
### Patch Diff Hash-SHA-256:

1d173d9918b9e00243e1eff5bfb46ba950c3464dbee08227085642f935125c88

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max(x0, (x1 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 624 of bug id Math50
### Patch Diff Hash-SHA-256:

fac398328c16e0f64ebe775176b022ae838deebe7a215a4c24fcb3f8e9be112c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(fx);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 625 of bug id Math50
### Patch Diff Hash-SHA-256:

9d858401661f7d07c85c5a3c191374e14453bb96216b0453938b595d7dc4e3ef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(atol);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 626 of bug id Math50
### Patch Diff Hash-SHA-256:

dd39a96597d567d9125a6fa983ececaaf5aef7a94e340fea601aa7b068bc8c1c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((f0 - 1.0), f0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 627 of bug id Math50
### Patch Diff Hash-SHA-256:

71e7d30010099999896a5a6c040da67bba5e7be5ee3e97fb62f7e485fca0425e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 > f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 628 of bug id Math50
### Patch Diff Hash-SHA-256:

a5840907ea99c69576a23a680000a96e2a8428e22f74dc776fb8eceff616f3fa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.max(f1, (f1 - f1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 629 of bug id Math50
### Patch Diff Hash-SHA-256:

d38e90eba8bd4bee709a3f1835946f3d78986be8520b3cbdc1e11dae2275c07e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x * (org.apache.commons.math.util.FastMath.abs(x));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 630 of bug id Math50
### Patch Diff Hash-SHA-256:

f8c2f3e7cfff4c2f937b2709fe15c5a73a63946acd0037b5401715a6d6166015

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (DEFAULT_ABSOLUTE_ACCURACY) - 1.0;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 631 of bug id Math50
### Patch Diff Hash-SHA-256:

b305e75f2d007b9d8fa00c1f620bbf9506eb34e6f0762596d43f6113016daafa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(rtol);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 632 of bug id Math50
### Patch Diff Hash-SHA-256:

0eb7d7365079d299ec9e6c818db751bb61a373172c7cd510ce33d4f85f226f4d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x0) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x0))), x1)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 633 of bug id Math50
### Patch Diff Hash-SHA-256:

90e1895382b471ae97aeb17ba7463078a042dcaeaae9530b760fd8bdccacac92

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((org.apache.commons.math.util.FastMath.abs(f1)) <= f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 634 of bug id Math50
### Patch Diff Hash-SHA-256:

6dafe4da58a274d8c335c52555d037b6f7743ed9e1096949fdda81ff3b65502b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 * (x0 - x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 635 of bug id Math50
### Patch Diff Hash-SHA-256:

541c90d8c676cdebd6d5c61a7c8c93eea8d03ae47829334e19271cae0297ba4d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.max((fx - 1.0), fx);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 636 of bug id Math50
### Patch Diff Hash-SHA-256:

4fa92308ca0b9dd0970afbe6844fbba055d92efda51bad3a49f8052e2c5cf6c0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1 + f1;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 637 of bug id Math50
### Patch Diff Hash-SHA-256:

68801ef26ff3d400735ef3e02c549c3da87eefc7a8e30352b55a0676ffe02e32

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x - x;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 638 of bug id Math50
### Patch Diff Hash-SHA-256:

d0bd3f393be6b4ae25d64528c9510ac0ed3d03eabbdec22222938890160039d2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (fx + fx) * 0.5;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 639 of bug id Math50
### Patch Diff Hash-SHA-256:

c1f053f5945f6e8dc1bfcd2f46e572882b5d1fb085c0c30e5b1bab99b84db4b3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(ftol);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 640 of bug id Math50
### Patch Diff Hash-SHA-256:

180ff61b2e1220ea9cae8ed48be413dd6f4c685d4076556bdfa6b0660b32a802

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = fx + fx;
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 641 of bug id Math50
### Patch Diff Hash-SHA-256:

2f601359ae4583cf2ac5d8615fbdef5253760549e9426112270035961ad531fc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 * x0) < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 642 of bug id Math50
### Patch Diff Hash-SHA-256:

9fb8c5e035265b23539d156e250513569d6bc6d2f03c6ba15339d22a9309b118

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = f0 + (0.5 * (f0 - f0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 643 of bug id Math50
### Patch Diff Hash-SHA-256:

3f817fcb20c94a03c3f32780bc2c00295d6e34143f635114a72239d43e74e08a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * (x0 - x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 644 of bug id Math50
### Patch Diff Hash-SHA-256:

56bf93da4a2106abad5bc28e047dbcef4a3e6200075ef2143f6fb5c9bd34c206

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (f0 + f0) * 0.5;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 645 of bug id Math50
### Patch Diff Hash-SHA-256:

8095236186d78d7fc96910397dcb9972bde33305293561ffbe12753499b322c3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * (f1 - f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 646 of bug id Math50
### Patch Diff Hash-SHA-256:

8a75592f7bc423efa3e1b571c6a8d682af3e5125cad581972951e75cc1284244

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = fx * (org.apache.commons.math.util.FastMath.abs(fx));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 647 of bug id Math50
### Patch Diff Hash-SHA-256:

7be96b5d57165145ab6a8a7eee61558be92c2dc63f68caae6d4f16b6d66cda82

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * (f0 - f0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 648 of bug id Math50
### Patch Diff Hash-SHA-256:

90e5a4c2e33772bc593a6128e1470c2e12363c76f29b3c459c738dd33fb2aa40

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x0 >= 0) && (x1 <= 0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 649 of bug id Math50
### Patch Diff Hash-SHA-256:

aa783a2e1b878ab29f33d2b64cec5366127e63c988731ae8b9e53e2759c2eeee

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x1 * (x1 - x0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 650 of bug id Math50
### Patch Diff Hash-SHA-256:

957e4120666af1bcfef4307a2f906920073b44aa4404415afec4d17bfc1b2d2b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x0 + x1) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 651 of bug id Math50
### Patch Diff Hash-SHA-256:

85184cb69c32a40978edcfff722d5b7e1b59a7cf982faba5c508841935ba99d5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.abs((x0 - f1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 652 of bug id Math50
### Patch Diff Hash-SHA-256:

e6eb6cbf93e17e3c72c7dcda5b932dae2665ece76e86be7c9ee6135a6a67e612

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 + x0) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x0))), x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 653 of bug id Math50
### Patch Diff Hash-SHA-256:

74d22ec83abf5940f949e304c404bf38c19f6078d7a5b98bfbb27d7f50b674b2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x1) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x0)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 654 of bug id Math50
### Patch Diff Hash-SHA-256:

6416d9df7fc9717f6294bf1bbe31a87da285c47aff1072dedb977f5bd2a44623

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x1) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x1))), x0)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 655 of bug id Math50
### Patch Diff Hash-SHA-256:

3d2a4bbf2d8b8a561ab1ae3f8e1707a5258774e86f40a5665a7c449dcda60162

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 + x0) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 656 of bug id Math50
### Patch Diff Hash-SHA-256:

bcd43d783536e70cf814a851aed0fcd46a8849c795cef9545fc0ffd8a0d4ee4b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 * (x0 - x1)) / (x0 - x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 657 of bug id Math50
### Patch Diff Hash-SHA-256:

fcdb7de8e54b480f4320257217b23b61a22988088342f30df831f938e610e592

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.min(x0, (x0 + x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 658 of bug id Math50
### Patch Diff Hash-SHA-256:

dc6dd7db12408e1951d9a9ea5f6f1041903ccf8b4ca7c3df742c2fd01809f9f5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = x1 * (x0 - x0);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 659 of bug id Math50
### Patch Diff Hash-SHA-256:

5626726f211a8b28d73814efd0c98c0161d0c6e2f79d9808c376614228735e03

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x0) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x1)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 660 of bug id Math50
### Patch Diff Hash-SHA-256:

b75f353073295d5a6db4ef38e3b8e378b1145101e3c48a668733aa6a1a249903

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 + x1) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x1))), x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 661 of bug id Math50
### Patch Diff Hash-SHA-256:

b5a3e6e8965554460a078a5025d63b69a5540eb643ea53e6ea61e81a89c4c73e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.isSequence(x0, x1, x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 662 of bug id Math50
### Patch Diff Hash-SHA-256:

af1b1ff8a2dd732c01360ad1934499b740ae7904fb988c65ba99ae89e596f8c4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 663 of bug id Math50
### Patch Diff Hash-SHA-256:

7796698d34d02d0d20826c4f758e980f6e10f541f6a1ffab291895b7c216a1ff

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (((x0 >= 0) && (x1 <= 0)) || ((x0 <= 0) && (x1 >= 0))) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 664 of bug id Math50
### Patch Diff Hash-SHA-256:

9ec3272a455c267c8ca803f47ba940ce8f4eb84a91cafb63341e00bbfd29d321

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x0) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x0))), x0)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 665 of bug id Math50
### Patch Diff Hash-SHA-256:

a29a7f08f29c68f6e97c3754afa240670ac1e2913f2e38e92111a9a9f908e033

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < x0) && (x0 < x1)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 666 of bug id Math50
### Patch Diff Hash-SHA-256:

a8338f6ef4c1c5d4b45d84820040feefea12a293c2d3f908d34f97d224f0f46f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.isSequence(x1, x1, x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 667 of bug id Math50
### Patch Diff Hash-SHA-256:

35e9ffecd74bab26bd45f17f17a4ff0f10d3534a78cca89b5616d0320777ec1d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs(ftol);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 668 of bug id Math50
### Patch Diff Hash-SHA-256:

03c80eaf6401261d5759012b57aba8b4bde7f514f3c49b51ffc1caffe3a8ebf5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f1 < f1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 669 of bug id Math50
### Patch Diff Hash-SHA-256:

fad1a873ad432a6a3d11cf7e0b8e548c7fd74e8709218ecbe6ad82e40b99a86c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1 * (f1 - f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 670 of bug id Math50
### Patch Diff Hash-SHA-256:

d2751d8e2cf2bc35298743fddcc6b6e6941e9322af129a9b86f117cc86882f91

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 + x0) - (org.apache.commons.math.util.FastMath.max((x1 * (org.apache.commons.math.util.FastMath.abs(x0))), x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 671 of bug id Math50
### Patch Diff Hash-SHA-256:

4ca8e4fb497271088016708cf844945a509aa6f5e3871499772386da2b49a0a4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((f1 * f1) < 0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 672 of bug id Math50
### Patch Diff Hash-SHA-256:

4030a57930f9d46e50f3c8214cb516ae1350e9f64d7713d9626c3a11d04930ef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 * (x1 - x1)) / (x0 - x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 673 of bug id Math50
### Patch Diff Hash-SHA-256:

492298b664540598d0a797becc6fb1a3fd5da9df49871708cacfe16976dab3ab

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = (x1 + x1) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x1))), x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 674 of bug id Math50
### Patch Diff Hash-SHA-256:

7974d2b2c68d1224024cc12ab4b48c87aed45791a1dced347b4ddd934260bc73

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = 0.5 * ((x1 + x0) - (org.apache.commons.math.util.FastMath.max((x0 * (org.apache.commons.math.util.FastMath.abs(x0))), x0)));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 675 of bug id Math50
### Patch Diff Hash-SHA-256:

4062acb6c2daaf2115bccd25ca5567b48f70f678c47430832a493b4f137bac65

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((f1 - f1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 676 of bug id Math50
### Patch Diff Hash-SHA-256:

4f20c9694d0986d1db9293c54e1c0d4bd86a4f1c35f58060850ea3164e172e7f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x0 + x1) - (doSolve()));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 677 of bug id Math50
### Patch Diff Hash-SHA-256:

93e1e5fcd5708672d9d5841fdab5b0f612201d285f782de67ddba9e3e27aabd5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x0 + x1) - (getRelativeAccuracy()));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 678 of bug id Math50
### Patch Diff Hash-SHA-256:

4ecaf32eb22f57775d5c1fc40b76adc3895a0f1f1a1ee1b70c7d1518b44918ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min((fx + 1.0), fx);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 679 of bug id Math50
### Patch Diff Hash-SHA-256:

d72f18b3c4d31d0d3edc0566e70c85189d0da0cdbe804501fa74089024cfec6d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 - ((x1 * (x0 - x1)) / (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 680 of bug id Math50
### Patch Diff Hash-SHA-256:

8b4d5852dec4a2d048f480c4ba009adb9aa163b94c6a225886e2fa865602eeae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((f0 - f0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 681 of bug id Math50
### Patch Diff Hash-SHA-256:

4eae66bb36a4413eb0d3c501849b79f289f857694e6b2a5d635444cf82d44648

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.max((f1 * (org.apache.commons.math.util.FastMath.abs(f1))), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 682 of bug id Math50
### Patch Diff Hash-SHA-256:

e30523fda1032b7255cc818450e83e021abe2ebd4891e86aa2364ae9189cd358

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((x - x));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 683 of bug id Math50
### Patch Diff Hash-SHA-256:

85094d615ea8074f739678040a583cb051db1d4574a57691727f1b0e127f2e61

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 - ((x1 * (x0 - x1)) / (x1 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 684 of bug id Math50
### Patch Diff Hash-SHA-256:

a51e0c0b7bc0ef64d69ceeb358be747c36144b7b833d8bc03313cd7bc384d90d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((fx - fx));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 685 of bug id Math50
### Patch Diff Hash-SHA-256:

170d57cd203dc3e68fb6c0489590c1965881b532ea00942988c67f4fd2833ac1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min((x1 + 1.0), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 686 of bug id Math50
### Patch Diff Hash-SHA-256:

70aa53d01e69557c1e7dcb63fe1806e769f9f2c7114a03d45f31bc16589b8bcd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min((x0 + 1.0), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 687 of bug id Math50
### Patch Diff Hash-SHA-256:

5c09ea366bda4f80d8d45a8aaa7f04248d548a3818ae47439147b8fd940259e3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min((f0 + 1.0), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 688 of bug id Math50
### Patch Diff Hash-SHA-256:

ca964a1c51a32ab0ed9c2304885a96900c297a7dcbae994af548ac37fc310c28

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 - ((x1 * (x1 - x0)) / (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 689 of bug id Math50
### Patch Diff Hash-SHA-256:

b66c4d37bb495310b5a4e444a1338207d4106d4733f30be0999a933864d68b06

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x * x;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 690 of bug id Math50
### Patch Diff Hash-SHA-256:

37c5f5f5f37156d8dbd581b9f8c27119296773cc8aaf97d581e90696f24c55dc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((f1 - fx));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 691 of bug id Math50
### Patch Diff Hash-SHA-256:

16f05ed652f1c582c9d324441a65f4f76ca6d0600c08cff6c7a7060f599efbc4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(DEFAULT_ABSOLUTE_ACCURACY);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 692 of bug id Math50
### Patch Diff Hash-SHA-256:

cee784df5113e6b194b1c5d043b5340fb723caa38b53e332fd4346ec369f19a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min(f1, (f1 + f1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 693 of bug id Math50
### Patch Diff Hash-SHA-256:

4bb6d31921dc10fd76dc9de7d067e64776fab902857301a4e8820cfa1771270f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((fx - f1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 694 of bug id Math50
### Patch Diff Hash-SHA-256:

2d4b378e76e0df490b3197a6caad20aed7f55ecd7fb55071c7608ecde561e820

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.max(f1, (x1 - x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 695 of bug id Math50
### Patch Diff Hash-SHA-256:

cc1d2f077b41315a072ceb74a62f008f373710f578aa487a28b12bb9659243a5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min(f1, (x1 + x0));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 696 of bug id Math50
### Patch Diff Hash-SHA-256:

47392595ef989e0bc7d497b3559ca75b8d09b0d02eeb3cad4e3aed1f23f7dff9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 - ((x0 * (x1 - x0)) / (x0 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 697 of bug id Math50
### Patch Diff Hash-SHA-256:

d11498d20ca089f679756cbbe7d8c50a22c6c2db0ece7d68337027efbe24b975

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (x1 == x0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 698 of bug id Math50
### Patch Diff Hash-SHA-256:

adfeaf6a01b2e832b2d2a62b4009e859c316c687f0f2cbf8297ef69370f455d9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (doSolve())), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 699 of bug id Math50
### Patch Diff Hash-SHA-256:

c134323cce3acbcfbff015f8cb27439ff8f974d48bdb81c5d0d9f812ef510b82

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * (x1 * (org.apache.commons.math.util.FastMath.abs(x1)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 700 of bug id Math50
### Patch Diff Hash-SHA-256:

6597835f4fb33e2454f9ad43b153e8fb739049e3a06cbb03739c05e0c45f46eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min(f1, (x0 + x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 701 of bug id Math50
### Patch Diff Hash-SHA-256:

0783e9cbc2efb822d3049823824e7d51767fd8fb8fec3bf8c67ac08494add6bd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.max((f1 - 1.0), fx);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 702 of bug id Math50
### Patch Diff Hash-SHA-256:

2122b4f36ccd5a3364863baf9460a861f2734f53525ec0f2daf33c9b80e6f4ff

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.max((fx - 1.0), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 703 of bug id Math50
### Patch Diff Hash-SHA-256:

4a1817051b4c3e88c89cf58a0256024f3fa58fb3c5406f8c3af42ad60a8909b1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 - ((x1 * (x0 - x0)) / (x1 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 704 of bug id Math50
### Patch Diff Hash-SHA-256:

df4502d0e8f512841da2af97874978503a168e8aadcc3b033e21778f30f23f6c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 - ((x0 * (x0 - x0)) / (x0 - x1));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 705 of bug id Math50
### Patch Diff Hash-SHA-256:

1750da60f8943243821f0344af97b957915dd5eee968e0b4a310de07b3a11718

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * (x1 - f1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 706 of bug id Math50
### Patch Diff Hash-SHA-256:

d6f079017ac9102403d62c59585c01a86220b8d40c5a26c3063334d3ae81f759

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x1 - ((x0 * (x1 - x1)) / (x0 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 707 of bug id Math50
### Patch Diff Hash-SHA-256:

287c1bb4f3fbcaf9a2b4e294fecbc3f407dd40ff5b5a78842d2b8cd8c11a5a5f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min((fx + 1.0), f1);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 708 of bug id Math50
### Patch Diff Hash-SHA-256:

4901b76bd298b932ac70e0fbeba59eece3c9bfee43f5f6569588ef7ab024b15d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * (x1 - atol);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 709 of bug id Math50
### Patch Diff Hash-SHA-256:

80d88e490527f4690fcdc8362aeb459df264b918c13de4298b0924652e20c2eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = f0 + (0.5 * (f1 - f0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 710 of bug id Math50
### Patch Diff Hash-SHA-256:

7f44aea7ac4182b828a7dc47e14a94929cd6c27dd95b4ee17ddc2b83928939a8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.min((f1 + 1.0), fx);
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 711 of bug id Math50
### Patch Diff Hash-SHA-256:

e275bbe3ada189553da521b5c80912ed6b82f612c5a8f24ce0e74d549c1d1b76

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = org.apache.commons.math.util.FastMath.abs((x - x1));
 						}
 						break;
 					default :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 712 of bug id Math50
### Patch Diff Hash-SHA-256:

300fdfef562c50b3974f40b3907b706c723be9b5fe44ac5d2eeb295027f1ffec

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 * (x1 - rtol);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 713 of bug id Math50
### Patch Diff Hash-SHA-256:

02dd4e49725e20264282fcedc3f6f4787450fc53a2971353c6efa35de3f06f77

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if ((x1 < x1) && (x1 < x0)) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 714 of bug id Math50
### Patch Diff Hash-SHA-256:

33a79262ea27ae78275a781f1157270c837f2b2ea0e5f08bb78a5392a0d3443b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = x0 - ((x1 * (x0 - x0)) / (x1 - x0));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 715 of bug id Math50
### Patch Diff Hash-SHA-256:

34b98323a8faf8549da6c482bb5648f1713c46ad7d328bef5d48fb925d06a924

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x1 * (x1 - x0)) / (x1 - x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 716 of bug id Math50
### Patch Diff Hash-SHA-256:

13fc71763ccd2473ffd64dc136482142c046866e39fd0193ddec67e8b393dcf1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x1 * (org.apache.commons.math.util.FastMath.abs(x1))) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 717 of bug id Math50
### Patch Diff Hash-SHA-256:

195250f43e3827a0ecae2fc2a64dd85597de53d6ef3058af3b2d0273aa54c3f6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x0 + x1) - (getFunctionValueAccuracy()));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 718 of bug id Math50
### Patch Diff Hash-SHA-256:

e68381140f042f891ff0502ec33c9dbc859437c2d16d233b4a0ec11af159dab5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,7 +77,7 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
+						if (f0 < f0) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 719 of bug id Math50
### Patch Diff Hash-SHA-256:

6657657017bed93d72c0ba325608efcba3b76fa1c1db77d915cd8cd6258e3b71

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = (x0 * (x1 - x0)) / (x0 - x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 720 of bug id Math50
### Patch Diff Hash-SHA-256:

683f77c2b39a2591b95bbeff18b321b2bb5a441193cc8bde36b326a73037c4b4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (computeObjectiveValue(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 721 of bug id Math50
### Patch Diff Hash-SHA-256:

b17d8ccde73a063a71a337857619e1fe4265ce34af3fa3543106d400c22e8ccd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x0 + x1) - (0.5 * (x1 - x1)));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 722 of bug id Math50
### Patch Diff Hash-SHA-256:

86c186ba0655af9a25286696defb911be9c443588219a06d778ad5c4eb1d4415

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.abs((x1 - x1))));
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---