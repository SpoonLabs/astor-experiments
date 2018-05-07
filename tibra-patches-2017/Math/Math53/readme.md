
# Patches of Math53 from Defects4J 
Total patches 2
## Patch 1 of bug id Math53
### Patch Diff Hash-SHA-256:

433785ee8b78f11feb9e794dff5b1258d8fd9ad143c27a09cad553f083705797

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -53,6 +53,9 @@
 	}
 
 	public org.apache.commons.math.complex.Complex add(org.apache.commons.math.complex.Complex rhs) throws org.apache.commons.math.exception.NullArgumentException {
+		if ((isNaN) || (rhs.isNaN)) {
+			return org.apache.commons.math.complex.Complex.NaN;
+		}
 		org.apache.commons.math.util.MathUtils.checkNotNull(rhs);
 		return createComplex(((real) + (rhs.getReal())), ((imaginary) + (rhs.getImaginary())));
 	}
```


---
## Patch 2 of bug id Math53
### Patch Diff Hash-SHA-256:

e4e87f4c5612434f094ac5bc587084d0366465b4a3cc183d1a048a8f2c39af3d

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -54,6 +54,9 @@
 
 	public org.apache.commons.math.complex.Complex add(org.apache.commons.math.complex.Complex rhs) throws org.apache.commons.math.exception.NullArgumentException {
 		org.apache.commons.math.util.MathUtils.checkNotNull(rhs);
+		if ((isNaN) || (rhs.isNaN)) {
+			return org.apache.commons.math.complex.Complex.NaN;
+		}
 		return createComplex(((real) + (rhs.getReal())), ((imaginary) + (rhs.getImaginary())));
 	}
```


---