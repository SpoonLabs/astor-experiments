
# Patches of Math33 from Defects4J 
Total patches 1
## Patch 1 of bug id Math33
### Patch Diff Hash-SHA-256:

4906b7764502e1f62aeb0f868b903278f20e9ced08b554a3824bd20806aca0aa

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexTableau.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexTableau.java	
@@ -168,7 +168,7 @@
 		columnsToDrop.add(0);
 		for (int i = getNumObjectiveFunctions(); i < (getArtificialVariableOffset()); i++) {
 			final double entry = tableau.getEntry(0, i);
-			if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
+			if (entry >= (((1.5 * (epsilon)) * (epsilon)) - (org.apache.commons.math3.util.FastMath.abs((entry * (epsilon)))))) {
 				columnsToDrop.add(i);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---