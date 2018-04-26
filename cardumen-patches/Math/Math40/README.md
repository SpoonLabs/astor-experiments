
# Patches of Math40 from Defects4J 
Total patches 12
## Patch 1 of bug id Math40
### Patch Diff Hash-SHA-256:

7976ff6f5033e2d4aa0df57160502da69084d8bcda71ae25c4f77520d2cedb71

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -128,7 +128,7 @@
 				java.lang.System.arraycopy(x, start, tmpX, start, (end - start));
 				nextX = guessX(targetY, tmpX, y, start, end);
 				if (!((nextX > xA) && (nextX < xB))) {
-					if ((signChangeIndex - start) >= (end - signChangeIndex)) {
+					if (2.0 >= (end - signChangeIndex)) {
 						++start;
 					}else {
 						--end;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math40
### Patch Diff Hash-SHA-256:

8e49644c4c1006b80d06cfcb6b7f7a914e0a59d103e2b0edca4b6648545a07e1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -131,7 +131,7 @@
 					if ((signChangeIndex - start) >= (end - signChangeIndex)) {
 						++start;
 					}else {
-						--end;
+						signChangeIndex++;
 					}
 					nextX = java.lang.Double.NaN;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math40
### Patch Diff Hash-SHA-256:

3c9e5370b500ec7e4f901b6b0e0531cac02061d2da9b097152da70f7b8a7e36f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -147,7 +147,7 @@
 			}
 			if ((nbPoints > 2) && ((end - start) != nbPoints)) {
 				nbPoints = end - start;
-				java.lang.System.arraycopy(x, start, x, 0, nbPoints);
+				java.lang.System.arraycopy(x, 1, x, 0, signChangeIndex);
 				java.lang.System.arraycopy(y, start, y, 0, nbPoints);
 				signChangeIndex -= start;
 			}else
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math40
### Patch Diff Hash-SHA-256:

c365042f42182b55703ed35654a3e4bcea80957e39013fbd17e200d694faf363

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -131,7 +131,7 @@
 					if ((signChangeIndex - start) >= (end - signChangeIndex)) {
 						++start;
 					}else {
-						--end;
+						++signChangeIndex;
 					}
 					nextX = java.lang.Double.NaN;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math40
### Patch Diff Hash-SHA-256:

8f771ad41c77c0654e8ba685903a48b3c2ef5020e5513a19bb2bc20b245bf0ca

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -190,7 +190,7 @@
 			}
 		}
 		double x0 = 0;
-		for (int j = end - 1; j >= start; --j) {
+		for (int j = (maximalOrder) - 1; j >= start; --j) {
 			x0 = (x[j]) + (x0 * (targetY - (y[j])));
 		}
 		return x0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math40
### Patch Diff Hash-SHA-256:

9d0dd7e4e5f4bd02326257d5538990c6108e0e9d4c42941db264948c5de9b976

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -128,7 +128,7 @@
 				java.lang.System.arraycopy(x, start, tmpX, start, (end - start));
 				nextX = guessX(targetY, tmpX, y, start, end);
 				if (!((nextX > xA) && (nextX < xB))) {
-					if ((signChangeIndex - start) >= (end - signChangeIndex)) {
+					if ((signChangeIndex - start) >= (((maximalOrder) + 1) - (maximalOrder))) {
 						++start;
 					}else {
 						--end;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math40
### Patch Diff Hash-SHA-256:

3464ca1959875d40b9e8bfaad6a5dd6aa718524db814d2127b150e5ef6e80fd2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -128,7 +128,7 @@
 				java.lang.System.arraycopy(x, start, tmpX, start, (end - start));
 				nextX = guessX(targetY, tmpX, y, start, end);
 				if (!((nextX > xA) && (nextX < xB))) {
-					if ((signChangeIndex - start) >= (end - signChangeIndex)) {
+					if ((signChangeIndex - start) >= ((signChangeIndex + 1) - signChangeIndex)) {
 						++start;
 					}else {
 						--end;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math40
### Patch Diff Hash-SHA-256:

4f2a2364cb5c4743ccfbf64dc7648761c5bd94f4b0856c8674b21211e1e9c674

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -147,7 +147,7 @@
 			}
 			if ((nbPoints > 2) && ((end - start) != nbPoints)) {
 				nbPoints = end - start;
-				java.lang.System.arraycopy(x, start, x, 0, nbPoints);
+				java.lang.System.arraycopy(x, 1, x, 0, nbPoints);
 				java.lang.System.arraycopy(y, start, y, 0, nbPoints);
 				signChangeIndex -= start;
 			}else
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math40
### Patch Diff Hash-SHA-256:

9ea7937da02648d1715702b668b1ee61b9903f6348513931e8af20006fa4645a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -190,7 +190,7 @@
 			}
 		}
 		double x0 = 0;
-		for (int j = end - 1; j >= start; --j) {
+		for (int j = ((maximalOrder) + 1) / 2; j >= start; --j) {
 			x0 = (x[j]) + (x0 * (targetY - (y[j])));
 		}
 		return x0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math40
### Patch Diff Hash-SHA-256:

a1e279d009bc0bbeec96542aebbe1b224eaf09188110eccfc9f66af34750640f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -190,7 +190,7 @@
 			}
 		}
 		double x0 = 0;
-		for (int j = end - 1; j >= start; --j) {
+		for (int j = ((DEFAULT_MAXIMAL_ORDER) + 1) / 2; j >= start; --j) {
 			x0 = (x[j]) + (x0 * (targetY - (y[j])));
 		}
 		return x0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math40
### Patch Diff Hash-SHA-256:

bdf746c59a8ccc0815ef291c6db9a0558e669b68b475c6ccd62b068a5c3525df

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -190,7 +190,7 @@
 			}
 		}
 		double x0 = 0;
-		for (int j = end - 1; j >= start; --j) {
+		for (int j = (MAXIMAL_AGING) + 1; j >= start; --j) {
 			x0 = (x[j]) + (x0 * (targetY - (y[j])));
 		}
 		return x0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math40
### Patch Diff Hash-SHA-256:

c7b6a3841103a1064ae73f1e9d2a1dabb581ba3154cb904ac12e1ff9997be195

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -190,7 +190,7 @@
 			}
 		}
 		double x0 = 0;
-		for (int j = end - 1; j >= start; --j) {
+		for (int j = (maximalOrder) - 2; j >= start; --j) {
 			x0 = (x[j]) + (x0 * (targetY - (y[j])));
 		}
 		return x0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---