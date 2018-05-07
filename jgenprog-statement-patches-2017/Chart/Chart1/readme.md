
# Patches of Chart1 from Defects4J 
Total patches 6
## Patch 1 of bug id Chart1
### Patch Diff Hash-SHA-256:

48550e26be56230e01654f2d16703f7528b05305621c8c60ecd6dff02092f22b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,8 +766,8 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
-			return result;
+		if (dataset == null) {
+			return null;
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---
## Patch 2 of bug id Chart1
### Patch Diff Hash-SHA-256:

41d9f6bfe43e30002aea0765e8e52298106dd13d2f15fe24b5e95c51b679acde

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,9 +766,6 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
-			return result;
-		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
 			for (int i = 0; i < seriesCount; i++) {
```


---
## Patch 3 of bug id Chart1
### Patch Diff Hash-SHA-256:

c106cf73d85053e8aa71a79faa5e8a25bc6b02297b95579eee0fafadb1b4d0e6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -767,7 +767,6 @@
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
 		if (dataset != null) {
-			return result;
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---
## Patch 4 of bug id Chart1
### Patch Diff Hash-SHA-256:

33a16f770f80ea62253d5c86b232098bcb437c9d090fe65e6053b93a68d27a6b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```


---
## Patch 5 of bug id Chart1
### Patch Diff Hash-SHA-256:

8df291d695162cfa90216fc27b12374ee552320c12c826c18424e7de58d856e6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -767,7 +767,11 @@
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
 		if (dataset != null) {
-			return result;
+			org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.rowCount = dataset.getRowCount();
+			org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.columnCount = dataset.getColumnCount();
+		}else {
+			org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.rowCount = 0;
+			org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.columnCount = 0;
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---
## Patch 6 of bug id Chart1
### Patch Diff Hash-SHA-256:

5f2f96c2e7856b62418ddb72be118d016464c9b12c1a5f3a337ab4ce8f16a07d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,8 +766,8 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
-			return result;
+		if (plot == null) {
+			throw new java.lang.IllegalArgumentException("Null 'plot' argument.");
 		}
 		int seriesCount = dataset.getRowCount();
 		if (plot.getRowRenderingOrder().equals(org.jfree.chart.util.SortOrder.ASCENDING)) {
```


---