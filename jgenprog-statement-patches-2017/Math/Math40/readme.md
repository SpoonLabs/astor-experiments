
# Patches of Math40 from Defects4J 
Total patches 3
## Patch 1 of bug id Math40
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


---
## Patch 3 of bug id Math40
### Patch Diff Hash-SHA-256:

559376e939e1e3732effe2407955ef06f1e56f87f52dc834365de5db973f20cb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -118,6 +118,7 @@
 				if (agingB >= (org.apache.commons.math.analysis.solvers.BracketingNthOrderBrentSolver.MAXIMAL_AGING)) {
 					targetY = (-(org.apache.commons.math.analysis.solvers.BracketingNthOrderBrentSolver.REDUCTION_FACTOR)) * yA;
 				}else {
+					signChangeIndex = 2;
 					targetY = 0;
 				}
```


---