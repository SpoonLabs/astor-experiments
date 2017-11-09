
# Patches of Math28 from Defects4J 
Total patches 203
## Patch 1 of bug id Math28
### Patch Diff Hash-SHA-256:

bd016171a3277d536001b780ed67124e382996cffac34e8138c57c75de5e3896

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((epsilon) == (DEFAULT_EPSILON)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math28
### Patch Diff Hash-SHA-256:

4bed64ba6c5cee1fffcedd35dad38e4880337c075cf61a23b6902abfb046f29b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (tableau.isOptimal())) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math28
### Patch Diff Hash-SHA-256:

7f9c753144022f8f34422762a6d8f2d0628ad31cc55712ae7d02080a75696bfd

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((org.apache.commons.math3.util.Precision.compareTo(DEFAULT_EPSILON, 0.0, maxUlps)) > 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math28
### Patch Diff Hash-SHA-256:

ff7d748b432f6d3206c3e1f4e7bc95bdfebf9c2320f0a3d2ba54b251bf50717d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					org.apache.commons.math3.util.Precision.equals(entry, 0.0, maxUlps);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math28
### Patch Diff Hash-SHA-256:

d038406acd7f77ca0b6b757f96027d8a229167be957ffd3b3c69707c937c64a4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i < ((tableau.getWidth()) - 1)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math28
### Patch Diff Hash-SHA-256:

a808d77688d71cb3b9b79690541889270f05d0d6e3c0224a7f6e859c888af464

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (org.apache.commons.math3.util.Precision.compareTo(epsilon, 0.0, epsilon)) > 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math28
### Patch Diff Hash-SHA-256:

004909102899eaaff522bac2019117ec2cfe155996124ae5e423e26ecaad3fd9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (entry < (epsilon)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math28
### Patch Diff Hash-SHA-256:

d422901309714822e92ead518a93baab03081a2fc264c87a3438e360dde726a0

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i >= 0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math28
### Patch Diff Hash-SHA-256:

9591b776557f61d9f6bd7292a93acb41dc7ed3aecd50e28c2b1b2681817266c4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (col == col) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math28
### Patch Diff Hash-SHA-256:

070eba7ccf64bca990f7e64e341ba72fb21ebdc3d0e133d0e32fedbcc4fb0bf7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) >= 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math28
### Patch Diff Hash-SHA-256:

7b7858740fb288b67ccd31b03b2519bed4e8746b80df4ddc9cc8e759d979aaea

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((DEFAULT_ULPS) < ((tableau.getWidth()) - 1)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math28
### Patch Diff Hash-SHA-256:

9a556f9e5dd01e2dc71e84ad8f972e63a235cc7dcb3c43490c7d9f8228216f9e

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (minIndex > 0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math28
### Patch Diff Hash-SHA-256:

6f63a6b1b59b94aa21d306178e51d27c5d73d57a7d668c70635be8747ab93780

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (column == column) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math28
### Patch Diff Hash-SHA-256:

49344d47724989b44ddd3e02e6ddd75356f970ddbf5c5309cdc3c6cdad7f4101

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (minRow == null) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math28
### Patch Diff Hash-SHA-256:

03af1867fcefee8a5acba0cf8e7b60612e3a058eac1bb20e6ae07f932996e3a7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, epsilon)) < 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math28
### Patch Diff Hash-SHA-256:

5b2e91e0ceebac26e840525881d30567b48b179391b053cb30bd1056356a97c4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					tableau.isOptimal();
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math28
### Patch Diff Hash-SHA-256:

3f760ae1a03cbe0e677fe8da7c0063b4e8f7d1af1957eb7f59fc3ec97df878bb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((epsilon) != 0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math28
### Patch Diff Hash-SHA-256:

609cd3e80bc0d2eef71d78c5ba73dd4ec6530a718f1cbf6c17c8ed26ca19b393

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (maxUlps) < (-1); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math28
### Patch Diff Hash-SHA-256:

96eeb91b34182c1288593c32c2b34043b9c956fdc49be5e37d36b9b8e6e2b614

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (java.lang.Double.isInfinite(DEFAULT_EPSILON)) || (java.lang.Double.isInfinite(DEFAULT_EPSILON)); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math28
### Patch Diff Hash-SHA-256:

b81c102c2bc54d6d4dec231091b1a672c621852fe989a9639fe5e1cda7c43bcb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -24,7 +24,7 @@
 	private java.lang.Integer getPivotColumn(org.apache.commons.math3.optimization.linear.SimplexTableau tableau) {
 		double minValue = 0;
 		java.lang.Integer minPos = null;
-		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
+		for (int i = tableau.getNumObjectiveFunctions(); minValue == 0; i++) {
 			final double entry = tableau.getEntry(0, i);
 			if (entry < minValue) {
 				minValue = entry;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math28
### Patch Diff Hash-SHA-256:

50e09f0201d4ad2d93d54a7c58bd0c0eb06c89e8bf8cf1bce6c70dc6903a72cf

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (col != 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math28
### Patch Diff Hash-SHA-256:

2f532802e1818584265f3cfab8792d927b7c0084337d45b1843820d0279eec27

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (col < 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math28
### Patch Diff Hash-SHA-256:

61968848e33875dfb20dcf86660b9b220473960f32610bd020df26adfe8f2223

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.FastMath.abs((minRatio - entry))) > 1.0E-5) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math28
### Patch Diff Hash-SHA-256:

0db7eedfaeff22057f2b4ff0a03e8668ada9ccdb064de4cecfb700f1a1c11e65

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) > 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math28
### Patch Diff Hash-SHA-256:

4c3b0e8fbbf4f5aebb43d8ab5286dada31bae3f68d1d2f3fe86e8e18070d2770

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((DEFAULT_ULPS) >= 0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math28
### Patch Diff Hash-SHA-256:

db291205a692562804529cb8c895e5445e30a8b079ff07298aa6c21a1db0baa5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((DEFAULT_ULPS) == 30) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math28
### Patch Diff Hash-SHA-256:

32057c9bd92fa18b2a7806f810f824744e70a43dac6220b12a20a5c8c0c54137

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((minRatioPositions.size()) == 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math28
### Patch Diff Hash-SHA-256:

5032eb4440e707c9d767cffb8fa0b988cbb4f3993a28418e5e3094319eceec08

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (minIndex > (i / 2)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math28
### Patch Diff Hash-SHA-256:

4eb70457cbe1a53d0aa055ee943f4ba17561abe5f9f678e02ff620f9f3beebb6

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((DEFAULT_EPSILON) == 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math28
### Patch Diff Hash-SHA-256:

a756f1fd870fcdd95605ed233304dae7fd12b5c4a332041584905862fee6288b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((DEFAULT_ULPS) < 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math28
### Patch Diff Hash-SHA-256:

2a5a67ac234d80fd2c3648b71bc28932944543a4c765b725360d0e01419330ab

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((DEFAULT_EPSILON) > 0.0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math28
### Patch Diff Hash-SHA-256:

8867c35b6fc63ee352997101f3c6b1145c6122e50e59ad62961fb5541ad4cb2c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (((org.apache.commons.math3.util.FastMath.abs(((epsilon) - entry))) <= entry) || ((org.apache.commons.math3.util.FastMath.abs(epsilon)) <= entry)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math28
### Patch Diff Hash-SHA-256:

1eb48fd1b3b3f85629cb5004fb813b4f23e20604638c0606c4b5beaaf7ff50cb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) == (org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math28
### Patch Diff Hash-SHA-256:

980212b48bf429f51f2fee96099f39dfa81b596d333f7335855c8a94d74771d7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (entry > column) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math28
### Patch Diff Hash-SHA-256:

3a0d94abdb658d20748ed9a43b9bed2c1e7d9217213e529edadfe15bfce4e315

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) == 0) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math28
### Patch Diff Hash-SHA-256:

3edc3b66ed1e64114b2b91f30ae3cab0f3564084a76ec0bee525d7a7ce063bbd

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (entry > entry) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math28
### Patch Diff Hash-SHA-256:

0a8d8de9ae9c7f647338e343b22423600f20249f18c7472478c6aa22e87a3d79

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((DEFAULT_ULPS) >= 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math28
### Patch Diff Hash-SHA-256:

c3b351fcfccfe169b83c1b385d460763e397919ab1060ca5a07ab98a96220c9d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((col <= col) && (col > 0)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math28
### Patch Diff Hash-SHA-256:

44b5acb1f3ffb39810659731352d79069b5079a8472baad5af08334ce825b90d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; col == 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math28
### Patch Diff Hash-SHA-256:

a404c179b74a855f4d32b4b3681749c6411746f605a0648a2d6623afccd2ef2d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (true) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math28
### Patch Diff Hash-SHA-256:

0a11e5f1182cadbeac3c3874893c4e8746a93a4a7d84c6ebeaed9a1f5a935958

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (false) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math28
### Patch Diff Hash-SHA-256:

a1bc9cee54a1c8c849113396ec3367a6632e34888edcc4795411376e78aca2f1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (org.apache.commons.math3.util.Precision.equals(minRatio, 0.0, 1)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math28
### Patch Diff Hash-SHA-256:

e161c343c12c7a5e1ee5a765b5e0fa7bc0bc095493b499b4853f98e8262ea1df

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (true) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math28
### Patch Diff Hash-SHA-256:

f733066e3093170ecb647bf2b067c3bfaa17c9d6f7d69ec63d1d97490aa7fe3b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; minRatioPositions.isEmpty(); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math28
### Patch Diff Hash-SHA-256:

9164ffd04b00520ff0f39b35a30a6ac8981876c7e2a4c79535efd7874673d85f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((((DEFAULT_EPSILON) >= (epsilon)) && ((DEFAULT_EPSILON) <= (DEFAULT_EPSILON))) || (((DEFAULT_EPSILON) >= (DEFAULT_EPSILON)) && ((DEFAULT_EPSILON) <= (epsilon)))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math28
### Patch Diff Hash-SHA-256:

23e23f741508a700b6cc25b3e35ed2ee4095da26a0d19df5cf908899fcfe9d40

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((maxUlps) < (org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math28
### Patch Diff Hash-SHA-256:

acfaa59887a9c1341046f430c6b90d181463528527971c5d540af5ab5482738b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) == 1) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math28
### Patch Diff Hash-SHA-256:

fa2bdc3c7a29f3da48303ae6d68946838e92ba613bc3f424930201cec80246f5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (col <= 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math28
### Patch Diff Hash-SHA-256:

8040ec8dfeedb493a3344caf5e302035943735e0ab98fb07638f3511e3e3b0f3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((epsilon) < 0.1) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math28
### Patch Diff Hash-SHA-256:

d4fb9e262c959ec7c93d8751b3174426984b03b2d80593f215f845640ca6874d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if (rhs < 0) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math28
### Patch Diff Hash-SHA-256:

b4e668888ee33494ffdbb48deebcf2e6098760a763e796914ce5fc296870c78d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((maxUlps) != (-1)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math28
### Patch Diff Hash-SHA-256:

0fa0d57bb91ec3b4380c1880ba21eaf865c0029502ec057201c6b7263d4b1fc9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; col <= 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math28
### Patch Diff Hash-SHA-256:

c4c27828ce22d677209c379a34cee84d5e625fee4237c87dd14ac08b5a15b1b2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (true) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math28
### Patch Diff Hash-SHA-256:

11a0a322f6f9ac2e2c52aa421e35ce09b041d69fa8cd543118d79c4f08fd5d64

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((epsilon) < 1.0E-4) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math28
### Patch Diff Hash-SHA-256:

4ccaaa88dfe4268ae9349d7290c2b3d293886bd52965d583c746170e818f3a68

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					restrictToNonNegative();
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math28
### Patch Diff Hash-SHA-256:

f68a3f1702896be8dab4c7b3a3f56a11bcafb27652cf68347747bce5d70d5d62

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (column == 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math28
### Patch Diff Hash-SHA-256:

48cc96b9c86f96d72fcb3fdaae2c9b5c1cc528846919166871a6c39580edc523

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (col > (col / 2)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math28
### Patch Diff Hash-SHA-256:

94fa2b0114ff3df4835f92c99fd3f95c77c68423b3134bca04a8187a7467e173

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (!(minRatioPositions instanceof org.apache.commons.math3.analysis.polynomials.PolynomialFunction)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math28
### Patch Diff Hash-SHA-256:

6c8692fef5e2f4b088c86cf8f6a06240785e109f7056136508ff9a92dc5c04af

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if (false) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math28
### Patch Diff Hash-SHA-256:

173f6645ac44b3e0f153c3533d0309ec1875fb602658f05efbcc0e81b1a9f396

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (maxUlps) == 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math28
### Patch Diff Hash-SHA-256:

1a0799f140763e022b0dd0c78a8d72c2e50c534066b3018737d5fb6ccc31bfd2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -24,7 +24,7 @@
 	private java.lang.Integer getPivotColumn(org.apache.commons.math3.optimization.linear.SimplexTableau tableau) {
 		double minValue = 0;
 		java.lang.Integer minPos = null;
-		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
+		for (int i = tableau.getNumObjectiveFunctions(); minPos == null; i++) {
 			final double entry = tableau.getEntry(0, i);
 			if (entry < minValue) {
 				minValue = entry;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math28
### Patch Diff Hash-SHA-256:

ceb935575c1a12ccf420abbc1397159676845104b4d497b9b1e620bd7e253c47

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((minRatio > 0) || ((1 / minRatio) > 0)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math28
### Patch Diff Hash-SHA-256:

62a266c0775f9d6379b4cff9acb5f6ca8d1e51eaf22ef62f62dc465801370180

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.FastMath.abs(epsilon)) >= (org.apache.commons.math3.util.FastMath.abs(DEFAULT_EPSILON))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math28
### Patch Diff Hash-SHA-256:

e1e0d45c6227997f29d5d2499d9737570d296f51144af6d6715c1499c6b188ce

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((DEFAULT_EPSILON) > 1) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math28
### Patch Diff Hash-SHA-256:

1bf9d85d7ed828f3e8309662a1ee58fa839a8ebdd4d91af7d6761dffd31c52ff

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((DEFAULT_ULPS) < 0) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math28
### Patch Diff Hash-SHA-256:

1e00b996e7ca1b61004c41861c8f0da2827ca55d3130b01aa1cf1199c5f126d8

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((entry >= 0) && ((epsilon) <= 0)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math28
### Patch Diff Hash-SHA-256:

3b2db292879dd470c941c2ff561bd7022f000c83b451053233c7cb94f9321ef5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (col > (maxUlps)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math28
### Patch Diff Hash-SHA-256:

ddfd11825b235fcf3730f96657f0fa989b46478c7ad7cd65041d6592625dc696

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; minRatioPositions == null; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math28
### Patch Diff Hash-SHA-256:

c11d1dd22fbe0b894d5d8dc01d51d0c09cea81355a80dbb500ded99728540685

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (((maxUlps) & 1) == 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math28
### Patch Diff Hash-SHA-256:

512f0e5fb0f67ae1e24fefff4eb54bd2617bb2c181ad99ac94004c842a649fcc

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((java.lang.Double.isNaN(ratio)) && (java.lang.Double.isNaN(rhs))) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math28
### Patch Diff Hash-SHA-256:

bf93609b1f954884aa6e98e0b0d59eb64bb80214bad4bd0d58d848869b20dda6

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((minRatio * minRatio) < 1.0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math28
### Patch Diff Hash-SHA-256:

594723c79b5f8f0cc2651798de66f026d178a6808008f80a39617230621bbee3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((DEFAULT_EPSILON) > 0.0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math28
### Patch Diff Hash-SHA-256:

6f9be3bb08ae0ec5147996b3e2b412e2bbeabcec1f95bf54b90a09ee84a1fed1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) <= 0) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math28
### Patch Diff Hash-SHA-256:

cb9033a174e7e5b69e2aba7ff90852308e433475c87990b0b479d215b737593c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) > 709) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math28
### Patch Diff Hash-SHA-256:

f27c9d3268c585e146a27439e8c7e9db4fd5bf287d4b429c49909e54d27f307b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((DEFAULT_EPSILON) > ((DEFAULT_EPSILON) * (DEFAULT_EPSILON))) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math28
### Patch Diff Hash-SHA-256:

aa7c863826dd0ddc82ec4ae8cba51de2c6d96138a964205c3986619aeebd54ed

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (((epsilon) == 0.0) && ((DEFAULT_EPSILON) == 0.0)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math28
### Patch Diff Hash-SHA-256:

95d3726e330a61c8f592bc9e0871d9431b6f0c922c8fdd4c1af3b8686e12daf2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (((org.apache.commons.math3.util.FastMath.floor(DEFAULT_EPSILON)) / 2.0) == (org.apache.commons.math3.util.FastMath.floor(((java.lang.Math.floor(DEFAULT_EPSILON)) / 2.0)))) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math28
### Patch Diff Hash-SHA-256:

c971c55358649ed6ef9fb08ab3e1f105b16f2159b42258b2470b40aa8dba8b59

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((maxUlps) < 255) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math28
### Patch Diff Hash-SHA-256:

1940a169c92e89bf83dfb76105bb17bf0ebfdefde6db136ac78489a422cadae9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (minRatio > 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math28
### Patch Diff Hash-SHA-256:

ab895ee053f13a07567cde85cd302d73bdd7e518ff8b0614ebc8382d90c214d5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i < (minIndex - 3)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math28
### Patch Diff Hash-SHA-256:

8928846295090cca9363525977c18253a4dde66715677d826f039f3895b79074

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.equals(entry, 0.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math28
### Patch Diff Hash-SHA-256:

13510e4bae775ff1699fcca72930e68e3565c3bd142735f88e46f082f1e60b2f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) < (tableau.getHeight()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math28
### Patch Diff Hash-SHA-256:

5c1b6a130469c9591dd445f8f562d858c15740e7c7d5f54df86825a288a1d58f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i > 0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math28
### Patch Diff Hash-SHA-256:

f87bead7d63737eff5c6e5b64ec3ac079201dfce94613279b0b97dbc4150d278

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					org.apache.commons.math3.util.Precision.equals(tableau.getEntry(0, tableau.getRhsOffset()), 0.0, epsilon);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math28
### Patch Diff Hash-SHA-256:

e6f4b61ca9ec497317e94032dcba02b7d23f205705dafeacfdeff78085fc15f7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if (minRatioPositions instanceof org.apache.commons.math3.optimization.linear.LinearObjectiveFunction) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math28
### Patch Diff Hash-SHA-256:

313a94e80e0a2c4e4b5137be201e12ff4c4e519bae090e2e5e33df3076e848ed

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) < ((tableau.getWidth()) - 1)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math28
### Patch Diff Hash-SHA-256:

f85706eb99431520fdf6f965307640aba25866d95d9e2903e205c396d87abd54

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (column < (minRatioPositions.size())) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math28
### Patch Diff Hash-SHA-256:

39b52f21ced3313e8b1c78c7cbf4c34637ee9b3e25b2b9eb83e3890a6d044135

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (org.apache.commons.math3.util.Precision.compareTo(DEFAULT_EPSILON, 0.0, epsilon)) > 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math28
### Patch Diff Hash-SHA-256:

21a81404e1f2d2fad275ac0ae31cb9f0279af791dda4e447297d8338474a8e80

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((DEFAULT_ULPS) > 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math28
### Patch Diff Hash-SHA-256:

eb129f0d6f1a7c3f9a5097e1fd3f78d8fe6d2568e474ad5ef3aad167a58453b2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i == i) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math28
### Patch Diff Hash-SHA-256:

fbd88cb00e46d8ced896b748018f1b8ed96f9265e2480f27224560028ef521c1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math28
### Patch Diff Hash-SHA-256:

20aefbe36bdb7061f7a4a37eefc1ab8cdedec18b1d4415bc0f6afe162fbfd6e9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (minRatio < (DEFAULT_EPSILON)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math28
### Patch Diff Hash-SHA-256:

3480ff44207042399d9d228e8d98c8c2549c6f269267287cf9c932ea8058d5f3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, epsilon)) > 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math28
### Patch Diff Hash-SHA-256:

23e9ab641f7d0a50f92075edf90d35dc213c2d5c2a97a4e4364c1691b03f1b17

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (DEFAULT_ULPS) < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math28
### Patch Diff Hash-SHA-256:

1b503eba9c4dfc896adbe369f6ed9750b9f86570f0e8db5ecc4dfb98fcdeb1af

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (minRow == null) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math28
### Patch Diff Hash-SHA-256:

3d39ee523b1cf55b31bd79591ca3b9b4033524d990d17073bc0d6bfea6d82e5d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((epsilon) == entry) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math28
### Patch Diff Hash-SHA-256:

ee4a2d42eb0d63e2e0b08e8b32ca3c3728f67ccc07bf9e0f9f8d4ffa6f4a0286

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((maxUlps) == (maxUlps)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math28
### Patch Diff Hash-SHA-256:

bd0a84485c7a89f71c5e3477e76e05e5734c74a1bef2a90db5a87ed547392c97

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) < ((tableau.getWidth()) - 1); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math28
### Patch Diff Hash-SHA-256:

1b8a4e19ec44b6bb833cf0f43e7aa5507febefd00e49074502449d2877d3b064

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((minRatioPositions.size()) == 0) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math28
### Patch Diff Hash-SHA-256:

afe35e13b9698f01b616942561cb45b13733b174f7cd872e4947e7f1dc3c067a

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (java.lang.Double.isNaN(epsilon)) || (java.lang.Double.isNaN(epsilon)); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math28
### Patch Diff Hash-SHA-256:

86a19fc208d8e86d097f4236f4f668cd7e1ebe97bf8e49bd96c5f1cf540d7bc8

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((maxUlps) < (maxUlps)) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math28
### Patch Diff Hash-SHA-256:

f7c2ac98f793e91a5ef79ea66bfdc4d9b8eb9b038fac1558decef17e7f5f8910

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((epsilon) < (-20.0)) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math28
### Patch Diff Hash-SHA-256:

d5651be7f8bb48b436520a4a4e7113e7e7e6693dd636bd61ddae8ba0937785fe

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (epsilon) > 1.0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math28
### Patch Diff Hash-SHA-256:

01f19d58d74aa742b15d819fdbeeaca3f594aa6229ab9fa18024b257b05a2c2b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) > (-1023)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math28
### Patch Diff Hash-SHA-256:

b46eb67bfa887b78c8170e50fdc17b7de06a780118a08ed1aadf78e0c9ab62c2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (tableau instanceof java.io.Serializable) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math28
### Patch Diff Hash-SHA-256:

eab9e2f3615c283621d2c4a1a5577258f329e5d8c32c883de025863ea264cd88

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (maxUlps) < (maxUlps); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math28
### Patch Diff Hash-SHA-256:

36a68a47f6df55bf9bdf5ca7fbe5c5c4c8e25527e76540360af8e00df5e1df8f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((epsilon) != 0.0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math28
### Patch Diff Hash-SHA-256:

bb5bc2fee916c86d355427f0ef11f31d2eb6624347caa87a3483d695be038abb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (epsilon) <= 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math28
### Patch Diff Hash-SHA-256:

7336a9440e7dbf79b2d547b941ec40b59b07218ab3ee7dce8401485001dc51e8

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (minRatioPositions.size()) < 2; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Math28
### Patch Diff Hash-SHA-256:

c1412d9c6e6feb4a2259e79d7349fec377103160d261104c56780633349c94fe

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (java.lang.Double.isInfinite(epsilon)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Math28
### Patch Diff Hash-SHA-256:

37d87bbdacd9657aa8897d2d9ca4e05594ab5bd64c4a80f94568f5d9f2447c4c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i >= 1) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Math28
### Patch Diff Hash-SHA-256:

1b2b9b52c9ce8fd47099a2135c84d3b610ecd9ae5937bff9bdaffc5d44d74752

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) < (maxUlps)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Math28
### Patch Diff Hash-SHA-256:

b32b7ddf77d2d3ed2c0cfbb45c37d9e7c8110d13d27f0c452b2468efbf27dd09

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (i < (maxUlps)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Math28
### Patch Diff Hash-SHA-256:

87eb75279b5f27d540b5f5e01f963305bbd89a99910d1c8df34da5daf0be11d7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((epsilon) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Math28
### Patch Diff Hash-SHA-256:

1df4b0068ed41eb3b295a901643c617c2af671e30094c6ff2b0391a38f1a7a13

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) < (-1)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Math28
### Patch Diff Hash-SHA-256:

7523ef3e67998caba61af7c6892f76ade2df88915bcbbbf6a032917f9c96f811

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((epsilon) <= (epsilon)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Math28
### Patch Diff Hash-SHA-256:

962864f15b00eababcb3baf77d642feb25a9e63da9700bbbf32a2cab9c91742d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((i > (-127)) && (i < 128)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Math28
### Patch Diff Hash-SHA-256:

1424c654ac81f9d18c14ee014238d8156e08b3874ad8ece86746bbd9fd779ad0

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((epsilon) > 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Math28
### Patch Diff Hash-SHA-256:

b5eab4d9ab385b9f1d9a385d3317c16f666ae32ef1f9cc0d163f6bd885f77810

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (i > 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Math28
### Patch Diff Hash-SHA-256:

bfbff9c946bb5a75d4dea84d0519630cb0eab786d4dae49cb041316d81ff97db

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i <= i) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Math28
### Patch Diff Hash-SHA-256:

87ade288a20fa819ed4b95d4101558522dbc0c84d2d02a0f0592a1469c2191af

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((minRatioPositions.size()) < i) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Math28
### Patch Diff Hash-SHA-256:

79adcace3c25c7cb5419ae7ca115cb84e021a85cf52c4d6f23a5981d8960d791

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (epsilon) == 0.0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Math28
### Patch Diff Hash-SHA-256:

7e44150d519e3a2e49c608bcb5d4e00710d577f3b1ecbd70d58398043419535d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (i <= i) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Math28
### Patch Diff Hash-SHA-256:

449777eb3ea397489224a6107e41727d87a476bd73cbfe3c7569cb0ecd40b871

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) < 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Math28
### Patch Diff Hash-SHA-256:

8b0d9c3d67195a5c28d670e1ca12267c25cc5bda057813eea05ac1a52fc75709

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((epsilon) > (epsilon)) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Math28
### Patch Diff Hash-SHA-256:

3afba50d2c9dc441182e4cdd161d6db62c875a9240a605e5ee0b8b3ec354ea1a

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) == (-1023)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Math28
### Patch Diff Hash-SHA-256:

0ff24ddc90e6697a659e68eb9709c6a994974bafa9ef92a26946d4ed8f011ac2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (java.lang.Double.isNaN(epsilon)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Math28
### Patch Diff Hash-SHA-256:

56b5cd5a907491169d6adda85dc8c5bb2d7841a9e71782ef4157ea7dcbd6bf7b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					minRatioPositions.equals(minRatioPositions);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Math28
### Patch Diff Hash-SHA-256:

d6fe378022d9f56bcf60edfd06078875b0fa5558d111a9451d316f48de626dbb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((maxUlps) != (maxUlps)) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Math28
### Patch Diff Hash-SHA-256:

348e0f52d9467647b90ae95672452ef7920d31f74e6cbee043b4a396e5488268

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i != (i - 1)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Math28
### Patch Diff Hash-SHA-256:

1bb339f31826f66a32156babc8c3f6ab637d94117416671e481fb6e40a11b1df

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; java.lang.Double.isNaN(epsilon); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Math28
### Patch Diff Hash-SHA-256:

9520f8db70c3d81ab8c59497a15c8e7018a0158facd46277b5d74a376f54c7c2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (((epsilon) < 1.0E-4) || ((epsilon) > 0.9999)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Math28
### Patch Diff Hash-SHA-256:

6c2439f4a20e048a27776f4071abd7babf34fcfd64fce13278d4d569078aec8d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((org.apache.commons.math3.util.FastMath.abs(epsilon)) < 1.0E-20) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Math28
### Patch Diff Hash-SHA-256:

1f4620497f0e1895c6cfd5ca202139d4f0f5e3e29033fc88fb1e6f07956fbce9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((epsilon) >= 1) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Math28
### Patch Diff Hash-SHA-256:

902dfa18e2097c9abe06e26f57c344e5c414a21da556c1971643b8fc38cf2c78

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (epsilon) < (epsilon); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Math28
### Patch Diff Hash-SHA-256:

68008ffa4b47819e7c56ba7a03010b43d5d14235381321eac88627cc8384713c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (((epsilon) - 1) != 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Math28
### Patch Diff Hash-SHA-256:

d2e83a9c7b8b5c058735991bd6615bbff8d6cd0b75542aa661d86dbac6c5832c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) <= (maxUlps)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Math28
### Patch Diff Hash-SHA-256:

d9901dab29404dc705793a08a2eb0a2f8c3c506f6d598b5e387bf75d0eba2a9f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (epsilon) > 0.5; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Math28
### Patch Diff Hash-SHA-256:

a0fb19edb00f9ef40ba9e631dca456944c47f74c63e45d153feb42211a8760cb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (maxUlps) != (maxUlps); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Math28
### Patch Diff Hash-SHA-256:

3b8e1dfdffd9c00fe54843cbbb100eae4f24b3e739d02b161b305555a53afe5b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (i >= i) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Math28
### Patch Diff Hash-SHA-256:

606b258222840dda67411936f56c2449dc1718e3f8b7283ff1bb1c4938c66531

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.equals(tableau.getEntry(0, tableau.getRhsOffset()), 0.0, epsilon)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Math28
### Patch Diff Hash-SHA-256:

a910dd867749d945bc692012925c5130af526b7ad63cbb7a24a899270710a3ac

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((java.lang.Double.isInfinite(epsilon)) || (java.lang.Double.isNaN(epsilon))) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Math28
### Patch Diff Hash-SHA-256:

c8b6b77b2c5a92d362b967d99cb6f6dda088313c8333a6a96eaf0e4d0d1891a7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((org.apache.commons.math3.util.FastMath.abs(epsilon)) <= (epsilon)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Math28
### Patch Diff Hash-SHA-256:

6dd91174ca9fbe4533bc615e16ec58bb928784910072ae1e5b3adca2614f4990

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((org.apache.commons.math3.util.FastMath.log(epsilon)) < ((0.5 * (epsilon)) + ((epsilon) * ((1 - (epsilon)) + (org.apache.commons.math3.util.FastMath.log(epsilon)))))) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Math28
### Patch Diff Hash-SHA-256:

3d678015e00b8262f654069165c8fc5697a7993bf92f000a139b71a9d6ecb7fd

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) == 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Math28
### Patch Diff Hash-SHA-256:

ad6c9637260bf60bafbfa1e6a242b9c97979d89e5d849e9b797ba8d0166dec65

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if (((maxUlps) < 0) || ((maxUlps) == (java.lang.Integer.MAX_VALUE))) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Math28
### Patch Diff Hash-SHA-256:

b94f01483e8a55d7f8119ecece3fb3074941bc5d500f1e99c204a99a8f212240

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((epsilon) <= 0.25) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Math28
### Patch Diff Hash-SHA-256:

3a3c7b175ac0da90be4bb31b554185eb46ec6b2424cbe45b33228264f0dd9df2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (epsilon) < 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Math28
### Patch Diff Hash-SHA-256:

3823a6cd40e10764cfbc56bb4e1b68c44521d3c3856945621d5f1572a0361d36

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) < 1) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Math28
### Patch Diff Hash-SHA-256:

3315adb5bc6cff1b7b53be63ea6221a6fe6e1e259d172a571217d8a8390643d3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if ((epsilon) < 0) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Math28
### Patch Diff Hash-SHA-256:

6bc949069979ec726323b42e03528ade30f231abcf2a821016efb69efe5050fa

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if (((epsilon) < 1.0E-4) || ((epsilon) > 0.9999)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Math28
### Patch Diff Hash-SHA-256:

86d2d3c6472656f6ecde72e96657da36bab9858ec40d8aad6c7eeac7a8a97f11

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((org.apache.commons.math3.util.FastMath.abs(((epsilon) - (epsilon)))) <= (epsilon)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Math28
### Patch Diff Hash-SHA-256:

79852018703aa6d117e88b822e7b11971e45851a09a4adad7f8a3143739050a9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) == (-1)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Math28
### Patch Diff Hash-SHA-256:

f59f3b19cabea3af148c2ff1a716629bd44a162d217133f5884f70674248593d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (maxUlps) < 0; i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Math28
### Patch Diff Hash-SHA-256:

0fb5bf6d304956a33483ffd1e68a6a4d6c9086e408f8a2d83806752dde5dac1b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((org.apache.commons.math3.util.FastMath.abs(((epsilon) - (epsilon)))) > (epsilon)) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Math28
### Patch Diff Hash-SHA-256:

46cf55da4576ebad81f80fa3711edd3a4b29c7e64569d8f86a801586a2262c1f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (i < (tableau.getHeight())) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Math28
### Patch Diff Hash-SHA-256:

72b8581c4c13708a04078f4200d842e1015306eb19f3aafeb729cbc136073ec3

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Math28
### Patch Diff Hash-SHA-256:

1f97975b40a6d3e2f14a6b9a68bf45ac5895d43fa79b0094c7a0f75e107464b1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -71,7 +71,7 @@
 				int minIndex = tableau.getWidth();
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
-					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
+					for (; minRow == null; i++) {
 						if (row == (tableau.getBasicRow(i))) {
 							if (i < minIndex) {
 								minIndex = i;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Math28
### Patch Diff Hash-SHA-256:

8e9a1279b97b76a79d3b728435248dd556d2c64b83a7a532dcda070c8b923903

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if (minRatio < minRatio) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Math28
### Patch Diff Hash-SHA-256:

6164dd28528a8ba2dcdb3275f482a8d7c239be85a00254f581623bb5623c2256

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -26,7 +26,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			final double entry = tableau.getEntry(0, i);
-			if (entry < minValue) {
+			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, epsilon)) < 0) {
 				minValue = entry;
 				minPos = i;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Math28
### Patch Diff Hash-SHA-256:

94558946fe9621e6d5e1bbb327e377335e0ef7be609f18a4ffe4414555befe5c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) == (org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS)) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Math28
### Patch Diff Hash-SHA-256:

69244cde57f3cef71f4f5210efbe0d04c715a94654e59a69e7452986849328eb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((minRatioPositions.size()) > 1) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Math28
### Patch Diff Hash-SHA-256:

02bc7b08f909c2aa36bf6b60dc82544185e61c4193f48cf178c0063bdd5d1b1a

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -71,7 +71,7 @@
 				int minIndex = tableau.getWidth();
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
-					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
+					for (; (i < ((tableau.getWidth()) - 1)) && ((2 * (i + 1)) != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
 							if (i < minIndex) {
 								minIndex = i;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Math28
### Patch Diff Hash-SHA-256:

04b03c9f860118cd0567e64c560b6fbbfd6544b5743cd758591808d3c86f30d0

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.equals(entry, 7.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Math28
### Patch Diff Hash-SHA-256:

4f6b2fc324f8c641df032f9d12cac94fd79d48c13643203e8953e17bec83064e

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if (((epsilon) * (epsilon)) == 0) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Math28
### Patch Diff Hash-SHA-256:

f166905e39f23da140bcdfa5270e623f36987f0b5eb7ccad73acd1df68e14ef1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -61,7 +61,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
+						final double entry = org.apache.commons.math3.util.FastMath.abs(epsilon);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Math28
### Patch Diff Hash-SHA-256:

bb0c95b20305d1c36d0d129f11ffe83c897da32a2362b1eacd31cb62fec3a118

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if (cmp == 1.0E-10) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Math28
### Patch Diff Hash-SHA-256:

a586b4cb10d915461c4ab23b59f7df5cb1dbb222ca3099278800f01431b1cf82

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -74,7 +74,7 @@
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
 							if (i < minIndex) {
-								minIndex = i;
+								i = i;
 								minRow = row;
 							}
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Math28
### Patch Diff Hash-SHA-256:

379e4b480be19f50118aa996476fb5984f4bfa6ce9d571cda25fd2399a201185

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -61,7 +61,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
+						final double entry = tableau.getEntry(0, tableau.getRhsOffset());
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Math28
### Patch Diff Hash-SHA-256:

dc8592207ace5b07160bbd4fcaba811d9ebd3387bb5c5a99ee78f192845a7ae4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if (cmp == (+0.5701626539230347)) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Math28
### Patch Diff Hash-SHA-256:

0879b8ae92a03ec8666ed691631d2219792e4cbf819107376823961afd33441e

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -61,7 +61,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
+						final double entry = org.apache.commons.math3.util.FastMath.abs(minRatio);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Math28
### Patch Diff Hash-SHA-256:

b4d20cf7f8401dcc5e6064612107586d1c4222964551d41856bb8393c9ded6da

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((minRatioPositions.size()) > 1) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Math28
### Patch Diff Hash-SHA-256:

d9f51c7ea4c5fc377bf3538631fa75afef57de738eca23b932e4e9c89750ad15

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (col == col) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Math28
### Patch Diff Hash-SHA-256:

4a3b57d4f5d5267d9b73db49e7d35cc1a1c2371bf5b09200aa342e0006875097

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((epsilon) == (epsilon)) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Math28
### Patch Diff Hash-SHA-256:

1f9f2fa2c31def15dd06acbf26a611ed8798affdd4f3ebb7c2db13e2769461d8

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (column < ((tableau.getWidth()) - 1)) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Math28
### Patch Diff Hash-SHA-256:

7f34cec85fb5f2a5d558d605b46fc2a43caeedc8099f09d5afc9423fc8938cf7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((org.apache.commons.math3.util.Precision.compareTo(epsilon, 0.0, maxUlps)) > 0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Math28
### Patch Diff Hash-SHA-256:

b025c8c48df6f712d5610aecf6559e4475968c006910d7a7e1a9c97d16c94e76

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; (maxUlps) < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Math28
### Patch Diff Hash-SHA-256:

f17d36c05a4c79a49c1e64ab70b3a9c526994ae81d8b83c95c63b044f4c15794

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,7 +60,7 @@
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
+						int column = i + (java.lang.Double.compare(epsilon, epsilon));
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Math28
### Patch Diff Hash-SHA-256:

ce3c52a87859cc97af996436171ae1bb41d5a83cbaefad26badc88b79e7246c2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,7 +60,7 @@
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
+						int column = i + (tableau.getHeight());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Math28
### Patch Diff Hash-SHA-256:

774d015d267b7f972994430ad289a4394ef656b2fee4a2ba8c3ccfdce11c4649

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (org.apache.commons.math3.util.Precision.equals(epsilon, 0.0, maxUlps))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Math28
### Patch Diff Hash-SHA-256:

366e50e265d1cfbd6583bb7b1d0a76df380eb789f235f23a35114a705e22516e

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.equals(epsilon, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Math28
### Patch Diff Hash-SHA-256:

173201c17a485b187d36141b19f36593aa2cec920f20a6cf07d669fce9e895db

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.equals(epsilon, 0.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Math28
### Patch Diff Hash-SHA-256:

0fcedeb23e16f5cd738112a035089378e67ea13d785eb360cbad776da4c82a95

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if (column < (tableau.getNumArtificialVariables())) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Math28
### Patch Diff Hash-SHA-256:

57e5448249dd77e8227ecda318323624868acb938487239a58023ba013fc3635

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((epsilon) < (epsilon)) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Math28
### Patch Diff Hash-SHA-256:

7dfc6bf2605cf8507f7a051e16e0a16a3a0839965b6938344eae01b70a111fc4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -71,7 +71,7 @@
 				int minIndex = tableau.getWidth();
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
-					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
+					for (; (minRow == null) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
 							if (i < minIndex) {
 								minIndex = i;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Math28
### Patch Diff Hash-SHA-256:

6657f58fd6abc4b7f5f43b15515a652cb8b9e53e81c121cbf4745a5184700ec7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,7 +59,7 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
+					for (int i = 0; i < (tableau.getNumObjectiveFunctions()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Math28
### Patch Diff Hash-SHA-256:

ca0cd731d52d9a13b9ba089e0115f1fbc5ff980617b3e6c1236a86adc79c7c3c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((org.apache.commons.math3.util.Precision.compareTo(epsilon, 0.0, maxUlps)) > 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Math28
### Patch Diff Hash-SHA-256:

6aac219e468643bb6c787763c17dfd5207c133d56a41462bbe1cd8edfef7ca8a

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if ((maxUlps) > 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Math28
### Patch Diff Hash-SHA-256:

fc89ed41677e7cc9ecf5a80d590b8363d38bf99d7e3401a622085d87e19fb541

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					org.apache.commons.math3.util.Precision.equals(tableau.getEntry(0, tableau.getRhsOffset()), 0.0, entry);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Math28
### Patch Diff Hash-SHA-256:

099cea4c2be97bb4ae8bb96b8f88787987e7a555ae5a49ec9a6f17aa88333cc5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((maxUlps) < (minRatioPositions.size())) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Math28
### Patch Diff Hash-SHA-256:

938b2f0e7d9db2762d16354671c33d432c3d63164a4523a018b6b2e6ca8f9034

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,7 +73,7 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
+							if ((maxUlps) > 0) {
 								minIndex = i;
 								minRow = row;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Math28
### Patch Diff Hash-SHA-256:

fc6f79d561429d1e4e12d15c66d6bf8c54beda7893b1cb17a230cb71a60d74b6

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((maxUlps) < (tableau.getNumArtificialVariables())) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Math28
### Patch Diff Hash-SHA-256:

40177904d66c02c5c1512177089ecb9c8b562d4683aaf0e44c476f9621ae9588

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					org.apache.commons.math3.util.Precision.equals(epsilon, 1.0, maxUlps);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Math28
### Patch Diff Hash-SHA-256:

d7bac1de50175cc37cf4778b5473b5b1de913f7163c93fe2d9df0d7660a5795f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) < (minRatioPositions.size())) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Math28
### Patch Diff Hash-SHA-256:

38609fbb47156fef7d2a7e861a7f8042eb80de33704e432a1d926a91be45a9e5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((org.apache.commons.math3.util.Precision.compareTo(epsilon, 0.0, epsilon)) > 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Math28
### Patch Diff Hash-SHA-256:

ec5c3662ff6e60630dfbd91fd0c29d1958f84f17cb875e428ddb7cbe95b5a8e9

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((tableau.getNumObjectiveFunctions()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Math28
### Patch Diff Hash-SHA-256:

612707feaed0a7a785b285855af1bce83206917affa5060671782c792cc86904

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -43,7 +43,7 @@
 			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
-				if (cmp == 0) {
+				if (col < (minRatioPositions.size())) {
 					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Math28
### Patch Diff Hash-SHA-256:

2efa9466a576451e6881dcc848f9a10c653bf4281540a2d31ca30771b71f063e

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((maxUlps) >= 0) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Math28
### Patch Diff Hash-SHA-256:

fdaa7fb65de680f63a8226c763a57008279edf118c341bf2d2481ba752be17b1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -61,7 +61,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
+						final double entry = tableau.getEntry(0, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Math28
### Patch Diff Hash-SHA-256:

b1a39b918f91756780079645c98d78365e7a911713d6b6943f49daa5bea0d0b1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					org.apache.commons.math3.util.Precision.equals(epsilon, 0.0, maxUlps);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Math28
### Patch Diff Hash-SHA-256:

154a15d687f7307df5298af6377c4d1b9ef9c73ee058bc5e3436cb3a6261bcb0

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,7 +57,7 @@
 		if ((minRatioPositions.size()) == 0) {
 			return null;
 		}else
-			if ((minRatioPositions.size()) > 1) {
+			if ((java.lang.Double.valueOf(epsilon).hashCode()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Math28
### Patch Diff Hash-SHA-256:

e91555efcac20a784976fff14b0fa6bed435a9eb403a64475e119d768c873b14

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -62,7 +62,7 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
+						if ((column < (tableau.getHeight())) && (row.equals(tableau.getBasicRow(column)))) {
 							return row;
 						}
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Math28
### Patch Diff Hash-SHA-256:

3ae70ae55c0dccc2269874bcb32a5ee36298536ea98f2ee75ec02f6ca83757c2

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -72,7 +72,7 @@
 				for (java.lang.Integer row : minRatioPositions) {
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
+						if (i >= 0) {
 							if (i < minIndex) {
 								minIndex = i;
 								minRow = row;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---