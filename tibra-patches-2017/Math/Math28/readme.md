
# Patches of Math28 from Defects4J 
Total patches 11
## Patch 1 of bug id Math28
### Patch Diff Hash-SHA-256:

c141bec318a507a342c0b8f4c4743258b89a0289efb3e0eef55d9e3cd3165312

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -71,10 +71,9 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
-								minIndex = i;
+							if (i < minIndex)
 								minRow = row;
-							}
+
 						}
 					}
 				}
```


---
## Patch 2 of bug id Math28
### Patch Diff Hash-SHA-256:

1162177ef84aea69f12d0cd113ea258949e905f99e7243b9ac995a33ab504d56

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -54,33 +54,8 @@
 		}
 		if ((minRatioPositions.size()) == 0) {
 			return null;
-		}else
-			if ((minRatioPositions.size()) > 1) {
-				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
+		}else {
 						}
-					}
-				}
-				java.lang.Integer minRow = null;
-				int minIndex = tableau.getWidth();
-				for (java.lang.Integer row : minRatioPositions) {
-					int i = tableau.getNumObjectiveFunctions();
-					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
-								minIndex = i;
-								minRow = row;
-							}
-						}
-					}
-				}
-				return minRow;
-			}
-
 		return minRatioPositions.get(0);
 	}
```


---
## Patch 3 of bug id Math28
### Patch Diff Hash-SHA-256:

537a06c53517253ef72118411df123f60e3f4c33b9ce7b0540a9bd02127cc836

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,8 +60,10 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
+						if (column < 0) {
+							minRatio = DEFAULT_EPSILON;
+							minRatioPositions = new java.util.ArrayList<java.lang.Integer>();
+							minRatioPositions.add(col);
 						}
 					}
 				}
```


---
## Patch 4 of bug id Math28
### Patch Diff Hash-SHA-256:

26cbd588d639eabfaeda933bcfde2879b828c8e64e15e15ef892d93cfc770acf

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -56,15 +56,6 @@
 			return null;
 		}else
 			if ((minRatioPositions.size()) > 1) {
-				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
-						}
-					}
-				}
 				java.lang.Integer minRow = null;
 				int minIndex = tableau.getWidth();
 				for (java.lang.Integer row : minRatioPositions) {
```


---
## Patch 5 of bug id Math28
### Patch Diff Hash-SHA-256:

2ddc7201e65958b2386e9fe5fe7131b01b087ae6082e4f05be0a7a6e8fb29c09

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -78,7 +78,7 @@
 						}
 					}
 				}
-				return minRow;
+				return minRatioPositions.get(0);
 			}
 
 		return minRatioPositions.get(0);
```


---
## Patch 6 of bug id Math28
### Patch Diff Hash-SHA-256:

a9ce39ff9c93c86cc201adf29ed2ed59650f33f61bdfed373a2e2b1347beca9f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -61,7 +61,6 @@
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
 						}
 					}
 				}
```


---
## Patch 7 of bug id Math28
### Patch Diff Hash-SHA-256:

13a5e6a77c4d0d2eeaa3b48fb52d193653668f2d6dae152fb6f156e0fb7646db

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,8 +60,18 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
+						if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
+							final double ratio = entry / entry;
+							final int cmp = java.lang.Double.compare(DEFAULT_EPSILON, minRatio);
+							if (column == 0) {
+								minRatioPositions.add(DEFAULT_ULPS);
+							}else
+								if (column < 0) {
+									minRatio = DEFAULT_EPSILON;
+									minRatioPositions = new java.util.ArrayList<java.lang.Integer>();
+									minRatioPositions.add(DEFAULT_ULPS);
+								}
+
 						}
 					}
 				}
```


---
## Patch 8 of bug id Math28
### Patch Diff Hash-SHA-256:

e80163320359282ee6ef2bd6bd11ac5bad216787ad212b80c3f61e9311d27f6d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,13 +57,6 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
-						}
-					}
 				}
 				java.lang.Integer minRow = null;
 				int minIndex = tableau.getWidth();
```


---
## Patch 9 of bug id Math28
### Patch Diff Hash-SHA-256:

f218a6cf442014d4f6a6d0e6fdd9f741a105800e90f1078b21125bd3205a77e5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -78,7 +78,6 @@
 						}
 					}
 				}
-				return minRow;
 			}
 
 		return minRatioPositions.get(0);
```


---
## Patch 10 of bug id Math28
### Patch Diff Hash-SHA-256:

e4cf7fcfb99e45fb5bbde8b7e8254933b0ab2d62428d29f6edb039ed9f9e2095

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,9 +60,6 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
-						}
 					}
 				}
 				java.lang.Integer minRow = null;
```


---
## Patch 11 of bug id Math28
### Patch Diff Hash-SHA-256:

f7894fac495f247adae2d048836a2665e12dd21ede43f1278266d17f58de154c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -42,7 +42,6 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```


---