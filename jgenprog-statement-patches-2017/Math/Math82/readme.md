
# Patches of Math82 from Defects4J 
Total patches 1
## Patch 1 of bug id Math82
### Patch Diff Hash-SHA-256:

22a211091f9029d0f86f2ce242b01a68320675ddd795973d1cca0568c49af573

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -20,10 +20,9 @@
 		double minValue = 0;
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
-			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0)
 				minPos = i;
-			}
+			
 		}
 		return minPos;
 	}
```


---