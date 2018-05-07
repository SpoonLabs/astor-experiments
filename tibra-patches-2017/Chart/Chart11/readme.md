
# Patches of Chart11 from Defects4J 
Total patches 1
## Patch 1 of bug id Chart11
### Patch Diff Hash-SHA-256:

5e9cb8d57ac602d816c41e85bb41767d550f3faec04d2e80414531f780c241b4

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeUtilities.java	
+++ /fixed/org/jfree/chart/util/ShapeUtilities.java	
@@ -123,6 +123,7 @@
 			return false;
 		}
 		java.awt.geom.PathIterator iterator1 = p1.getPathIterator(null);
+		p1 = p2;
 		java.awt.geom.PathIterator iterator2 = p1.getPathIterator(null);
 		double[] d1 = new double[6];
 		double[] d2 = new double[6];
```


---