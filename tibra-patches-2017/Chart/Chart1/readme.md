
# Patches of Chart1 from Defects4J 
Total patches 6
## Patch 1 of bug id Chart1
### Patch Diff Hash-SHA-256:

8ce3588226c5ec690169fdc81ffe53a02e9da2c73b82fd228a3719b4a846bd04

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -764,9 +764,6 @@
 		}
 		int index = this.plot.getIndexOf(this);
 		org.jfree.data.category.CategoryDataset dataset = this.plot.getDataset(index);
-		if (dataset != null) {
-			return result;
-		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
 			for (int i = 0; i < seriesCount; i++) {
```


---
## Patch 2 of bug id Chart1
### Patch Diff Hash-SHA-256:

a9a9caf6f09cb105384adb60cf8cb3a58eaf6db70a1363c0d2e488793551d951

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -765,7 +765,6 @@
 		int index = this.plot.getIndexOf(this);
 		org.jfree.data.category.CategoryDataset dataset = this.plot.getDataset(index);
 		if (dataset != null) {
-			return result;
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---
## Patch 3 of bug id Chart1
### Patch Diff Hash-SHA-256:

4f0a0016cab57e51b0663e997b1993644501699bdf6c85040f277982b4d4cd5f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -764,8 +764,8 @@
 		}
 		int index = this.plot.getIndexOf(this);
 		org.jfree.data.category.CategoryDataset dataset = this.plot.getDataset(index);
-		if (dataset != null) {
-			return result;
+		if (plot == null) {
+			throw new java.lang.IllegalArgumentException("Null 'plot' argument.");
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---
## Patch 4 of bug id Chart1
### Patch Diff Hash-SHA-256:

b2ccf579edaa9414b9ca6e9dfb34b86a968adceacf172871253ae448bc0b7369

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -764,8 +764,8 @@
 		}
 		int index = this.plot.getIndexOf(this);
 		org.jfree.data.category.CategoryDataset dataset = this.plot.getDataset(index);
-		if (dataset != null) {
-			return result;
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) == null) {
+			throw new java.lang.IllegalArgumentException("Null 'hotspot' argument.");
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---
## Patch 5 of bug id Chart1
### Patch Diff Hash-SHA-256:

6b6b591372f3c461752218a060416d06482bffaa35da45b0a8385cceeaa73ca7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -764,7 +764,7 @@
 		}
 		int index = this.plot.getIndexOf(this);
 		org.jfree.data.category.CategoryDataset dataset = this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((this.plot) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```


---
## Patch 6 of bug id Chart1
### Patch Diff Hash-SHA-256:

a29f221fbba24fa160ccde13de4ae77d786e1dfaf11664817dbbe5109f70bd08

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -764,8 +764,8 @@
 		}
 		int index = this.plot.getIndexOf(this);
 		org.jfree.data.category.CategoryDataset dataset = this.plot.getDataset(index);
-		if (dataset != null) {
-			return result;
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) == null) {
+			throw new java.lang.IllegalArgumentException("Null 'lastBarPaint' argument");
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---