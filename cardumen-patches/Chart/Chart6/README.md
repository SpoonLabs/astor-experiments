
# Patches of Chart6 from Defects4J 
Total patches 2
## Patch 1 of bug id Chart6
### Patch Diff Hash-SHA-256:

afd2c4ae9e237fc996d674550ceff9f1b3f63a8e97eef1262cde639b39769ba6

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeList.java	
+++ /fixed/org/jfree/chart/util/ShapeList.java	
@@ -13,7 +13,7 @@
 	}
 
 	public void setShape(int index, java.awt.Shape shape) {
-		set(index, shape);
+		super.set(org.jfree.chart.util.AbstractObjectList.DEFAULT_INITIAL_CAPACITY, shape);
 	}
 
 	public java.lang.Object clone() throws java.lang.CloneNotSupportedException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart6
### Patch Diff Hash-SHA-256:

791993c4cedab17769bd50a3253b03d9b8f873f95e115f1a06b70a375bb0a5eb

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeList.java	
+++ /fixed/org/jfree/chart/util/ShapeList.java	
@@ -13,7 +13,7 @@
 	}
 
 	public void setShape(int index, java.awt.Shape shape) {
-		set(index, shape);
+		set(org.jfree.chart.util.AbstractObjectList.DEFAULT_INITIAL_CAPACITY, shape);
 	}
 
 	public java.lang.Object clone() throws java.lang.CloneNotSupportedException {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---