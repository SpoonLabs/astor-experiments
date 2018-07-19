
# Patches of Chart11 from Defects4J 
Total patches 2
## Patch 1 of bug id Chart11
### Patch Diff Hash-SHA-256:

efc784c5419f96f7951128c386ee0278be7998f552f4253356f01de05b9b79d1

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeUtilities.java	
+++ /fixed/org/jfree/chart/util/ShapeUtilities.java	
@@ -122,7 +122,7 @@
 		if ((p1.getWindingRule()) != (p2.getWindingRule())) {
 			return false;
 		}
-		java.awt.geom.PathIterator iterator1 = p1.getPathIterator(null);
+		java.awt.geom.PathIterator iterator1 = p2.getPathIterator(null);
 		java.awt.geom.PathIterator iterator2 = p1.getPathIterator(null);
 		double[] d1 = new double[6];
 		double[] d2 = new double[6];
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart11
### Patch Diff Hash-SHA-256:

0362307596b1ce5782f7e283f4c882f142d7f8ea2b3d023a57e4e6b501cc5bab

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeUtilities.java	
+++ /fixed/org/jfree/chart/util/ShapeUtilities.java	
@@ -123,7 +123,7 @@
 			return false;
 		}
 		java.awt.geom.PathIterator iterator1 = p1.getPathIterator(null);
-		java.awt.geom.PathIterator iterator2 = p1.getPathIterator(null);
+		java.awt.geom.PathIterator iterator2 = p2.getPathIterator(null);
 		double[] d1 = new double[6];
 		double[] d2 = new double[6];
 		boolean done = (iterator1.isDone()) && (iterator2.isDone());
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---