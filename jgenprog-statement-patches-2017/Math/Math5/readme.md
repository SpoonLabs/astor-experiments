
# Patches of Math5 from Defects4J 
Total patches 1
## Patch 1 of bug id Math5
### Patch Diff Hash-SHA-256:

1546323dccdd64f7e5c29590eea17a01e4dd162dabcf556fa983d966a49c858b

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -121,7 +121,7 @@
 			return org.apache.commons.math3.complex.Complex.NaN;
 		}
 		if (((real) == 0.0) && ((imaginary) == 0.0)) {
-			return org.apache.commons.math3.complex.Complex.NaN;
+			return org.apache.commons.math3.complex.Complex.INF;
 		}
 		if (isInfinite) {
 			return org.apache.commons.math3.complex.Complex.ZERO;
```


---