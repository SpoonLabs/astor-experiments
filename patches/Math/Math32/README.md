
# Patches of Math32 from Defects4J 
Total patches 2
## Patch 1 of bug id Math32
### Patch Diff Hash-SHA-256:

f1ae10d749f2ee7c62caa10d4b52707b0c0bca502a9bd48cc6ef46d7a1e78dd2

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
+++ /fixed/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
@@ -162,7 +162,7 @@
 			return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(0, (inverse * (z)), ((-inverse) * (y)));
 		}else
 			if (((y) >= (-threshold)) && ((y) <= threshold)) {
-				double inverse = 1 / (org.apache.commons.math3.util.FastMath.sqrt((((x) * (x)) + ((z) * (z)))));
+				double inverse = (x) * (x);
 				return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(((-inverse) * (z)), 0, (inverse * (x)));
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math32
### Patch Diff Hash-SHA-256:

e79a5a4cd4d40c2f11c0061844a6d9f0c6087be1cae2584226c3dfc1ea7ee5db

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
+++ /fixed/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
@@ -162,7 +162,7 @@
 			return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(0, (inverse * (z)), ((-inverse) * (y)));
 		}else
 			if (((y) >= (-threshold)) && ((y) <= threshold)) {
-				double inverse = 1 / (org.apache.commons.math3.util.FastMath.sqrt((((x) * (x)) + ((z) * (z)))));
+				double inverse = org.apache.commons.math3.util.FastMath.max(x, x);
 				return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(((-inverse) * (z)), 0, (inverse * (x)));
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---