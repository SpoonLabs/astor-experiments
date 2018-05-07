
# Patches of Chart6 from Defects4J 
Total patches 3
## Patch 1 of bug id Chart6
### Patch Diff Hash-SHA-256:

f935f6a68d77b1bb4ff42e6534762d50de22db1a6d2476112f764d943b440ad6

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeList.java	
+++ /fixed/org/jfree/chart/util/ShapeList.java	
@@ -11,6 +11,7 @@
 	}
 
 	public void setShape(int index, java.awt.Shape shape) {
+		index = 0;
 		set(index, shape);
 	}
```


---
## Patch 2 of bug id Chart6
### Patch Diff Hash-SHA-256:

81f73a7b80fe8173783258468fd3dcd1705a74281aceb5df0922cd34970a20b3

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeList.java	
+++ /fixed/org/jfree/chart/util/ShapeList.java	
@@ -11,6 +11,7 @@
 	}
 
 	public void setShape(int index, java.awt.Shape shape) {
+		index = org.jfree.chart.util.AbstractObjectList.DEFAULT_INITIAL_CAPACITY;
 		set(index, shape);
 	}
```


---
## Patch 3 of bug id Chart6
### Patch Diff Hash-SHA-256:

ee709fb0fd85977addc0143334eedcd7890b1a8fa81caceb96b2bd611a646afc

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeList.java	
+++ /fixed/org/jfree/chart/util/ShapeList.java	
@@ -11,6 +11,7 @@
 	}
 
 	public void setShape(int index, java.awt.Shape shape) {
+		index = 193;
 		set(index, shape);
 	}
```


---