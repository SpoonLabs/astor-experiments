
# Patches of Math5 from Defects4J 
Total patches 2
## Patch 1 of bug id Math5
### Patch Diff Hash-SHA-256:

5934ee3d118acb4e3c4818d81bd648af32eebcd4b3624ede12c6d31bebacc69e

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -119,7 +119,7 @@
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
## Patch 2 of bug id Math5
### Patch Diff Hash-SHA-256:

e68ea76406a1925af695123b16973633e3a9ada18502912a37fbc84f74824261

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -119,7 +119,7 @@
 			return org.apache.commons.math3.complex.Complex.NaN;
 		}
 		if (((real) == 0.0) && ((imaginary) == 0.0)) {
-			return org.apache.commons.math3.complex.Complex.NaN;
+			return createComplex(((real) + (INF.getReal())), ((imaginary) + (INF.getImaginary())));
 		}
 		if (isInfinite) {
 			return org.apache.commons.math3.complex.Complex.ZERO;
```


---