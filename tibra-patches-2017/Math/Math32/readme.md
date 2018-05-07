
# Patches of Math32 from Defects4J 
Total patches 1
## Patch 1 of bug id Math32
### Patch Diff Hash-SHA-256:

c73c2ebbff35c2e4b56eeff94a4a9a61ded043aeb48e31a1c112757daf090884

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/partitioning/BSPTree.java	
+++ /fixed/org/apache/commons/math3/geometry/partitioning/BSPTree.java	
@@ -57,6 +57,7 @@
 		cut = chopped;
 		plus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>();
 		plus.parent = this;
+		cut = cut.reunite(chopped);
 		minus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>();
 		minus.parent = this;
 		return true;
@@ -227,11 +228,11 @@
 				{
 					final org.apache.commons.math3.geometry.partitioning.BSPTree<S> split = minus.split(sub);
 					if ((cut.side(sHyperplane)) == (org.apache.commons.math3.geometry.partitioning.Side.PLUS)) {
-						split.plus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.plus, attribute);
+						split.plus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.plus, this.attribute);
 						split.plus.condense();
 						split.plus.parent = split;
 					}else {
-						split.minus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.minus, attribute);
+						split.minus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.minus, this.attribute);
 						split.minus.condense();
 						split.minus.parent = split;
 					}
```


---