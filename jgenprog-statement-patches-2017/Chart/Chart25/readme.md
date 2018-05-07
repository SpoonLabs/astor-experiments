
# Patches of Chart25 from Defects4J 
Total patches 53
## Patch 1 of bug id Chart25
### Patch Diff Hash-SHA-256:

a5a60dce58ad3c7d492b366c6c66b2ba70bcf467ad533836d387cae0adf94b4c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,9 +1226,6 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
-			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
 				if (r != null) {
```


---
## Patch 2 of bug id Chart25
### Patch Diff Hash-SHA-256:

21439558d9fedb6f3141a779d6f535538c01925c317fb5009df3d23f470b1a62

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,13 +223,6 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
-					return false;
-				}
-			}
-		}
 		return true;
 	}
```


---
## Patch 3 of bug id Chart25
### Patch Diff Hash-SHA-256:

d981a3ef4a482527cace0c107990a5ee82a78658d95ddf9d4d9b3a47e536034c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,33 +1336,6 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}
-			}
 		}
 		return foundData;
 	}
```


---
## Patch 4 of bug id Chart25
### Patch Diff Hash-SHA-256:

703f2c8fa1efd0712ccc37d5193f1d7ecfb08514e7cde9f063b0bcb2c388f0c5

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -86,7 +86,6 @@
 			row = new org.jfree.data.KeyedObjects();
 			org.jfree.data.KeyedObjects2D.this.rows.add(row);
 		}
-		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
```


---
## Patch 5 of bug id Chart25
### Patch Diff Hash-SHA-256:

3f29bcb428490ec886020b62ffadb4d655c927cea8f5f73ee95328ab2254833e

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -26,7 +26,6 @@
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
 		if (masd != null) {
-			result = masd.getMean();
 		}
 		return result;
 	}
```


---
## Patch 6 of bug id Chart25
### Patch Diff Hash-SHA-256:

1a2558833014308bf1cae58a1642acca17f1d76e8c8ea6486404f8128a702abe

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -95,7 +95,7 @@
 	}
 
 	public int getColumnCount() {
-		return org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getColumnCount();
+		return 0;
 	}
 
 	public void add(double mean, double standardDeviation, java.lang.Comparable rowKey, java.lang.Comparable columnKey) {
```


---
## Patch 7 of bug id Chart25
### Patch Diff Hash-SHA-256:

d5ce1e229f1ef4314815b270272ba04c1fa65218f1f67bdd2b328780ca5f42e4

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -104,7 +104,6 @@
 
 	public void add(java.lang.Number mean, java.lang.Number standardDeviation, java.lang.Comparable rowKey, java.lang.Comparable columnKey) {
 		org.jfree.data.statistics.MeanAndStandardDeviation item = new org.jfree.data.statistics.MeanAndStandardDeviation(mean, standardDeviation);
-		org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.addObject(item, rowKey, columnKey);
 		double m = 0.0;
 		double sd = 0.0;
 		if (mean != null) {
```


---
## Patch 8 of bug id Chart25
### Patch Diff Hash-SHA-256:

304620c0b6aa1a4049e94dd47c0340b3606f09b80fa93947cb6642172caae1cc

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,9 +225,6 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
-					return false;
-				}
 			}
 		}
 		return true;
```


---
## Patch 9 of bug id Chart25
### Patch Diff Hash-SHA-256:

cc8663207f21cec07d69b0dc83be6c26f506f7bcc60016afe0dab8c5c6883738

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,8 +1226,13 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+			for (int i = 0; i < datasetCount; i++) {
+				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
+				if (r != null) {
+					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
+					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
+					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
+				}
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```


---
## Patch 10 of bug id Chart25
### Patch Diff Hash-SHA-256:

fd5a89f9b099aec6e8985abb545c89be29ae4b7e2376e9f9d3fe5dd55ae7a038

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1195,48 +1195,8 @@
 		java.awt.Composite originalComposite = g2.getComposite();
 		g2.setComposite(java.awt.AlphaComposite.getInstance(java.awt.AlphaComposite.SRC_OVER, getForegroundAlpha()));
 		org.jfree.chart.plot.DatasetRenderingOrder order = getDatasetRenderingOrder();
-		if (order == (org.jfree.chart.plot.DatasetRenderingOrder.FORWARD)) {
-			int datasetCount = org.jfree.chart.plot.CategoryPlot.this.datasets.size();
-			for (int i = 0; i < datasetCount; i++) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
-				}
-			}
-			for (int i = 0; i < datasetCount; i++) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
-			}
-			for (int i = 0; i < datasetCount; i++) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.FOREGROUND, state);
-				}
-			}
-		}else {
-			int datasetCount = org.jfree.chart.plot.CategoryPlot.this.datasets.size();
-			for (int i = datasetCount - 1; i >= 0; i--) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
-				}
-			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
-			}
-			for (int i = datasetCount - 1; i >= 0; i--) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.FOREGROUND, state);
-				}
-			}
+		if (isRangeCrosshairVisible()) {
+			drawRangeCrosshair(g2, dataArea, getOrientation(), getRangeCrosshairValue(), getRangeAxis(), getRangeCrosshairStroke(), getRangeCrosshairPaint());
 		}
 		for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.renderers.size()); i++) {
 			drawDomainMarkers(g2, dataArea, i, org.jfree.chart.util.Layer.FOREGROUND);
```


---
## Patch 11 of bug id Chart25
### Patch Diff Hash-SHA-256:

2df1f07112adad077da2aadd39b9e747e8cab627aed5f16abd2a93ae3332df19

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,12 +29,6 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
-			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
-				result = rowData.getObject(columnKey);
-			}
-		}
 		return result;
 	}
```


---
## Patch 12 of bug id Chart25
### Patch Diff Hash-SHA-256:

c241704e8e56ec8ba62ab2b963869a8e5d9892a04b14ba47d0a5dd37efe77e6f

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,6 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```


---
## Patch 13 of bug id Chart25
### Patch Diff Hash-SHA-256:

339cf5010b036ad8ea7beba8c82c7b9a6d7b13ab45035976f39653e6a79d132b

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,9 +25,6 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
-			result = masd.getMean();
-		}
 		return result;
 	}
```


---
## Patch 14 of bug id Chart25
### Patch Diff Hash-SHA-256:

4a22f082c936211f89969e26937046cbf92441bdbe6bb960c903efb6bf1c5094

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,9 +88,6 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
-		}
 	}
 
 	public void removeObject(java.lang.Comparable rowKey, java.lang.Comparable columnKey) {
```


---
## Patch 15 of bug id Chart25
### Patch Diff Hash-SHA-256:

8463158d5c6f791bc1ac93e2cc06c6e1f2231149c9fd9bb0410045bee9e3d98f

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,32 +1336,8 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}
+			for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.renderers.size()); i++) {
+				drawRangeMarkers(g2, dataArea, i, org.jfree.chart.util.Layer.BACKGROUND);
 			}
 		}
 		return foundData;
```


---
## Patch 16 of bug id Chart25
### Patch Diff Hash-SHA-256:

61b1eee80366a8b86c73ad3411f196b847081d50927378c2d29b2833f74beced

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,11 +224,6 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
-					return false;
-				}
-			}
 		}
 		return true;
 	}
```


---
## Patch 17 of bug id Chart25
### Patch Diff Hash-SHA-256:

720fcc8c4d5c3e08b137ba855dcad9091902b293be8249ebc4af74c8db24247d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,39 +1330,8 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
-			foundData = true;
-			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
-			int columnCount = currentDataset.getColumnCount();
-			int rowCount = currentDataset.getRowCount();
-			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}
-			}
+		if (rangeAxis == null) {
+			throw new java.lang.IllegalArgumentException("Null 'rangeAxis' argument.");
 		}
 		return foundData;
 	}
```


---
## Patch 18 of bug id Chart25
### Patch Diff Hash-SHA-256:

00f828915b19924dd620e3077427c1399677abdca8bb045c1635602545328aa9

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -23,7 +23,7 @@
 	}
 
 	public int getColumnCount() {
-		return org.jfree.data.KeyedObjects2D.this.columnKeys.size();
+		return -1;
 	}
 
 	public java.lang.Object getObject(int row, int column) {
```


---
## Patch 19 of bug id Chart25
### Patch Diff Hash-SHA-256:

b00446ef8071afb54a9370252de1685f6d87574304cc6a83e00d9d4a9b36f984

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -86,7 +86,7 @@
 			row = new org.jfree.data.KeyedObjects();
 			org.jfree.data.KeyedObjects2D.this.rows.add(row);
 		}
-		row.setObject(columnKey, object);
+		org.jfree.data.KeyedObjects2D.this.columnKeys.remove(columnKey);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
```


---
## Patch 20 of bug id Chart25
### Patch Diff Hash-SHA-256:

152fdaae76bb28e896403c5ba09e37128c25f2cc8879f1289c0c4a5cf6fb001c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
@@ -40,13 +40,6 @@
 		}
 		org.jfree.data.statistics.StatisticalCategoryDataset statData = ((org.jfree.data.statistics.StatisticalCategoryDataset) (data));
 		org.jfree.chart.plot.PlotOrientation orientation = plot.getOrientation();
-		if (orientation == (org.jfree.chart.plot.PlotOrientation.HORIZONTAL)) {
-			drawHorizontalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
-		}else
-			if (orientation == (org.jfree.chart.plot.PlotOrientation.VERTICAL)) {
-				drawVerticalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
-			}
-		
 	}
 
 	protected void drawHorizontalItem(java.awt.Graphics2D g2, org.jfree.chart.renderer.category.CategoryItemRendererState state, java.awt.geom.Rectangle2D dataArea, org.jfree.chart.plot.CategoryPlot plot, org.jfree.chart.axis.CategoryAxis domainAxis, org.jfree.chart.axis.ValueAxis rangeAxis, org.jfree.data.statistics.StatisticalCategoryDataset dataset, int row, int column) {
```


---
## Patch 21 of bug id Chart25
### Patch Diff Hash-SHA-256:

f082a0e73c8b9cac72b104658684a11a4958a3595b5dae2b01e163bd328ddc01

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -554,7 +552,6 @@
 	public java.awt.image.BufferedImage createBufferedImage(int width, int height, int imageType, org.jfree.chart.ChartRenderingInfo info) {
 		java.awt.image.BufferedImage image = new java.awt.image.BufferedImage(width, height, imageType);
 		java.awt.Graphics2D g2 = image.createGraphics();
-		draw(g2, new java.awt.geom.Rectangle2D.Double(0, 0, width, height), null, info);
 		g2.dispose();
 		return image;
 	}
@@ -733,31 +730,3 @@
 	}
 }
 
-class JFreeChartInfo extends org.jfree.chart.ui.ProjectInfo {
-	public JFreeChartInfo() {
-		java.lang.String baseResourceClass = "org.jfree.chart.resources.JFreeChartResources";
-		java.util.ResourceBundle resources = java.util.ResourceBundle.getBundle(baseResourceClass);
-		setName(resources.getString("project.name"));
-		setVersion(resources.getString("project.version"));
-		setInfo(resources.getString("project.info"));
-		setCopyright(resources.getString("project.copyright"));
-		setLogo(null);
-		setLicenceName("LGPL");
-		setLicenceText(org.jfree.chart.ui.Licences.getInstance().getLGPL());
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
-	}
-
-	public java.awt.Image getLogo() {
-		java.awt.Image logo = super.getLogo();
-		if (logo == null) {
-			java.net.URL imageURL = org.jfree.chart.JFreeChartInfo.this.getClass().getClassLoader().getResource("org/jfree/chart/gorilla.jpg");
-			if (imageURL != null) {
-				javax.swing.ImageIcon temp = new javax.swing.ImageIcon(imageURL);
-				logo = temp.getImage();
-				setLogo(logo);
-			}
-		}
-		return logo;
-	}
-}
-
```


---
## Patch 22 of bug id Chart25
### Patch Diff Hash-SHA-256:

5f9f8c6c9cb8bbebaaa5d4bbba02787c38bac4240d0b3ff3f31a981fb2eca124

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1337,31 +1337,6 @@
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}
 			}
 		}
 		return foundData;
```


---
## Patch 23 of bug id Chart25
### Patch Diff Hash-SHA-256:

8522f118885685ab68c877084ea9f4e94d0ed796fdec2eecba77656676901a6b

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,8 +225,8 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
-					return false;
+				if ((rowCount == 0) || (columnCount == 0)) {
+					return true;
 				}
 			}
 		}
```


---
## Patch 24 of bug id Chart25
### Patch Diff Hash-SHA-256:

865aeafa3e270b5b0db8bec46e82ae4a9cb000a10afb60e3cba7dd8a19aae065

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1341,7 +1341,6 @@
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
 							for (int row = rowCount - 1; row >= 0; row--) {
```


---
## Patch 25 of bug id Chart25
### Patch Diff Hash-SHA-256:

5156c01f5ad748a6a76cb9351dbac8656c015a554edd9fa18899d740c12ff9db

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1195,49 +1195,6 @@
 		java.awt.Composite originalComposite = g2.getComposite();
 		g2.setComposite(java.awt.AlphaComposite.getInstance(java.awt.AlphaComposite.SRC_OVER, getForegroundAlpha()));
 		org.jfree.chart.plot.DatasetRenderingOrder order = getDatasetRenderingOrder();
-		if (order == (org.jfree.chart.plot.DatasetRenderingOrder.FORWARD)) {
-			int datasetCount = org.jfree.chart.plot.CategoryPlot.this.datasets.size();
-			for (int i = 0; i < datasetCount; i++) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
-				}
-			}
-			for (int i = 0; i < datasetCount; i++) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
-			}
-			for (int i = 0; i < datasetCount; i++) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.FOREGROUND, state);
-				}
-			}
-		}else {
-			int datasetCount = org.jfree.chart.plot.CategoryPlot.this.datasets.size();
-			for (int i = datasetCount - 1; i >= 0; i--) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
-				}
-			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
-			}
-			for (int i = datasetCount - 1; i >= 0; i--) {
-				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
-				if (r != null) {
-					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
-					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
-					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.FOREGROUND, state);
-				}
-			}
-		}
 		for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.renderers.size()); i++) {
 			drawDomainMarkers(g2, dataArea, i, org.jfree.chart.util.Layer.FOREGROUND);
 		}
```


---
## Patch 26 of bug id Chart25
### Patch Diff Hash-SHA-256:

41583b76fe667b003087fa890a5cf0e94d0617a7da0c8e2c68950491dbf34ce7

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1339,15 +1339,6 @@
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
 					}
 				}else {
 					for (int column = columnCount - 1; column >= 0; column--) {
```


---
## Patch 27 of bug id Chart25
### Patch Diff Hash-SHA-256:

4f4da68aeecaef35ac048733b30a405853357438ede0fadd227ef3f767cbd4d2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,31 +1336,10 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
+			for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.domainAxes.size()); i++) {
+				org.jfree.chart.axis.CategoryAxis axis = ((org.jfree.chart.axis.CategoryAxis) (org.jfree.chart.plot.CategoryPlot.this.domainAxes.get(i)));
+				if (axis != null) {
+					axis.removeChangeListener(org.jfree.chart.plot.CategoryPlot.this);
 				}
 			}
 		}
```


---
## Patch 28 of bug id Chart25
### Patch Diff Hash-SHA-256:

a55e5802133b5777aa54b4283244b4daf5ae7ad6bc9bafb7f373d961383cd499

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,9 +1340,6 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
 						}else {
 							for (int row = rowCount - 1; row >= 0; row--) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```


---
## Patch 29 of bug id Chart25
### Patch Diff Hash-SHA-256:

1f3e9dfdb3be16ba4090a60ae794571d0da93540a6eac4633a2c6824d6d0df5d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,31 +1336,10 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
+			for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.rangeAxes.size()); i++) {
+				org.jfree.chart.axis.ValueAxis axis = ((org.jfree.chart.axis.ValueAxis) (org.jfree.chart.plot.CategoryPlot.this.rangeAxes.get(i)));
+				if (axis != null) {
+					axis.configure();
 				}
 			}
 		}
```


---
## Patch 30 of bug id Chart25
### Patch Diff Hash-SHA-256:

92290e96ad550966e53f59efdff7626b0146fd0b17bed7e2033d0e4ecf4bfb6a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1137,6 +1137,7 @@
 				org.jfree.chart.axis.Axis yAxis = ((org.jfree.chart.axis.Axis) (org.jfree.chart.plot.CategoryPlot.this.rangeAxes.get(i)));
 				if (yAxis != null) {
 					org.jfree.chart.util.RectangleEdge edge = getRangeAxisEdge(i);
+					org.jfree.chart.plot.CategoryPlot.this.renderers = new org.jfree.chart.util.ObjectList();
 					space = yAxis.reserveSpace(g2, org.jfree.chart.plot.CategoryPlot.this, plotArea, edge, space);
 				}
 			}
```


---
## Patch 31 of bug id Chart25
### Patch Diff Hash-SHA-256:

3e326839b35ac622d1cb72822e022e857c0b55f255009ebcd925cfa76dbc5b40

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,8 +88,8 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+		if (rowKey == null) {
+			throw new java.lang.IllegalArgumentException("Null 'rowKey' argument.");
 		}
 	}
```


---
## Patch 32 of bug id Chart25
### Patch Diff Hash-SHA-256:

77e51f7fb89cf5e80ddb33c11fce4577518af3684b21f96b26e1655ce4bca51a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
@@ -40,13 +40,11 @@
 		}
 		org.jfree.data.statistics.StatisticalCategoryDataset statData = ((org.jfree.data.statistics.StatisticalCategoryDataset) (data));
 		org.jfree.chart.plot.PlotOrientation orientation = plot.getOrientation();
-		if (orientation == (org.jfree.chart.plot.PlotOrientation.HORIZONTAL)) {
-			drawHorizontalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
-		}else
-			if (orientation == (org.jfree.chart.plot.PlotOrientation.VERTICAL)) {
-				drawVerticalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
+		if ((org.jfree.chart.renderer.category.StatisticalBarRenderer.this.errorIndicatorStroke) != null) {
+			g2.setStroke(org.jfree.chart.renderer.category.StatisticalBarRenderer.this.errorIndicatorStroke);
+		}else {
+			g2.setStroke(getItemOutlineStroke(row, column));
 			}
-		
 	}
 
 	protected void drawHorizontalItem(java.awt.Graphics2D g2, org.jfree.chart.renderer.category.CategoryItemRendererState state, java.awt.geom.Rectangle2D dataArea, org.jfree.chart.plot.CategoryPlot plot, org.jfree.chart.axis.CategoryAxis domainAxis, org.jfree.chart.axis.ValueAxis rangeAxis, org.jfree.data.statistics.StatisticalCategoryDataset dataset, int row, int column) {
```


---
## Patch 33 of bug id Chart25
### Patch Diff Hash-SHA-256:

c6161a2b1010005b092ce3c906164b7be0bdd2b0fe03df4a24989630b480b466

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -32,7 +32,7 @@
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
-				result = rowData.getObject(columnKey);
+				org.jfree.data.KeyedObjects2D.this.rowKeys = new java.util.ArrayList();
 			}
 		}
 		return result;
```


---
## Patch 34 of bug id Chart25
### Patch Diff Hash-SHA-256:

4c3aa940da5c055b4f66d38caec1ab8334b726ef9b2e1aeb6e3205c8b10a043a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -32,7 +32,6 @@
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
-				result = rowData.getObject(columnKey);
 			}
 		}
 		return result;
```


---
## Patch 35 of bug id Chart25
### Patch Diff Hash-SHA-256:

3b45af11277d2881283eab1d0ed6678bd90ce03ce7a3e8a11b5482ed7e5a4cd4

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1337,30 +1337,8 @@
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
+				if (renderer != null) {
+					renderer.addChangeListener(org.jfree.chart.plot.CategoryPlot.this);
 				}
 			}
 		}
```


---
## Patch 36 of bug id Chart25
### Patch Diff Hash-SHA-256:

37388d27cccc88ea60eca378d8277f88ffafaba897e807d5f0c7f5d58f6e386a

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -95,7 +95,7 @@
 	}
 
 	public int getColumnCount() {
-		return org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getColumnCount();
+		return -1;
 	}
 
 	public void add(double mean, double standardDeviation, java.lang.Comparable rowKey, java.lang.Comparable columnKey) {
```


---
## Patch 37 of bug id Chart25
### Patch Diff Hash-SHA-256:

ad700eb658707284992a7f1d4f430d351345297c5b8b04fe36d8c27320fec316

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1109,6 +1109,7 @@
 			}
 			for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.domainAxes.size()); i++) {
 				org.jfree.chart.axis.Axis xAxis = ((org.jfree.chart.axis.Axis) (org.jfree.chart.plot.CategoryPlot.this.domainAxes.get(i)));
+				org.jfree.chart.plot.CategoryPlot.this.datasets = new org.jfree.chart.util.ObjectList();
 				if (xAxis != null) {
 					org.jfree.chart.util.RectangleEdge edge = getDomainAxisEdge(i);
 					space = xAxis.reserveSpace(g2, org.jfree.chart.plot.CategoryPlot.this, plotArea, edge, space);
```


---
## Patch 38 of bug id Chart25
### Patch Diff Hash-SHA-256:

f53d83095b2fc734ccd3c9b51a277bdf9f0a9aa3e929791bd390c92d6b63748b

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -104,7 +104,7 @@
 
 	public void add(java.lang.Number mean, java.lang.Number standardDeviation, java.lang.Comparable rowKey, java.lang.Comparable columnKey) {
 		org.jfree.data.statistics.MeanAndStandardDeviation item = new org.jfree.data.statistics.MeanAndStandardDeviation(mean, standardDeviation);
-		org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.addObject(item, rowKey, columnKey);
+		fireDatasetChanged();
 		double m = 0.0;
 		double sd = 0.0;
 		if (mean != null) {
```


---
## Patch 39 of bug id Chart25
### Patch Diff Hash-SHA-256:

e55651160962c5377e84246bb041fca07ba52d5c35cc0b16c7d97fbf99dec80e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1306,6 +1306,7 @@
 			org.jfree.chart.axis.Axis axis = ((org.jfree.chart.axis.Axis) (iterator.next()));
 			if (axis != null) {
 				org.jfree.chart.axis.AxisState axisState = axis.draw(g2, cursor, plotArea, dataArea, org.jfree.chart.util.RectangleEdge.LEFT, plotState);
+				org.jfree.chart.plot.CategoryPlot.this.renderers = new org.jfree.chart.util.ObjectList();
 				cursor = axisState.getCursor();
 				axisStateMap.put(axis, axisState);
 			}
```


---
## Patch 40 of bug id Chart25
### Patch Diff Hash-SHA-256:

0d23c87f00f735c093aef1aef8c622da170fd1a40517c2d83f54d93e4e582f16

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,40 +1330,6 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
-			foundData = true;
-			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
-			int columnCount = currentDataset.getColumnCount();
-			int rowCount = currentDataset.getRowCount();
-			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}
-			}
-		}
 		return foundData;
 	}
```


---
## Patch 41 of bug id Chart25
### Patch Diff Hash-SHA-256:

75d5c9e65904feb2fba881e6b178697940a38fe880ccf921393d0e97946d1bc5

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1311,7 +1311,7 @@
 			}
 		} 
 		cursor = (dataArea.getMaxX()) + (org.jfree.chart.plot.CategoryPlot.this.axisOffset.calculateRightOutset(dataArea.getWidth()));
-		iterator = axisCollection.getAxesAtRight().iterator();
+		org.jfree.chart.plot.CategoryPlot.this.renderers = new org.jfree.chart.util.ObjectList();
 		while (iterator.hasNext()) {
 			org.jfree.chart.axis.Axis axis = ((org.jfree.chart.axis.Axis) (iterator.next()));
 			if (axis != null) {
```


---
## Patch 42 of bug id Chart25
### Patch Diff Hash-SHA-256:

931e3afd82ef185b30265ee676a75b201e50673731713c2f998ec25b4e1e41d3

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,8 +1226,13 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+			for (int i = datasetCount - 1; i >= 0; i--) {
+				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
+				if (r != null) {
+					org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(i);
+					org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(i);
+					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
+				}
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```


---
## Patch 43 of bug id Chart25
### Patch Diff Hash-SHA-256:

16a2d9838afc00c46c5a0c77aebc566b248f1cbb70245ea086fd498a61ecde1c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
@@ -40,13 +40,9 @@
 		}
 		org.jfree.data.statistics.StatisticalCategoryDataset statData = ((org.jfree.data.statistics.StatisticalCategoryDataset) (data));
 		org.jfree.chart.plot.PlotOrientation orientation = plot.getOrientation();
-		if (orientation == (org.jfree.chart.plot.PlotOrientation.HORIZONTAL)) {
-			drawHorizontalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
-		}else
-			if (orientation == (org.jfree.chart.plot.PlotOrientation.VERTICAL)) {
-				drawVerticalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
+		if (plot == null) {
+			throw new java.lang.IllegalArgumentException("Null 'plot' argument.");
 			}
-		
 	}
 
 	protected void drawHorizontalItem(java.awt.Graphics2D g2, org.jfree.chart.renderer.category.CategoryItemRendererState state, java.awt.geom.Rectangle2D dataArea, org.jfree.chart.plot.CategoryPlot plot, org.jfree.chart.axis.CategoryAxis domainAxis, org.jfree.chart.axis.ValueAxis rangeAxis, org.jfree.data.statistics.StatisticalCategoryDataset dataset, int row, int column) {
```


---
## Patch 44 of bug id Chart25
### Patch Diff Hash-SHA-256:

a107dc215e13d15d557054b09503279b7a6eaf4956691b124936d505876c3d2a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -86,6 +86,7 @@
 			row = new org.jfree.data.KeyedObjects();
 			org.jfree.data.KeyedObjects2D.this.rows.add(row);
 		}
+		row = new org.jfree.data.KeyedObjects();
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
```


---
## Patch 45 of bug id Chart25
### Patch Diff Hash-SHA-256:

35d978d4c7cde7e4463bfd4213f8a980b0928aaa4b811ea0381b9f1b55dc9048

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,16 +1338,8 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
+					for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.renderers.size()); i++) {
+						drawRangeMarkers(g2, dataArea, i, org.jfree.chart.util.Layer.BACKGROUND);
 					}
 				}else {
 					for (int column = columnCount - 1; column >= 0; column--) {
```


---
## Patch 46 of bug id Chart25
### Patch Diff Hash-SHA-256:

eb8ec4e93c4b0ebcfe23612ec92860059c59d2846a205dfd43c30e157ddada63

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/StatisticalBarRenderer.java	
@@ -40,13 +40,11 @@
 		}
 		org.jfree.data.statistics.StatisticalCategoryDataset statData = ((org.jfree.data.statistics.StatisticalCategoryDataset) (data));
 		org.jfree.chart.plot.PlotOrientation orientation = plot.getOrientation();
-		if (orientation == (org.jfree.chart.plot.PlotOrientation.HORIZONTAL)) {
-			drawHorizontalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
-		}else
-			if (orientation == (org.jfree.chart.plot.PlotOrientation.VERTICAL)) {
-				drawVerticalItem(g2, state, dataArea, plot, domainAxis, rangeAxis, statData, row, column);
+		if ((org.jfree.chart.renderer.category.StatisticalBarRenderer.this.errorIndicatorPaint) != null) {
+			g2.setPaint(org.jfree.chart.renderer.category.StatisticalBarRenderer.this.errorIndicatorPaint);
+		}else {
+			g2.setPaint(getItemOutlinePaint(row, column));
 			}
-		
 	}
 
 	protected void drawHorizontalItem(java.awt.Graphics2D g2, org.jfree.chart.renderer.category.CategoryItemRendererState state, java.awt.geom.Rectangle2D dataArea, org.jfree.chart.plot.CategoryPlot plot, org.jfree.chart.axis.CategoryAxis domainAxis, org.jfree.chart.axis.ValueAxis rangeAxis, org.jfree.data.statistics.StatisticalCategoryDataset dataset, int row, int column) {
```


---
## Patch 47 of bug id Chart25
### Patch Diff Hash-SHA-256:

06dc88a03228cf88f4371b09a450950287780d166c6b5c451ed04c5b8b4dbf9a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1341,7 +1341,7 @@
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
+								configureRangeAxes();
 							}
 						}else {
 							for (int row = rowCount - 1; row >= 0; row--) {
```


---
## Patch 48 of bug id Chart25
### Patch Diff Hash-SHA-256:

83ff2a24b5cf209841812c65fab07f50bd3ad9e7c77aa202353adfc12898dda7

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -27,6 +27,7 @@
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
 		if (masd != null) {
 			result = masd.getMean();
+			org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data = new org.jfree.data.KeyedObjects2D();
 		}
 		return result;
 	}
```


---
## Patch 49 of bug id Chart25
### Patch Diff Hash-SHA-256:

7bb7a9b19064367f94da813e255fe70bf2c5ecfddd53b9c6bbdc4de309b74256

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,31 +1336,10 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
-				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
-				}else {
-					for (int column = columnCount - 1; column >= 0; column--) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}
-					}
+			for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.rangeAxes.size()); i++) {
+				org.jfree.chart.axis.ValueAxis axis = ((org.jfree.chart.axis.ValueAxis) (org.jfree.chart.plot.CategoryPlot.this.rangeAxes.get(i)));
+				if (axis != null) {
+					axis.removeChangeListener(org.jfree.chart.plot.CategoryPlot.this);
 				}
 			}
 		}
```


---
## Patch 50 of bug id Chart25
### Patch Diff Hash-SHA-256:

366a2628b1b4f74caf578a91b595456384c4f7c433ce5c7fbbfc5a4accd65397

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1339,14 +1339,10 @@
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
+						if ((getRenderer()) != null) {
+							getRenderer().drawBackground(g2, org.jfree.chart.plot.CategoryPlot.this, dataArea);
 						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
+							drawBackground(g2, dataArea);
 						}
 					}
 				}else {
```


---
## Patch 51 of bug id Chart25
### Patch Diff Hash-SHA-256:

5b504c80cacff9dc2cd459f2ffad20cbbe2aaff57844c9df0198578ec17cba26

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,8 +1340,11 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
+							for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.rangeAxes.size()); i++) {
+								org.jfree.chart.axis.ValueAxis axis = ((org.jfree.chart.axis.ValueAxis) (org.jfree.chart.plot.CategoryPlot.this.rangeAxes.get(i)));
+								if (axis != null) {
+									axis.configure();
+								}
 							}
 						}else {
 							for (int row = rowCount - 1; row >= 0; row--) {
```


---
## Patch 52 of bug id Chart25
### Patch Diff Hash-SHA-256:

b6b26aa0a3890cff34f77c779987e405a143945551162ff9d7d7f408af702fc3

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,8 +1226,8 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+			for (int i = 0; i < (org.jfree.chart.plot.CategoryPlot.this.renderers.size()); i++) {
+				drawDomainMarkers(g2, dataArea, i, org.jfree.chart.util.Layer.BACKGROUND);
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```


---
## Patch 53 of bug id Chart25
### Patch Diff Hash-SHA-256:

73b557557f310ad077a01f0c15716cfb350a0db899a96866b407b40fd9ef317e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1339,14 +1339,14 @@
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
-						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
-							}
-						}else {
-							for (int row = rowCount - 1; row >= 0; row--) {
-								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
+						if ((org.jfree.chart.plot.CategoryPlot.this.backgroundDomainMarkers) != null) {
+							java.util.Set keys = org.jfree.chart.plot.CategoryPlot.this.backgroundDomainMarkers.keySet();
+							java.util.Iterator iterator = keys.iterator();
+							while (iterator.hasNext()) {
+								java.lang.Integer key = ((java.lang.Integer) (iterator.next()));
+								clearDomainMarkers(key.intValue());
 							}
+							org.jfree.chart.plot.CategoryPlot.this.backgroundDomainMarkers.clear();
 						}
 					}
 				}else {
```


---