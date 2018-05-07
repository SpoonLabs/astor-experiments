
# Patches of Math28 from Defects4J 
Total patches 11
## Patch 1 of bug id Math28
### Patch Diff Hash-SHA-256:

507361f278146e2ab5e228c7d3aa253c601bc56b1ae05a65814e2c26b474b5bb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,13 +59,6 @@
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
## Patch 2 of bug id Math28
### Patch Diff Hash-SHA-256:

e2abbecb9621b20ee286c2d35602097b08aba454e0ca3ceb50cb4123f7c57862

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -80,7 +80,7 @@
 						}
 					}
 				}
-				return minRow;
+				return minRatioPositions.get(0);
 			}
 		
 		return minRatioPositions.get(0);
```


---
## Patch 3 of bug id Math28
### Patch Diff Hash-SHA-256:

ff1791318d4897b6d46123c220fb81ddcf9be77a40bdab59a94b60dabd71ea7c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -74,7 +74,7 @@
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
 							if (i < minIndex) {
-								minIndex = i;
+								minRatioPositions = new java.util.ArrayList<java.lang.Integer>();
 								minRow = row;
 							}
 						}
```


---
## Patch 4 of bug id Math28
### Patch Diff Hash-SHA-256:

bf52f162192c8ec6d664201a7f69a18b69b84e2e3e8a3166e88f315e8e89edac

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -56,33 +56,8 @@
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
## Patch 5 of bug id Math28
### Patch Diff Hash-SHA-256:

4fa7364586c371b4d328242d79d474a85a5d092f945710d60a62df1b638074d4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					setMaxIterations(org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```


---
## Patch 6 of bug id Math28
### Patch Diff Hash-SHA-256:

6e733bcbe1e1c6e2ffae2c42448cf5bffb5a64d335d9b5de192db37f3d391b01

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -58,15 +58,6 @@
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
## Patch 7 of bug id Math28
### Patch Diff Hash-SHA-256:

d166467c83b4ff8e26f8310e2b075bfc23875d034d736d969186bfc9c420dc8c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -26,10 +26,9 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			final double entry = tableau.getEntry(0, i);
-			if (entry < minValue) {
-				minValue = entry;
+			if (entry < minValue)
 				minPos = i;
-			}
+			
 		}
 		return minPos;
 	}
```


---
## Patch 8 of bug id Math28
### Patch Diff Hash-SHA-256:

21a3b3753ca3273af618a21ad4c27e99893e9e87730c4bb5cad2b75ce0a70cf5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,6 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```


---
## Patch 9 of bug id Math28
### Patch Diff Hash-SHA-256:

1b92de9ebd2f1b04f61428a53de0a744607262cd0b46c8e3c15341c0782191a1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,10 +73,9 @@
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
## Patch 10 of bug id Math28
### Patch Diff Hash-SHA-256:

8eea2eabc32d443ec60c9e2796b9252b78daaefba92acb768475c8f6a1618fa7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -80,7 +80,6 @@
 						}
 					}
 				}
-				return minRow;
 			}
 		
 		return minRatioPositions.get(0);
```


---
## Patch 11 of bug id Math28
### Patch Diff Hash-SHA-256:

014ae56c12ce25b9abe5c4324f7f1912fcaca8c4a7d6ffae9189c44bb1a3861c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -63,7 +63,6 @@
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
 						}
 					}
 				}
```


---