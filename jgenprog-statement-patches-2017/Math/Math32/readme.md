
# Patches of Math32 from Defects4J 
Total patches 2
## Patch 1 of bug id Math32
### Patch Diff Hash-SHA-256:

dd6f0404fbc1e20c403ebee64a203e833454c9a81c0d9c1a759d742068ec651c

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/partitioning/AbstractRegion.java	
+++ /fixed/org/apache/commons/math3/geometry/partitioning/AbstractRegion.java	
@@ -151,6 +151,7 @@
 			if (plusChar.hasOut()) {
 				final org.apache.commons.math3.geometry.partitioning.Characterization<S> minusChar = new org.apache.commons.math3.geometry.partitioning.Characterization<S>();
 				characterize(node.getMinus(), plusChar.getOut(), minusChar);
+				characterize(node.getMinus(), plusChar.getOut(), minusChar);
 				if (minusChar.hasIn()) {
 					plusOutside = minusChar.getIn();
 				}
```


---
## Patch 2 of bug id Math32
### Patch Diff Hash-SHA-256:

6604dd96ade105b23fa7f269bb42e62e232ce85fa43c23de0785e4f18b091671

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
+++ /fixed/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
@@ -162,7 +162,7 @@
 			return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(0, (inverse * (z)), ((-inverse) * (y)));
 		}else
 			if (((y) >= (-threshold)) && ((y) <= threshold)) {
-				double inverse = 1 / (org.apache.commons.math3.util.FastMath.sqrt((((x) * (x)) + ((z) * (z)))));
+				double inverse = 1 / (org.apache.commons.math3.util.FastMath.sqrt((((x) * (x)) + ((y) * (y)))));
 				return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(((-inverse) * (z)), 0, (inverse * (x)));
 			}
```


---