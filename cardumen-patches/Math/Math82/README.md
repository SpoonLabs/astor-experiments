
# Patches of Math82 from Defects4J 
Total patches 39
## Patch 1 of bug id Math82
### Patch Diff Hash-SHA-256:

3f2f1614b2765395c2f74b38ab133321d0aa53e6505e4609ef0074dbcd0747e6

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -36,7 +36,7 @@
 			final double entry = tableau.getEntry(i, col);
 			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
 				final double ratio = rhs / entry;
-				if (ratio < minRatio) {
+				if ((java.lang.Math.abs((minRatio - (epsilon)))) > ratio) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math82
### Patch Diff Hash-SHA-256:

5c80017593d85efd2ef4b2b239ed92d2848d87fc370de3499505e8bdd4c8eb36

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry > (DEFAULT_EPSILON)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math82
### Patch Diff Hash-SHA-256:

84d7b3888cfebeab88ed522db29508b9e93f66ed02b43bb2e3bd87e357b31e58

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -36,7 +36,7 @@
 			final double entry = tableau.getEntry(i, col);
 			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
 				final double ratio = rhs / entry;
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
## Patch 4 of bug id Math82
### Patch Diff Hash-SHA-256:

071c3e2d1fbef9bb728bbed63c4263930fe4e09da62d0c9a3dd6e39fc857170d

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry > 0) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math82
### Patch Diff Hash-SHA-256:

1cab5da1a62e59634fcef0c2cf1a333b743791831a01cadd1b032a2b7c5ffa4f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry >= (epsilon)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math82
### Patch Diff Hash-SHA-256:

e3af9b20d084a998faa8ac466325a3d635e6b64721476008ac4b7a8ef2409396

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((java.lang.Math.abs(((DEFAULT_EPSILON) - (epsilon)))) <= entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math82
### Patch Diff Hash-SHA-256:

56c6d0a519832fc2523165795c4fb9db2d0cfb4e6c262408ed0b4398603415de

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (((DEFAULT_EPSILON) * entry) > 0.0) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math82
### Patch Diff Hash-SHA-256:

95e69e1069fda56a4c4aa1ec6876834113582e2211f2410b98779e7bf8db7283

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (rhs < (minRatio * (entry - (DEFAULT_EPSILON)))) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math82
### Patch Diff Hash-SHA-256:

d87154b667d903b401af9a871d905750bc89e3028cfca7b18bd6075524e844c8

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry >= 0.0) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math82
### Patch Diff Hash-SHA-256:

d62a389720bc05206e4e90e1028ea3eea8d6834907de6b10a54295fdcd34fdd9

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((epsilon) < entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math82
### Patch Diff Hash-SHA-256:

a1b4bda1c8552627b6c19158c7635505bd923be4d527cdc9a337d8767976e442

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((java.lang.Math.abs(DEFAULT_EPSILON)) <= entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math82
### Patch Diff Hash-SHA-256:

4865d08f7237e4724a6765a6d4a270973cc32505cf9b1d260e19e53260c2e4d0

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry >= 0) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math82
### Patch Diff Hash-SHA-256:

4562649fba118699c426a7287cdf81f1de6274e990241f01a446e112a471d343

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry > 0.0) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math82
### Patch Diff Hash-SHA-256:

51f4b2c0ba81acb99027be4d960c785e01079fdb99e0ab8d464038bf651c4e6b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry > (epsilon)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math82
### Patch Diff Hash-SHA-256:

0593f11a4c80dba7c016b8023685542b82cec83e4bd403d7f923c0e9f4dae388

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((DEFAULT_EPSILON) <= entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math82
### Patch Diff Hash-SHA-256:

913079aef8bab75cf1fb8e77124d1cc89fc867b91875bd8ac73cf4748650807f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry > ((epsilon) * rhs)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math82
### Patch Diff Hash-SHA-256:

2873424472bf8ee1c9c918607011d5f9b0ab5f621eb39f35533aee626757002f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry >= 1.0E-4) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math82
### Patch Diff Hash-SHA-256:

3c34871d91cc92b21526dbf630c6c4a35186fb3cf916ae17cbf484976eb95bdb

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((DEFAULT_EPSILON) < entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math82
### Patch Diff Hash-SHA-256:

3ef63accdbc8e7703eb0c181876c06407cfe18042ab5c10bba77244e9909ec39

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry >= (4 * (epsilon))) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math82
### Patch Diff Hash-SHA-256:

a6fabe0b3691d992308236222ee73e244e0855c9a13358464e3fd2221dc5a668

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((entry * (DEFAULT_EPSILON)) > 0.0) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math82
### Patch Diff Hash-SHA-256:

cfa82336c2ba7cbe0a90822c64ac40e85ce92616454584fd5f7e1a7209ada036

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -36,7 +36,7 @@
 			final double entry = tableau.getEntry(i, col);
 			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
 				final double ratio = rhs / entry;
-				if (ratio < minRatio) {
+				if ((ratio * (minRatio - ratio)) >= 0) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math82
### Patch Diff Hash-SHA-256:

b6bc7dea45bd8c8268821ac881854e7d98bf4265a23546596c6a72b15687c9c5

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((DEFAULT_EPSILON) <= (0.1 * entry)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math82
### Patch Diff Hash-SHA-256:

ab7d4cdbb461bed300b5d9456ebcde9c36750f5b6a78e244fa4c1ce340fbe344

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((java.lang.Math.abs((entry - entry))) <= entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math82
### Patch Diff Hash-SHA-256:

11f3319103443b6fbf9493733cf8d5df6c9aa29a90760f994fd5c78e7e47463a

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -36,7 +36,7 @@
 			final double entry = tableau.getEntry(i, col);
 			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
 				final double ratio = rhs / entry;
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
## Patch 25 of bug id Math82
### Patch Diff Hash-SHA-256:

7cbe2c2292532f6134153220eac55718fca7e76477fe0696fcbda514ba48f7f5

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((java.lang.Math.abs(((epsilon) - (epsilon)))) <= entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math82
### Patch Diff Hash-SHA-256:

0c78187e1575c0bf264978857b9697dd340b8c44e2dd007f63a4fa49e30ca457

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((entry >= (-entry)) && (entry <= entry)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math82
### Patch Diff Hash-SHA-256:

2f09095a4fcd9123757609d2d68924ef8776308dd9f98a545ba6c0d37e539197

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((0.1 * entry) < entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math82
### Patch Diff Hash-SHA-256:

690afb1af4352533ea94be3000d54230be5bf8aa4890093f433569608d6dcd97

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((java.lang.Math.abs(entry)) <= entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math82
### Patch Diff Hash-SHA-256:

f6d4015c1e91cf1a9b7081e34a3911d2a475793b50c623570518ba5824c9cff4

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (((epsilon) >= (-entry)) && ((epsilon) <= entry)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math82
### Patch Diff Hash-SHA-256:

c7dbc5c9a557e892471dd6021de89b7d4e4cc9860e2eb859727c8fb27a7cff93

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((((org.apache.commons.math.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS) + 1) >= (org.apache.commons.math.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS)) && ((epsilon) <= entry)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math82
### Patch Diff Hash-SHA-256:

d58f7d851654106011fbfe14b03e807087967dcb5bca2ffb528bf2b76c1f0a68

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((epsilon) <= entry) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math82
### Patch Diff Hash-SHA-256:

6481d6a98776e0309cda2f7102b7d0094491e9ec2048b28d2f7a8367ef57b730

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (entry >= (-entry)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math82
### Patch Diff Hash-SHA-256:

cb9da44efc5af8ed7374ebd4557360c88e56ddc2f54f2a801e53d6d2c2488cee

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -36,7 +36,7 @@
 			final double entry = tableau.getEntry(i, col);
 			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
 				final double ratio = rhs / entry;
-				if (ratio < minRatio) {
+				if ((java.lang.Math.abs(ratio)) < (java.lang.Math.abs(minRatio))) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math82
### Patch Diff Hash-SHA-256:

9bd047caec5328d1e7f1e4d6484e4033ae08c33fd79f9972e92dcea051864f9c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -36,7 +36,7 @@
 			final double entry = tableau.getEntry(i, col);
 			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
 				final double ratio = rhs / entry;
-				if (ratio < minRatio) {
+				if ((java.lang.Math.abs(minRatio)) > ratio) {
 					minRatio = ratio;
 					minRatioPos = i;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math82
### Patch Diff Hash-SHA-256:

e8c1ee86cc417b5529a42e0dc485e553b2603b5fb6d656f8253b6f229e81a999

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if (((java.lang.Math.abs(entry)) <= entry) && (entry <= entry)) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math82
### Patch Diff Hash-SHA-256:

64b5c7e193e45074633a228dfd32168d11fb037b7321720a777ac0a7593b6ba6

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -36,7 +36,7 @@
 			final double entry = tableau.getEntry(i, col);
 			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
 				final double ratio = rhs / entry;
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
## Patch 37 of bug id Math82
### Patch Diff Hash-SHA-256:

3f4533ac861db6c60b949247e1616172d732cf412ad6f62fa7838786009fff86

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -21,7 +21,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minValue = minValue;
 				minPos = i;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math82
### Patch Diff Hash-SHA-256:

768530a23804c4c71041a30a7e2ae5f806e714feca19e8fba47079ee1fb74d8c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -21,7 +21,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minValue = (epsilon) - (epsilon);
 				minPos = i;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math82
### Patch Diff Hash-SHA-256:

bfc5fac9f0ed73429ba2e097ba55830b0e43e4ca88fbd1556c0b5207e4d805d9

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -34,7 +34,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < (tableau.getHeight()); i++) {
 			final double rhs = tableau.getEntry(i, ((tableau.getWidth()) - 1));
 			final double entry = tableau.getEntry(i, col);
-			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, epsilon)) >= 0) {
+			if ((org.apache.commons.math.util.MathUtils.compareTo(entry, 0, entry)) >= 0) {
 				final double ratio = rhs / entry;
 				if (ratio < minRatio) {
 					minRatio = ratio;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---