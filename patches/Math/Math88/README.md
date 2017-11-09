
# Patches of Math88 from Defects4J 
Total patches 5
## Patch 1 of bug id Math88
### Patch Diff Hash-SHA-256:

104464962ad6f0bc4ed0ad34e942f750a1d86cfde12b7af320ddde58e707caaa

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -35,7 +35,7 @@
 			double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(i, col), 0, epsilon)) >= 0) {
 				double ratio = rhs / (tableau.getEntry(i, col));
-				if (ratio < minRatio) {
+				if ((java.lang.Math.abs(ratio)) <= (java.lang.Math.abs(minRatio))) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math88
### Patch Diff Hash-SHA-256:

a75064ee330119e4fd42fc0407a54f8bd14db7dd5093aa6a77060bc4fb063c2c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -35,7 +35,7 @@
 			double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(i, col), 0, epsilon)) >= 0) {
 				double ratio = rhs / (tableau.getEntry(i, col));
-				if (ratio < minRatio) {
+				if ((ratio - minRatio) < minRatio) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math88
### Patch Diff Hash-SHA-256:

5e8d7850f38a72698dd13d4dcab4e4102ca380d3d87cd096fcbac065ee63f58e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -35,7 +35,7 @@
 			double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(i, col), 0, epsilon)) >= 0) {
 				double ratio = rhs / (tableau.getEntry(i, col));
-				if (ratio < minRatio) {
+				if (minRatio >= ratio) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math88
### Patch Diff Hash-SHA-256:

663c3ec7fad666d12f13d70cf1c435824716ae7b444bc7fd74ce8efb0f7598c3

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -35,7 +35,7 @@
 			double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(i, col), 0, epsilon)) >= 0) {
 				double ratio = rhs / (tableau.getEntry(i, col));
-				if (ratio < minRatio) {
+				if (ratio <= minRatio) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math88
### Patch Diff Hash-SHA-256:

770e8d6fc2a7f14dc83c26be7b667f03b5dc7d25e4ebe54a0008bd9b0151de7c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -35,7 +35,7 @@
 			double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(i, col), 0, epsilon)) >= 0) {
 				double ratio = rhs / (tableau.getEntry(i, col));
-				if (ratio < minRatio) {
+				if ((java.lang.Math.abs(ratio)) <= minRatio) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---