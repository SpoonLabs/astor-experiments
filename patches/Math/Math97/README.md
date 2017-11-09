
# Patches of Math97 from Defects4J 
Total patches 86
## Patch 1 of bug id Math97
### Patch Diff Hash-SHA-256:

640c98a828a6ae64a9827d8a83851694f493c883c033a77024b29197158d0706

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -44,7 +44,7 @@
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
 		double yMax = f.value(max);
-		double sign = yMin * yMax;
+		double sign = yMin - (0.5 * max);
 		if (sign >= 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math97
### Patch Diff Hash-SHA-256:

f385ecd7b2c2c496bccccf20b712788bdb28739ac77135b73e7c05ba51801aba

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -44,7 +44,7 @@
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
 		double yMax = f.value(max);
-		double sign = yMin * yMax;
+		double sign = ((1.5 * yMax) * yMin) - (java.lang.Math.abs((min * yMin)));
 		if (sign >= 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math97
### Patch Diff Hash-SHA-256:

182d29f0cf7fccfe344ca365807559998003a2b83778985cd9fb88a531e04a3b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -44,7 +44,7 @@
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
 		double yMax = f.value(max);
-		double sign = yMin * yMax;
+		double sign = ((1.5 * yMin) * yMax) - (java.lang.Math.abs((min * yMax)));
 		if (sign >= 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math97
### Patch Diff Hash-SHA-256:

8f3d78f6533a597ecc3ceb182efebcee30fa72908439232d8806af49faa256f3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -44,7 +44,7 @@
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
 		double yMax = f.value(max);
-		double sign = yMin * yMax;
+		double sign = ((1.5 * yMax) * yMin) - (java.lang.Math.abs((yMin * yMin)));
 		if (sign >= 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math97
### Patch Diff Hash-SHA-256:

6fc8b8c354ddffcdb646b918cd5818b7fd473a8d54b38601464b70c3cc91b43d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(functionValueAccuracy)) <= sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math97
### Patch Diff Hash-SHA-256:

25b7ab6c0564e3be621f7637c823efb398b1b3ee37d2dcdb7eda34800d30c8c6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(result)) <= sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math97
### Patch Diff Hash-SHA-256:

4b9527c3115c359fdc721d663743de9c5a5904760e580cf15c3fa4591fa8b405

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(absoluteAccuracy)) <= sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math97
### Patch Diff Hash-SHA-256:

197e9bd73bad34561dd10789a4f0ce365ba09cc0a21cd2105068504c170f1bb1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(relativeAccuracy)) <= sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math97
### Patch Diff Hash-SHA-256:

a36a30bd307fa72f52a90989ca1da25b5c869718e5fa444967bf8b1017d0b64e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(defaultAbsoluteAccuracy)) <= sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math97
### Patch Diff Hash-SHA-256:

6a210e50d55be7d621e13fc686566a517a61e44340ad7137d9a8fd94bbab4868

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(defaultRelativeAccuracy)) <= sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math97
### Patch Diff Hash-SHA-256:

5230315d4cd7d30b5898ed057078d3661657412d3bf09daefc3d3f820547e141

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(defaultFunctionValueAccuracy)) <= sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math97
### Patch Diff Hash-SHA-256:

369b9e1e7237d86b2aa55a900304869c82690a222236e09dc16ec7c2b0cd4d5e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -44,7 +44,7 @@
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
 		double yMax = f.value(max);
-		double sign = yMin * yMax;
+		double sign = ((1.5 * yMax) * yMin) - (java.lang.Math.abs(((functionValueAccuracy) * yMin)));
 		if (sign >= 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math97
### Patch Diff Hash-SHA-256:

f50fe5047f0c1364faa6db68bbb39dc2aa8068a3fe485a21df89f3535917b3a0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(functionValueAccuracy)) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math97
### Patch Diff Hash-SHA-256:

d60d48dfe1009d6b66c8904fa34c9b3300f6d81f1f8427425dc9cdfb67756272

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((functionValueAccuracy) < yMin) && (yMin < yMax)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math97
### Patch Diff Hash-SHA-256:

fab74dca72d28da0b7d41b9b833cde6c4642843f1c6998eab8ee60fcfaa91845

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(result)) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math97
### Patch Diff Hash-SHA-256:

a171d625fa7a5481f6f7d75f675f217a65adcd9abc7595ede81bce3bdc41313b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(absoluteAccuracy)) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math97
### Patch Diff Hash-SHA-256:

d3c4b915868c60d21617557636950195af58d1955f782e373425e4887972b733

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(relativeAccuracy)) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math97
### Patch Diff Hash-SHA-256:

b95cc6be7ed4c521b4e5c64799355b3028b6a3681bc4e7cc1a1547dbb114d6ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((functionValueAccuracy) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math97
### Patch Diff Hash-SHA-256:

83b5a5415f17fe5a80e534957303df2e53657a3849415f11a76a549b0cf471d4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((result) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math97
### Patch Diff Hash-SHA-256:

2a3d24e7a87b6fb22b4c83c619f0a3d13eaa093507869e69505c35dd21bd7847

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((absoluteAccuracy) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math97
### Patch Diff Hash-SHA-256:

ddc3d476e12856807dfe9f3f59da17da8db16792554fbc88759c47ca6674843f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((relativeAccuracy) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math97
### Patch Diff Hash-SHA-256:

fefcfe1213e3ec10cef582529b4d1a0a87b5ea18512cb60a5abcb7efc42066d3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((defaultAbsoluteAccuracy) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math97
### Patch Diff Hash-SHA-256:

e2e5a6152567c7e4ecc04e1ae237b6901bfeec89d0f2d51a71ebddebdc14d746

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((defaultRelativeAccuracy) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math97
### Patch Diff Hash-SHA-256:

a178e3e2c349bf77dc1d73cb089ca3ea2fa3c70384f2d0a6d093daafa7e7ad8a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((defaultFunctionValueAccuracy) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math97
### Patch Diff Hash-SHA-256:

630fc18bad09d28da10b7cd844ceddce0da5014167cfe7f9c6a9f40f56e5601f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(defaultAbsoluteAccuracy)) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math97
### Patch Diff Hash-SHA-256:

44df81d34231b93ee1668cdab1252b0c94df520289976c2b208c358722f27369

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(defaultRelativeAccuracy)) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math97
### Patch Diff Hash-SHA-256:

4d52b1546d61665824087c9b55daf9f80845171bd09e57eda659733eecc258b1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((java.lang.Math.abs(defaultFunctionValueAccuracy)) < sign) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math97
### Patch Diff Hash-SHA-256:

fe2d12cad73a757bd2a403e4dfa940bf04cc1252c1cc308998430357cf8d7310

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (functionValueAccuracy)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math97
### Patch Diff Hash-SHA-256:

a70ac821441e610fe04749c3484f7e25354ea09f92483a6d3cadc49479557945

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (result)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math97
### Patch Diff Hash-SHA-256:

c43010b4e2b8b9c9fe81f69607497839a2aad88ef847ea94f92693211ab01fce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (absoluteAccuracy)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math97
### Patch Diff Hash-SHA-256:

fd479fa88a4a21f57e539706938c158e59e4523fd857050fb7887344cedb3568

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (relativeAccuracy)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math97
### Patch Diff Hash-SHA-256:

1b5e2760295810dfb9bb76267dd173b5249f21661f75191b1baaed914da52bd9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (defaultAbsoluteAccuracy)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math97
### Patch Diff Hash-SHA-256:

af90b224df000823073c1f5f33af41de25ab06118204bcce6c0605e9516fdb5d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (defaultRelativeAccuracy)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math97
### Patch Diff Hash-SHA-256:

2dee6495457e2d2c135bd0e18e8e15dd2db7ae730af2c2e76cd56132218e5152

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (defaultFunctionValueAccuracy)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math97
### Patch Diff Hash-SHA-256:

7fcce02c23060a5ed0a398035c4d628d662cfb4769b3577679c738b20c284b49

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (isSequence(functionValueAccuracy, yMin, yMax)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math97
### Patch Diff Hash-SHA-256:

f84c3f2897c03a2be728c4db387086865dded075822d1f64dd048928498818b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (isSequence(result, yMin, yMax)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math97
### Patch Diff Hash-SHA-256:

2e7d53f9f76b93cf0d61bdf902be0d285b8723d9165b99ad3ccbea300ad1db35

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (isSequence(absoluteAccuracy, yMin, yMax)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math97
### Patch Diff Hash-SHA-256:

2ec86c22b1dfeffad12a5d36cc65a7a4f47d96f2ac09e52c6ff14345260ca961

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (isSequence(relativeAccuracy, yMin, yMax)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math97
### Patch Diff Hash-SHA-256:

864670246d46649ec70d915031fc5e3bb791ac599875d5cc6f173ffe22b20613

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -44,7 +44,7 @@
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
 		double yMax = f.value(max);
-		double sign = yMin * yMax;
+		double sign = ((1.5 * yMin) * yMax) - (java.lang.Math.abs(((result) * yMax)));
 		if (sign >= 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math97
### Patch Diff Hash-SHA-256:

cf89073eb1471562f1531da893e266ad374d2574eacffc8ca69dfe92f8b7594f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < (relativeAccuracy)) && ((relativeAccuracy) < sign)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math97
### Patch Diff Hash-SHA-256:

20eaec2d4e4199b6d617564ec6837c684cbacd92072bb637a3535ee8fc4b80ca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < (absoluteAccuracy)) && ((absoluteAccuracy) < sign)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math97
### Patch Diff Hash-SHA-256:

60fe59e03b14de53b22ef297b96a6a9d1909aa45455a4b141724f78613214050

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -44,7 +44,7 @@
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
 		double yMax = f.value(max);
-		double sign = yMin * yMax;
+		double sign = ((1.5 * yMax) * yMin) - (java.lang.Math.abs(((result) * yMin)));
 		if (sign >= 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math97
### Patch Diff Hash-SHA-256:

3a362ea7126b06313ef95cb81fa47235f865aa843bb032c4e46d98cf01d5a950

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < (functionValueAccuracy)) && ((functionValueAccuracy) < sign)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math97
### Patch Diff Hash-SHA-256:

62b2fc83866ffc834d98bd43b7f5c2294eec139d8aef387a8a76295d087aaaf4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < sign) && (sign < max)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math97
### Patch Diff Hash-SHA-256:

4d8f629328e0a31f3f93641dff7d2e0c6197a1626d1eff558299a0ce0f14156b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < sign) && (sign < min)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math97
### Patch Diff Hash-SHA-256:

e6f432b6719fb25e3c924a9ca50df51b8ca3b178765cccdcca501033e56138ea

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < sign) && (sign < yMin)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math97
### Patch Diff Hash-SHA-256:

cfde7bad974482646cd60c453417ae9b32a6024e52dab36d2b9e2f2e591d9f36

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < sign) && (sign < yMax)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math97
### Patch Diff Hash-SHA-256:

5fb52e14da348b1ec4b78f4c85c6d5768da39fb5c4c96a4c669cf6c6563284cb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (result)) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math97
### Patch Diff Hash-SHA-256:

f218a0b828effb441cf785b03dd413042982c47eb3899753c7e30c8ae5e2e7fb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * max) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math97
### Patch Diff Hash-SHA-256:

4314d693584a7512a64f507dccaa789fcecbb753bac9ead7ab128fd3a87b258e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * min) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math97
### Patch Diff Hash-SHA-256:

15a5e041d56adadecc0bd5b99aa31f1b2f0754adce9c09f42c6f5b04c06a7b70

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (relativeAccuracy)) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math97
### Patch Diff Hash-SHA-256:

b8ba9dc23328a3c830cb1d3679ee6e5e482ad0022a868bab36401693fd6903fd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (absoluteAccuracy)) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math97
### Patch Diff Hash-SHA-256:

b4da0baf678236ee5cb98f6c95c2fcd3d169a88310c172208a745d67f4ae8a02

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((result) < yMin) && (yMin < yMax)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math97
### Patch Diff Hash-SHA-256:

42126b8ad815731b86a8ff94a458b5629de4f9fd914e81be03ded57533042e9d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (functionValueAccuracy)) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math97
### Patch Diff Hash-SHA-256:

9703bb370144babac642aa0c36b99c79e93294f66a4edce02ff2329ae4db8366

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * sign) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math97
### Patch Diff Hash-SHA-256:

c12938bc19221a5e794650372f3ccafe644036b374b1dd3a1df167048d66e4dd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * yMin) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math97
### Patch Diff Hash-SHA-256:

01db50fe909dea435756f149c95fc6c2f6e60aed4ed842f26f2aa1697aaffeac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * yMax) * (result))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math97
### Patch Diff Hash-SHA-256:

1fd673ae9db9d8f7b6183b864c9700d670ade2e30c5c1d02e54513098e7a794b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((((result) - max) * (sign - (result))) < 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math97
### Patch Diff Hash-SHA-256:

a7d475a36b160128b8815cb8d67ec5c0881c6065b3daf429632f633af58b8081

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((((relativeAccuracy) - max) * (sign - (relativeAccuracy))) < 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math97
### Patch Diff Hash-SHA-256:

4750abc07f1a2bd9e15946271b991b07f6cdd89ad4e3819b4a63dd9fdc2390d6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((((absoluteAccuracy) - max) * (sign - (absoluteAccuracy))) < 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math97
### Patch Diff Hash-SHA-256:

dc99d9462d554c1dea3b598ad7c9440870f9ca3d6beb898d3b23ebf82720d710

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if ((((functionValueAccuracy) - max) * (sign - (functionValueAccuracy))) < 0) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math97
### Patch Diff Hash-SHA-256:

1b22bb0bab38430c9f4c24b6a89378501f32ee077ebf9db285e502d9fd00baf5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (result)) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math97
### Patch Diff Hash-SHA-256:

dbb6f86692ca7f4e7247f50e0d2446401667ad8756e26ddc5d4a24d581bc8030

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * min) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math97
### Patch Diff Hash-SHA-256:

ee04698d5226f1e16f9a2583f5e66a00e9f7933d60b7c841c6d62c8d586ec155

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (relativeAccuracy)) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math97
### Patch Diff Hash-SHA-256:

016700c1cda77ddf82ad240524a2b6b1c6530c117f7ec328ae37f4cec76bd2f2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (absoluteAccuracy)) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math97
### Patch Diff Hash-SHA-256:

26bcba248554b262fc941ec616ef2d1c08cf4eba6b6c28d0f30df2e919d547dd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (functionValueAccuracy)) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math97
### Patch Diff Hash-SHA-256:

c2c61cbad8729bad03ca8394e4614062a6950466a0375218bfb9a25c86e822a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * sign) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math97
### Patch Diff Hash-SHA-256:

09d4948cede5a9c9049c149b3dda1b0ece701efc160658229b56f8fa6fb8fb00

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * yMin) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math97
### Patch Diff Hash-SHA-256:

a3d8d734bf7ea02c277560b3cf5133a4591ac929d67affca29edd72d0c345fbd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * yMax) * max)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math97
### Patch Diff Hash-SHA-256:

e6f3dca539617a30c9ab0168f90a13914c283d3afddc5aabe4010c2ce59b076c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (result)) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math97
### Patch Diff Hash-SHA-256:

a5e5a10f2b3f9342f6019af7a4e7f152d4847a08d823528dffff20348b21d7d2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * max) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math97
### Patch Diff Hash-SHA-256:

c9fa6646ab0690f80099b9d3f8e585231f69e850335f648884559f0007247eec

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * min) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math97
### Patch Diff Hash-SHA-256:

81e84ead74d43c175808cb92c48c4db2359a7563eae9542eb0a57d48bc960b60

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (relativeAccuracy)) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math97
### Patch Diff Hash-SHA-256:

5cf082fea92b1ff18cea6e048322b97755b798bd49e32a249e383720c0e8adef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (absoluteAccuracy)) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math97
### Patch Diff Hash-SHA-256:

a9ddf3c0000f1c508b1c70adff1c6f6a4883d25d748b0cad2eae2ac79350c9b6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (functionValueAccuracy)) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math97
### Patch Diff Hash-SHA-256:

f76a69ef957d1967efc0f069d271cfca108575638c4c540e95f876e79c6564aa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * sign) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math97
### Patch Diff Hash-SHA-256:

b217c7e140eb31086835ad73c6e1c9c661dcd0adf4afe46c65064da81a92478e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * yMin) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math97
### Patch Diff Hash-SHA-256:

90d43e6829767a2bd9f0caa85128800fc2867fdaf553f4e8b5a85a7b5b5454ee

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * yMax) * min)))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math97
### Patch Diff Hash-SHA-256:

f3fce99ef448dad450b42b4a492e83c200ec1f2fdef135aafbb04749b6ade301

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((relativeAccuracy) < sign) && (sign < max)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math97
### Patch Diff Hash-SHA-256:

b3e16bdde0d9d30960bf281cda255a6505af48baad754309f0000a59566b6d55

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((absoluteAccuracy) < sign) && (sign < max)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math97
### Patch Diff Hash-SHA-256:

61904e6ef1ac8a203f862e1970d497c16efb04d334309f8eaecebc06050daeeb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((functionValueAccuracy) < sign) && (sign < max)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math97
### Patch Diff Hash-SHA-256:

e0149e048c3c83404537618f31ffa13c1c313f6f27dd7bca8daddfca6c74b4a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((relativeAccuracy) < sign) && (sign < min)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math97
### Patch Diff Hash-SHA-256:

9a6586698130ed4f8a9e0304c39657c082684e09676f0eeeccef92f4062ff3e0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((absoluteAccuracy) < sign) && (sign < min)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math97
### Patch Diff Hash-SHA-256:

b30b6f891eb939418ffb3b8b34ea99324d70a2d2bcc7dd304e53464a7264e0f8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * (result)) * (relativeAccuracy))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math97
### Patch Diff Hash-SHA-256:

25760eb13512591eadfec06b4c198589b000d9093706ef7af370da3e290883ec

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (((functionValueAccuracy) < sign) && (sign < min)) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math97
### Patch Diff Hash-SHA-256:

90cf46c9a0a1aa3e0ceb1bb7709f21b277f0fedc95d800c2961d881966b10bed

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -45,7 +45,7 @@
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
-		if (sign >= 0) {
+		if (sign >= (java.lang.Math.abs(((0.5 * max) * (relativeAccuracy))))) {
 			throw new java.lang.IllegalArgumentException((((((((((("Function values at endpoints do not have different signs." + "  Endpoints: [") + min) + ",") + max) + "]") + "  Values: [") + yMin) + ",") + yMax) + "]"));
 		}else {
 			ret = solve(min, yMin, max, yMax, min, yMin);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---