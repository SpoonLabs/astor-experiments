
# Patches of Math53 from Defects4J 
Total patches 2
## Patch 1 of bug id Math53
### Patch Diff Hash-SHA-256:

7d729043bc11d24f3d80a6fe33c5bb3c5dcea7965b49275dfcea1eef2af2584e

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -55,6 +55,9 @@
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

9e4e10b0129d5e56b28ad4962e0c68a8e881cfe22d1c0bafb7d9ddae412e25d6

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -56,6 +56,9 @@
 
 	public org.apache.commons.math.complex.Complex add(org.apache.commons.math.complex.Complex rhs) throws org.apache.commons.math.exception.NullArgumentException {
 		org.apache.commons.math.util.MathUtils.checkNotNull(rhs);
+		if ((isNaN) || (rhs.isNaN)) {
+			return org.apache.commons.math.complex.Complex.NaN;
+		}
 		return createComplex(((real) + (rhs.getReal())), ((imaginary) + (rhs.getImaginary())));
 	}
```


---