
# Patches of Chart25 from Defects4J 
Total patches 454
## Patch 1 of bug id Chart25
### Patch Diff Hash-SHA-256:

8b80065eee52522604b7841ec02ad4922e90a70e20695b681b073958f77f0e13

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (org.jfree.chart.plot.CategoryPlot.this.domainGridlinesVisible) != (drawSharedDomainAxis); pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart25
### Patch Diff Hash-SHA-256:

b7b05d9837e9d319ed35929319fff70866b243b52e4588ff1d16e08a0758924c

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (rowCount < rowCount) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart25
### Patch Diff Hash-SHA-256:

fec8d4299bade5b552bce0550069276c2c67028bd640c35fa1b932ff91e371b5

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1329,7 +1329,7 @@
 		org.jfree.chart.renderer.category.CategoryItemRenderer renderer = getRenderer(index);
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
-		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
+		boolean hasData = !(DEFAULT_RANGE_GRIDLINES_VISIBLE);
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart25
### Patch Diff Hash-SHA-256:

0a8f941d5dceb1fe1e7d78d462211a929f93b73d6f1a0d006d2826041ff3bc2a

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return true;
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart25
### Patch Diff Hash-SHA-256:

4eb1065799635a38900040e0b96d4f332ead64debb6c78729097bb33274ec2cf

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (rowData == null) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart25
### Patch Diff Hash-SHA-256:

981407d50fdff5b11693ae5835c08c18b377f2699b50bdadff401b8aca4325ce

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((columnKeys) == (org.jfree.data.KeyedObjects2D.this)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart25
### Patch Diff Hash-SHA-256:

f43c7596daf90ed2c90c2cf897281997ed1c806f80d14284b727690331e37ecc

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; rowCount < rowCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart25
### Patch Diff Hash-SHA-256:

7a84fb3106f746bd15117877c3045c9bb9b7cbe7f78e791e5ab447ce757c0a75

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			columnKey.equals(columnKeys);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart25
### Patch Diff Hash-SHA-256:

abc86ef04ab4963c5b062b1f4cb7f9ccf8500e7a4ec0252097c3f7e60233145f

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rows) == null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart25
### Patch Diff Hash-SHA-256:

5a6289cc5be20737c47b4b4b47bae2436fe91ab1e963b3f2487aae2368cce0b0

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (columnCount < rowCount) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart25
### Patch Diff Hash-SHA-256:

6701a2f5e4ad0c0bd61444987a54bb4b427460df685f7fbe93e7ee16ec5e9f4a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			org.jfree.data.KeyedObjects2D.this.columnKeys.remove(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart25
### Patch Diff Hash-SHA-256:

ca6cf836bc2cf7c2c1c7da3ded093f6055b011badf62545bca16bbc444192eac

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = (domainGridlinePaint.equals(domainGridlinePaint)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart25
### Patch Diff Hash-SHA-256:

5f7e6499af24a9f4eb7a915c49baf35f0f1b2edec08c278b7fc0f000e8aa7ba4

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1329,7 +1329,7 @@
 		org.jfree.chart.renderer.category.CategoryItemRenderer renderer = getRenderer(index);
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
-		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
+		boolean hasData = !(org.jfree.chart.util.ObjectUtilities.equal(dataArea, dataArea));
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart25
### Patch Diff Hash-SHA-256:

2be60382e26e5b3ab2e68005654df09b72096720821154855fa2215f0562cedc

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = ((rangeCrosshairStroke) != null) && ((DEFAULT_GRIDLINE_PAINT) != null);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart25
### Patch Diff Hash-SHA-256:

6629a8b90b8152bd5857faa9fc68e2be7bbf8714b708794bb3be8e3bef0dcfbe

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) > (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart25
### Patch Diff Hash-SHA-256:

56d28f393839a04eaa3ba6d401abbf09dfbf054761f93d558116a5062dd3ade7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (row < row) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart25
### Patch Diff Hash-SHA-256:

c7df681998835f67d47abb7b59034d9dc57a7995266330f96ea1a98aa7c662c9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = (org.jfree.chart.plot.Plot.DEFAULT_BACKGROUND_PAINT) == null;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart25
### Patch Diff Hash-SHA-256:

0c83831d82c4d80a1fe5026ec764b38bb04b03947104ac5ebe6d0efd43dee205

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((rowKeys) == (org.jfree.data.KeyedObjects2D.this)) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart25
### Patch Diff Hash-SHA-256:

1333e8566050480c492092d44572502a151409fb96bae53fe08c29d885e0fcc5

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				org.jfree.chart.plot.CategoryPlot.this.drawSharedDomainAxis = rangeCrosshairLockedOnData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Chart25
### Patch Diff Hash-SHA-256:

95cfc349199c14568826dc1791bc7aa208e875a2966527c19a218d201efe4e6f

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (org.jfree.chart.plot.Plot.DEFAULT_BACKGROUND_PAINT) == null; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Chart25
### Patch Diff Hash-SHA-256:

58e1617436c5aa1858b5322fb18f1e4321fa73e3323babcf630c5591f996f642

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((minimumRangeValueIncStdDev) > (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.maximumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Chart25
### Patch Diff Hash-SHA-256:

78bb29903494f6cba9c7933e844cf9cf7d04cc6dcd77b3366e9e070a06d2d424

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (result != null) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Chart25
### Patch Diff Hash-SHA-256:

802b13c3f856615ab1d3b7cd9e9fa6dddd769f7c9bb1394a5e23a8111bd188ce

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (result instanceof org.jfree.data.KeyedObjects) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Chart25
### Patch Diff Hash-SHA-256:

811cab11cd7c280b51ec0e06ecd6d3d874f6aa08695cab2fd51de04283e767be

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValue)) || ((maximumRangeValueIncStdDev) < (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Chart25
### Patch Diff Hash-SHA-256:

66fe84d7a147df5729a04dbe4f7d469b4ff7445450c5c4b8b1e20a83fd72a3f7

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (dataset instanceof org.jfree.data.RangeInfo) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Chart25
### Patch Diff Hash-SHA-256:

43fc08d39be9e813931e59a13130b0194c893aed9e87a654eb474824a70fe633

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; (rowCount == 0) || (columnCount == 0); r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Chart25
### Patch Diff Hash-SHA-256:

abca41ba4aa621490c32f215f071ed82b8993250d327a8e4aa68f1dcc50ba994

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((isRangeCrosshairVisible()) && (rangeCrosshairLockedOnData)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Chart25
### Patch Diff Hash-SHA-256:

7e09107c48219eda6dcf5fdeb41f570e36fd12e8a2f0415cc7393d4c31e639f6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (getRenderer()) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Chart25
### Patch Diff Hash-SHA-256:

8651e2f98a9e3aa755b4e0230483fb96b92af2b01a4e6a20ee7e20e6f8c9fed9

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rows) instanceof org.jfree.data.KeyedObjects2D) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Chart25
### Patch Diff Hash-SHA-256:

b583aa3796ae71ad2a8062dd0a3817face0bd9ccc1a1c83b3928f704079a3875

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; columnCount == 0; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Chart25
### Patch Diff Hash-SHA-256:

939432c84cb2153af5975731b1f1603f6b2f7bc964c5c63c8299191ed6b5abed

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((columnIndex >= 0) && (columnIndex < (columnKeys.size()))) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Chart25
### Patch Diff Hash-SHA-256:

a5b4e3dfdcada71c557180a99d2c2c8ef79152e95a304b030cf83e969afbca1f

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rowKeys) instanceof org.jfree.data.KeyedObject) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Chart25
### Patch Diff Hash-SHA-256:

97b18b154b6f118f57e3a8421c764a276107d99d7360442291c9368eb9551ddb

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				org.jfree.chart.plot.CategoryPlot.this.rangeCrosshairVisible = org.jfree.chart.plot.CategoryPlot.DEFAULT_CROSSHAIR_VISIBLE;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Chart25
### Patch Diff Hash-SHA-256:

293688554cb0957d3d1a104fd576515fb30b3f89d6c666b2fe63e127906ac84c

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((maximumRangeValueIncStdDev) < (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Chart25
### Patch Diff Hash-SHA-256:

2a8a68417d24e7294bd2bb705683ce1ec33a145a19cbf0b78a159a14f15d7550

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; columnCount < rowCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Chart25
### Patch Diff Hash-SHA-256:

adb6bc2523bef176c366f30f93de2916de37f0cf8380fdb4293a19109766f7b2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (weight) < (org.jfree.chart.plot.CategoryPlot.this.datasets.size());
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Chart25
### Patch Diff Hash-SHA-256:

6775c49100b5502fe61c4344bcced4f04722024abb24eba24894c4abb894f455

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return !(dataset instanceof org.jfree.chart.renderer.category.BarRenderer3D);
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Chart25
### Patch Diff Hash-SHA-256:

04f151669c9490ce71996bbe9bd3a69b03e27f0305962d22a1bf99f35b42fd7c

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			rowKeys.contains(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Chart25
### Patch Diff Hash-SHA-256:

c29f51dfa6dd84c176c321cc16569a7ba535ac4b6336a2be98edff5bcdd315c2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (hasData && ((backgroundDomainMarkers) instanceof org.jfree.chart.labels.BoxAndWhiskerToolTipGenerator)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Chart25
### Patch Diff Hash-SHA-256:

cc3b32572405f4b163c5a81c063db80f7630585fb243ac5bd65339e7d03a09e7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			columnKey.equals(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Chart25
### Patch Diff Hash-SHA-256:

a91b170b26ed5c00088f0cd4a8740d7f6b59996a383816f50d5f11f27b23b1ee

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (super.equals(data)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Chart25
### Patch Diff Hash-SHA-256:

762d81bdd87d4233a36363e37916a2e9b976691d87fa2d31b1bf881fb682ec05

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			super.equals(row);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Chart25
### Patch Diff Hash-SHA-256:

576826c64a4774f090e428013530bdc6bdc7052745115084de4b02c82d889c24

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (dataset instanceof org.jfree.data.time.Minute) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Chart25
### Patch Diff Hash-SHA-256:

47127a24057ddc5b059974bc02275d78c725689e1c2fdeaf8e5cbf17676fa1b1

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((rows) == null) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Chart25
### Patch Diff Hash-SHA-256:

d6453a399788e86ef432b804f8b2beeb7a9dacf45ab14e5facde56a21edda27e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((anchorValue) >= 0.0) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Chart25
### Patch Diff Hash-SHA-256:

45b7679fb121aa863878e0839326300d8c88e24f9fd21e9241bce76f506e0560

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				b1 = false;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Chart25
### Patch Diff Hash-SHA-256:

35748623e8477214794c5f7702d6be0eb01d3e87666eef634e9bfcf8c891ce85

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; ((anchorValue) / (anchorValue)) < (anchorValue); pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Chart25
### Patch Diff Hash-SHA-256:

dd9a6bc50a7c7af6fbaa2ed9f54f6e97f3f536e519491b6a49d6df11fcf85b08

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) < 1) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Chart25
### Patch Diff Hash-SHA-256:

7d03a42fbefc7750d6e15761df8f97dd5b0d68c2ddb28b15afc66419495e66b3

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (super.equals(rowKeys)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Chart25
### Patch Diff Hash-SHA-256:

7245965d75d62cedd3be9b556deeddc2eb6612b859c96ab375c7d56ef54d2451

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.data.xy.XIntervalSeriesCollection) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Chart25
### Patch Diff Hash-SHA-256:

2720470e32888e7dd2bd82b1d2eb8a1bf8ba46667c26a5a3da1e76e2a9dea7f2

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (row != 0) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Chart25
### Patch Diff Hash-SHA-256:

bca2f1ffef187860d8eec1c070e8dd63c778e3eadeea6fd84290cc7c283590e4

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((info != null) && ((info.getOwner()) != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Chart25
### Patch Diff Hash-SHA-256:

fac1e148250cf3d259bb38e8cfd04564197d5aaf124cec6b6b48fbf673b6787a

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (dataset instanceof org.jfree.chart.block.EntityBlockResult) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Chart25
### Patch Diff Hash-SHA-256:

7bed77c0bb61aa28f57364e70fa6015e9c67eb3e5de6d79395ca3b71c3351291

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (rangeCrosshairValue) < (org.jfree.chart.plot.Plot.ZERO.doubleValue()); column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Chart25
### Patch Diff Hash-SHA-256:

7a3c544f2285a7f99b0fcd77c42e2f19df6c74645f11f62708a3cc3dfe1a960e

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((((maximumRangeValue) + (minimumRangeValueIncStdDev)) >= (maximumRangeValue)) && (((maximumRangeValue) + (maximumRangeValue)) >= (minimumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Chart25
### Patch Diff Hash-SHA-256:

62dc7aa9701dafd02c3e1d374bff3de4a8646789f506e686c715139cf5a13b5e

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -215,7 +215,7 @@
 	}
 
 	public static boolean isEmptyOrNull(org.jfree.data.category.CategoryDataset dataset) {
-		if (dataset == null) {
+		if (!(dataset instanceof org.jfree.chart.axis.CategoryLabelPosition)) {
 			return true;
 		}
 		int rowCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Chart25
### Patch Diff Hash-SHA-256:

6af92a0495892ac391cc3a0dbcd73e492655a97d6411a14a25ee0f8cbff1ada7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.data.xy.IntervalXYDelegate) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Chart25
### Patch Diff Hash-SHA-256:

fe7f7955bfaaa494d4f0fb1cf5319c05d4c641cfac72295cc0090e715df5927a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = !(super.equals(rangeGridlineStroke));
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Chart25
### Patch Diff Hash-SHA-256:

3af4e77f554187c9020dcbe5dfa916aac7c5e57ffda307be3c2082ccd15539d6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((rangeGridlinesVisible) || b1) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Chart25
### Patch Diff Hash-SHA-256:

df61c687f2857599d0a8055f2ae13f4135de1fa634f0068d00f789af7147c7a4

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (column > 3) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Chart25
### Patch Diff Hash-SHA-256:

5bcb2fba35b48bd27eaee7cf17ab60f0f1256a98ad8e32cefb9ff57ea0927164

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (dataset instanceof org.jfree.data.xy.DefaultXYZDataset) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Chart25
### Patch Diff Hash-SHA-256:

223656c92cf5997ce20bbfd084c2753f1aa2bd1f92fb95c0cfbb45075fb238c2

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((super.equals(rows)) && ((rows) instanceof org.jfree.chart.needle.ShipNeedle)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Chart25
### Patch Diff Hash-SHA-256:

62ee94c453e0503896552ac66624b7d6bda5694d67681389243473d92e6cf6b8

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((maximumRangeValueIncStdDev) < (minimumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Chart25
### Patch Diff Hash-SHA-256:

934288a5376c5ed97e7e6cdc84144b8a33053f3890a2185d6a7cd2cf7058b140

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (org.jfree.data.time.SerialDate.isValidWeekdayCode(index)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Chart25
### Patch Diff Hash-SHA-256:

b707893de81a40fb739d54994199c407147c47e7acdc3bbf60ba8e35ecd921a4

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) <= passCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Chart25
### Patch Diff Hash-SHA-256:

241799509a67cefce79a525f1e6488538b9a75fdec6270810cdc3fb8f6c9af22

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -215,7 +215,7 @@
 	}
 
 	public static boolean isEmptyOrNull(org.jfree.data.category.CategoryDataset dataset) {
-		if (dataset == null) {
+		if (!(dataset instanceof org.jfree.chart.axis.NumberTickUnit)) {
 			return true;
 		}
 		int rowCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Chart25
### Patch Diff Hash-SHA-256:

43a60966c20e26e5fcb8ef557d782c6511a12387047588b49cf5403a44ad66cb

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = org.jfree.chart.util.ObjectUtilities.equal(DEFAULT_CROSSHAIR_STROKE, rangeGridlineStroke);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Chart25
### Patch Diff Hash-SHA-256:

5055824c603cf8b15bb7042f3b50e08692f0962a1d2f6b1debf0110e54cdad82

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				rangeGridlinesVisible = (rangeCrosshairValue) > 0.0;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Chart25
### Patch Diff Hash-SHA-256:

cba606137ac785d42c0614a9a282b4ef771181a2db3258bb1f188964fafd0d1d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (((rangeCrosshairValue) > 0) && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Chart25
### Patch Diff Hash-SHA-256:

28c50348d232e8ca8cc91cf23cd50b3fbda4871f6b0167af55ec9ba523128035

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = ((((weight) < 1) || (((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) < 1) && ((weight) < 5))) || ((weight) < (4 - (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW)))) || ((rangeCrosshairValue) >= (rangeCrosshairValue));
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Chart25
### Patch Diff Hash-SHA-256:

5a60126e64680c2629a9f68a9361d94a325beb8d83495451273aa9f95176a24e

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rows) instanceof org.jfree.chart.plot.DefaultDrawingSupplier) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Chart25
### Patch Diff Hash-SHA-256:

fe37310358f6e178dbf00585280d7f623b6325b4227972587ee549e8debf16a7

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) > 1;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Chart25
### Patch Diff Hash-SHA-256:

dc6fc9f05d1a2c960d40edaa2e06eb79f3f2ede8294953ed0ed5bd2042494c60

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (columnKey instanceof org.jfree.chart.renderer.xy.XYErrorRenderer) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Chart25
### Patch Diff Hash-SHA-256:

791240b02d549c1a6ec345acfe6e4c6d656a0b950a210e7dff8c5c832c9a3d16

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (!(columnKey.equals(columnKey))) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Chart25
### Patch Diff Hash-SHA-256:

cac12ceeff4bb046cbf146db252cdca7888c0a7212e0e75de92e1aa7dfaf3aeb

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (object instanceof org.jfree.chart.util.RectangleEdge) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Chart25
### Patch Diff Hash-SHA-256:

da5e70684fa5ce9e26b77c6f18c4225f86a37e24761928d3f5b20520fd6a0d0a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				b1 = !b1;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Chart25
### Patch Diff Hash-SHA-256:

d9af49e843ce2a0d9c0111b5a9ff8a7709710145ae3c55bb0e0224c6b03113b9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = !foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Chart25
### Patch Diff Hash-SHA-256:

fab9847956bf29fc33c65d11dbab5cdb8c3726974a69b271481cb0068aab2741

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (index == (-1)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Chart25
### Patch Diff Hash-SHA-256:

e4e4593630feb00f2b4f0b51a26926b2eca89045546794c85e8523c01aa034a6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (0 == (anchorValue)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Chart25
### Patch Diff Hash-SHA-256:

62259fecac1d27d70944b94e852915862e6bfb1e77c21853f06d56616e4c1969

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) < 10) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Chart25
### Patch Diff Hash-SHA-256:

3cf575d6427e0761a43582e6325daaef8e8dfe012eb8993bdbad17dab37745c6

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			columnKeys.contains(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Chart25
### Patch Diff Hash-SHA-256:

de578eadd4279ed12a92537b6a4c1ffcbceeb56a9807d0baa5e1c15b47cf91d3

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (row != row) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Chart25
### Patch Diff Hash-SHA-256:

bc0c8d8965341bcccef018b77c163bc4f89563c5c82f35c3fee186a789d2c4d6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (((rangeCrosshairValue) + (anchorValue)) > (rangeCrosshairValue)) && (!(drawSharedDomainAxis)); row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Chart25
### Patch Diff Hash-SHA-256:

b36f0d99ef039e9b3f503c2fc1ad2a0bbbe8c4c240145d7c00b1a74b7aaa0517

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((weight) == (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Chart25
### Patch Diff Hash-SHA-256:

e9e29cb69f50c6f84a82d2a34085078d479d80d0077691b1ad497837bd7b2508

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (column > 1) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Chart25
### Patch Diff Hash-SHA-256:

f71263e94b6dd425411398b828c6a4b090368d0d4d794671ca31fceaca4d935f

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (columnCount > 0) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Chart25
### Patch Diff Hash-SHA-256:

ff9bd504fd7a9cc0ac7ab5845ddc01101f25455c07c60844078ab0a9f6b9281f

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (columnCount <= 0) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Chart25
### Patch Diff Hash-SHA-256:

a0d2b0c5d51b5def4b4b1112c75a9de05471250098cc7053431494bbf84c7c8e

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((rows) instanceof org.jfree.data.time.Second) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Chart25
### Patch Diff Hash-SHA-256:

d4041fc682a3f6350890a427d2f1de203f69cbad7dffde3ee5270117a48854af

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (columnKey == null) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Chart25
### Patch Diff Hash-SHA-256:

32b543beda412d230ec50ee8eae9bac1dca93440f18be40ddf792259be2f4e61

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = area.contains(org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW, weight);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Chart25
### Patch Diff Hash-SHA-256:

3123ef84de09ef064b7aa8d7088d06f05fe0b59912b8ec30ed8fdea7864e12cd

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (rangeCrosshairValue) < (rangeCrosshairValue); pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Chart25
### Patch Diff Hash-SHA-256:

3050bbce890252a0fc77f4a95855c42831bd27b339938c246bd4356820ccc617

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (org.jfree.chart.plot.Plot.DEFAULT_LEGEND_ITEM_BOX) instanceof org.jfree.chart.renderer.category.BarRenderer; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Chart25
### Patch Diff Hash-SHA-256:

44ddd01fbf67af0a62374968b46c8c25451adaea50175cf6aacba17d1355261c

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowKey instanceof org.jfree.chart.renderer.xy.XYDotRenderer) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Chart25
### Patch Diff Hash-SHA-256:

5e79a50c0cff67d87dd6f5585bf36bd3eb6b977741255ba4629c78ebc6c8c041

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			super.equals(object);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Chart25
### Patch Diff Hash-SHA-256:

f5907b0b2eba5287114af241648dca288d33675c51c5c0ea6e708025702a1ae0

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (renderers) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Chart25
### Patch Diff Hash-SHA-256:

4811631984b353d3971a8f6139003a9d1bf242c0886d37551cd487a9cbb4b38a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (column < column) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Chart25
### Patch Diff Hash-SHA-256:

814f18aad19c53e39ccb2cbcc89dbaaa1df5f6346e541ca0c98ae369b2fb91c2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; rangeAxes.equals(backgroundRangeMarkers); i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Chart25
### Patch Diff Hash-SHA-256:

08cd276478a9553c8dc47a48748748ac4a4ebfbc095e1d262ae2bc571c569f13

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (super.equals(masd)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Chart25
### Patch Diff Hash-SHA-256:

4c76969536fb14c1e257798d7df9a3d19e647ceb4d7c87412a9403e5036e63a5

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return !(dataset instanceof org.jfree.chart.block.GridArrangement);
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Chart25
### Patch Diff Hash-SHA-256:

a5a2fc2cafc18afbad79d380d1a45ab64cbfc6ac06e35720646b4fdd4b67a757

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (rangeCrosshairPaint) instanceof java.awt.GradientPaint; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Chart25
### Patch Diff Hash-SHA-256:

6ead9c136bcc8ae02309d77e37904e21abd44dd56836adb1ca9929524001b394

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (super.equals(dataArea)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Chart25
### Patch Diff Hash-SHA-256:

6aa93f0a17fb9524fffc195935cb459c576a0b4a228aef90ee82ec9c41b43ae1

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; columnCount < 0; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Chart25
### Patch Diff Hash-SHA-256:

edd81c93e0ef3861c0374ea29d48e3cd84b27993b1a496f78efef049af836117

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((rowKeys) instanceof org.jfree.chart.renderer.xy.XYAreaRenderer) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Chart25
### Patch Diff Hash-SHA-256:

8811fc495752549d8e1321afe5e6e28d783ebf272cf7435b3ad4c459e72e6d7a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (!(org.jfree.chart.util.PaintUtilities.equal(org.jfree.chart.plot.Plot.DEFAULT_BACKGROUND_PAINT, rangeGridlinePaint))) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Chart25
### Patch Diff Hash-SHA-256:

8c3c3e4b69de5a2caf2461c68bd41ac96c6b9a5191941876bbe6a31f4dfc95f3

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (!(dataset instanceof org.jfree.chart.plot.RingPlot)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Chart25
### Patch Diff Hash-SHA-256:

6118f5e93766b9d52a4d9058f4080bafd8a76b5948a6093a5d933790ea27e5e0

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rows) instanceof org.jfree.chart.plot.CategoryPlot) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Chart25
### Patch Diff Hash-SHA-256:

fbf28b8a9f61b6bf6cbd15c0e9678af5c11027d0c3285c2a92770b2bdee9fe38

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = !(java.lang.Double.isNaN(((anchorValue) + (rangeCrosshairValue))));
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Chart25
### Patch Diff Hash-SHA-256:

ebd2d592f2bcdeb41358a19b7a021b3da67531c59be4bed7131618c0130747e9

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (columnCount > rowCount) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Chart25
### Patch Diff Hash-SHA-256:

4318d49c596d9997dd61e5159fb44e683dfdcef926ae5efbd1473819ec540011

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (rowCount < 6) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Chart25
### Patch Diff Hash-SHA-256:

daa97206ef74a0ea3730f0799643dfa2aa08ce7835ce86647a5b777be427b1d9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (org.jfree.chart.plot.Plot.DEFAULT_BACKGROUND_PAINT) == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Chart25
### Patch Diff Hash-SHA-256:

87edbda1d686c3e892bdc576c120355366070b03ec04e1f54b8bceb3323a1c1e

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			columnKey.equals(rowKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Chart25
### Patch Diff Hash-SHA-256:

ff92e8c849e5d324b2af94a05c2b57e0c6f419701a0275fa4a93fa1bda4bcdaa

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; org.jfree.chart.util.PaintUtilities.equal(DEFAULT_GRIDLINE_PAINT, org.jfree.chart.plot.Plot.DEFAULT_OUTLINE_PAINT); i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Chart25
### Patch Diff Hash-SHA-256:

280630e952a8a2a1224b21886182f840ec783bc720dd9eb88b774579c242e675

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (org.jfree.chart.plot.Plot.ZERO) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Chart25
### Patch Diff Hash-SHA-256:

3c00f3034da4a4341dd595ff8c808819ed206e07b8b436ee3fba8c931d0029f7

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; dataset instanceof org.jfree.data.xy.OHLCDataItem; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Chart25
### Patch Diff Hash-SHA-256:

9218112d16cbbedd5749aa8ba81f9fa5f736b1a1ebec0ada8c69533af0988eb7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((column > column) && (column <= row)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Chart25
### Patch Diff Hash-SHA-256:

975c56e2af4d6bb1105c1039098fff9f1263a26da3fc4bf7a895a08a60dba844

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowIndex < (columnIndex - 1)) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Chart25
### Patch Diff Hash-SHA-256:

c5d32c2bfb69ea92c83eb567b296bdbcea8f71ed3bbcd5ab6096e954c87ea1b6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (weight) < 0; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Chart25
### Patch Diff Hash-SHA-256:

045fcb744b46c2a98e6bdb08099e040a077c28517fe9d823130268c57a496219

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (org.jfree.chart.plot.Plot.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.data.time.TimeSeries; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Chart25
### Patch Diff Hash-SHA-256:

1f2ed7a24854ff9d1a8ab05cbe9d1f72ea75783c84581e35290751c33204273e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (dataArea.getWidth()) < ((org.jfree.chart.plot.Plot.DEFAULT_BACKGROUND_ALPHA) - (dataArea.getX())); column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Chart25
### Patch Diff Hash-SHA-256:

9352303a5aeaffc2c52141e3f54cd1910933cd83baffb49230d98aad7c1b4ebe

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((columnIndex > columnIndex) && (columnIndex < rowIndex)) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Chart25
### Patch Diff Hash-SHA-256:

1212f6a58b35d183c65abf526907e753e23560bed8d39383c237b3301be10b5c

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((columnKeys) instanceof org.jfree.chart.renderer.AbstractRenderer) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Chart25
### Patch Diff Hash-SHA-256:

7dfc32c98af35eaef505c287fb0b0f0943cea07d71522969741d68f271124a0e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) >= 0;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Chart25
### Patch Diff Hash-SHA-256:

ad1d4097e91aa1be886d4a501b939dddf1d843b610e46eb3a51950d3fb4699ec

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (area != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Chart25
### Patch Diff Hash-SHA-256:

adaa45981c9dfa734c0c6e649db8bfac197cd2d3e3a6ecbbb520155602586142

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (object instanceof org.jfree.chart.plot.MultiplePiePlot) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Chart25
### Patch Diff Hash-SHA-256:

cf9e186dbd6a643eb5b537924cdbb3f4d954e5c00275045f6f3bb6bfe118bbd4

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (dataset instanceof org.jfree.chart.block.AbstractBlock) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Chart25
### Patch Diff Hash-SHA-256:

0353cb36a7dfad0d8f5ff4b049bb6e482b4a9dc21a7f605ce4df6f4116808fc0

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return !(dataset instanceof org.jfree.data.xy.DefaultOHLCDataset);
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Chart25
### Patch Diff Hash-SHA-256:

820158225a8c178072183e557a01638f245ce9199b8f8de8c201fe4778a093ad

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (super.equals(columnKeys)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Chart25
### Patch Diff Hash-SHA-256:

167a3ee6f69c24f9623e1a3fd84159776afad73b9961744deda4deae5d3621b7

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; rowCount < 1; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Chart25
### Patch Diff Hash-SHA-256:

cad637c6cb072ae327c6acb22056d5d9516db4b044c51b55ca26ba0c7a79c1c7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((columnKeys) instanceof org.jfree.chart.entity.CategoryItemEntity) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Chart25
### Patch Diff Hash-SHA-256:

808589ad0a1abbf4563a87250adc508a2a34b64a68ae0c193698c609fe17509d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; (DEFAULT_VALUE_LABEL_FONT) == null; i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Chart25
### Patch Diff Hash-SHA-256:

2b7ee3b81b52892df5ef2a856799b71775a54928de63bd4a6c9da6f15ab1bf71

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; dataset == null; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Chart25
### Patch Diff Hash-SHA-256:

b02bc74abdc2fd4c6213291dfa0cc3fb1ae15f601e8c4603d72706d116cb85ef

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((rangeCrosshairValue) >= (anchorValue)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Chart25
### Patch Diff Hash-SHA-256:

2f6b1f3229494f7598be4add3bc2922e2acfacd45901e81aa03305991b7681ff

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.chart.needle.ShipNeedle) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Chart25
### Patch Diff Hash-SHA-256:

ba5bedef5cf65bdfd7a6df9a22ea8bf019060add01919bf2d6d92699f9d3184c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (org.jfree.chart.plot.Plot.DEFAULT_OUTLINE_STROKE) == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Chart25
### Patch Diff Hash-SHA-256:

c4e358de28799f8e232ae0dc245dfe96ba339df18674a1f400cc6fae7d5712ae

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (org.jfree.chart.plot.CategoryPlot.localizationResources) instanceof org.jfree.chart.block.EntityBlockParams; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Chart25
### Patch Diff Hash-SHA-256:

4cee12023c2bd52e0b03409a61a82ec56ed3eb2ae0d69350dd772bc3c9edc956

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return rowCount < 2;
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Chart25
### Patch Diff Hash-SHA-256:

cdaa50b5303288239aa77e7568d7956ca7e2322df4a2ebc68e806ed5d386958e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (org.jfree.chart.plot.Plot.DEFAULT_BACKGROUND_PAINT) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Chart25
### Patch Diff Hash-SHA-256:

509a0a28ccbc16d3f5fb706853abc09e81d6a4cdceb40325a33691cb2907afdd

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (backgroundRangeMarkers) instanceof org.jfree.chart.axis.Axis; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Chart25
### Patch Diff Hash-SHA-256:

64c5ba9454480a47e6c4e81b40d0680bed8ac82fdf2b78e39eb4f3d76491a2ef

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (columnIndex == 0) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Chart25
### Patch Diff Hash-SHA-256:

10c1b32c2983905f3944ccd1e17fb11557a3e02ffd0a3647e14f0ddaaf317959

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (row == (-1)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Chart25
### Patch Diff Hash-SHA-256:

e78506cb5e6eaca874f0aa75eff67e51fc05bc5208834e93c4acd4decaff77ab

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; columnCount < 0; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Chart25
### Patch Diff Hash-SHA-256:

aee38c486fd7ec2c22abc881db0519f0fe637689ccc4db8c92bde391b3e1142e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (DEFAULT_VALUE_LABEL_FONT) instanceof org.jfree.data.general.PieDataset; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Chart25
### Patch Diff Hash-SHA-256:

53a04a0329149094eba3f7d146634bedefcf0615ac100d0ff646bd63ba8b6a4d

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.chart.labels.StandardCategorySeriesLabelGenerator) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Chart25
### Patch Diff Hash-SHA-256:

0f0942eafb21b3731d6fe06a4674103b76a39ce2df58d396ef81a1bbcf52425e

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowKey instanceof org.jfree.chart.plot.Plot) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Chart25
### Patch Diff Hash-SHA-256:

6dfe865595f9a0cdcbe35a5939131919301e9000af6b461143f14b24913e2972

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; dataset instanceof org.jfree.data.time.ohlc.OHLCSeriesCollection; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Chart25
### Patch Diff Hash-SHA-256:

98aa17e4cbb41ebb495fcd978a9931207225e225dff87e43aa4ba5a4790c33f1

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (column < row) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Chart25
### Patch Diff Hash-SHA-256:

346a0d8bd1ba482596d7612ef7b88460989b4eaec79b4c694eefa8390faf88f3

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (!(dataset instanceof org.jfree.data.xy.DefaultXYZDataset)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Chart25
### Patch Diff Hash-SHA-256:

1ff519a973bd7d05eaab05ba3552ae1cadcbcefdc9f478b7f27f2bda94934922

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowIndex < 0) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Chart25
### Patch Diff Hash-SHA-256:

6012fe1c8de03d189e15993d1a2042b49606ae1fa9699b1785aefac8d41a3771

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; info == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Chart25
### Patch Diff Hash-SHA-256:

7e4c064aa25159c26471fd2a94d6b4250390adf805f098570cf5f323119fef50

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((columnIndex == 0) || (columnIndex == 0)) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Chart25
### Patch Diff Hash-SHA-256:

24d675794414cb77a6fc9160c087e5061f35bd9adf3f38d78a304c1ae9c90ab2

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			rowKey.equals(rowKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Chart25
### Patch Diff Hash-SHA-256:

f87f102b56799d45866990a5c577590aa3d1020e489a5122b218b1e76b5aefa8

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (DEFAULT_VALUE_LABEL_FONT) == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Chart25
### Patch Diff Hash-SHA-256:

6301e4b484f0366cc6ca9abdb74c67fc916193e78af08c2a4c19a0c58f1682be

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; dataset instanceof org.jfree.data.xy.XIntervalSeriesCollection; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Chart25
### Patch Diff Hash-SHA-256:

eb890ef3fbb7909d720cf5feef18eb981d959a908063597585ab2f06dd7468f9

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; dataset instanceof org.jfree.data.category.IntervalCategoryDataset; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Chart25
### Patch Diff Hash-SHA-256:

1d5137ea4b0d8f36f821070294fed8646947f9df545ab67552b3b5f204fa94c4

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (column > 3) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Chart25
### Patch Diff Hash-SHA-256:

922777a763b117110c150a2c7c90f83c760707277aeeb7ee7a1c5fa6d19c7a57

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (org.jfree.data.time.SerialDate.isValidMonthCode(columnIndex)) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Chart25
### Patch Diff Hash-SHA-256:

d864bd3016f3b18dfd7dd7f1f8ba48a15249a422005139bd809bf9555a51412d

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.chart.title.LegendTitle) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Chart25
### Patch Diff Hash-SHA-256:

0f54601848ee17df6222bece605477588a6d125d53f6ccf7bf8e7bb5ada1be4c

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -215,7 +215,7 @@
 	}
 
 	public static boolean isEmptyOrNull(org.jfree.data.category.CategoryDataset dataset) {
-		if (dataset == null) {
+		if (!(dataset instanceof org.jfree.chart.urls.CustomXYURLGenerator)) {
 			return true;
 		}
 		int rowCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Chart25
### Patch Diff Hash-SHA-256:

2e7a5b3bb982891f267136695341a97c0c51145ed1a5aeda7bd1bbb5727b3d8d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (anchorValue) <= 1;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Chart25
### Patch Diff Hash-SHA-256:

e9df6096454486d26007c8663ccb71d36b8809c0145befb32572ee8f5fee16e9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (annotations) != null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Chart25
### Patch Diff Hash-SHA-256:

26580010cc47208065daec1b63b13d860cefb317ee63f308139e232948aed8ef

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.data.xy.YIntervalSeriesCollection) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Chart25
### Patch Diff Hash-SHA-256:

d262685f7e9b95afefdda3974be924c252a0543480d88f7facda547c73cc2ef2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) < 0) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Chart25
### Patch Diff Hash-SHA-256:

5a73595e7933a1da9946350913a07a2b12337a43aa2e3f730299ef61a05cbe7a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			columnKeys.add(rowKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Chart25
### Patch Diff Hash-SHA-256:

252fe60348320c2f222aa95af1d281a8fda8aca33255478759948c5c01ea053e

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return dataset == dataset;
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Chart25
### Patch Diff Hash-SHA-256:

6975ffe377e6af827b9c9823de7b611a895a0bb3018ca1bcbc4b88ac58050de2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (org.jfree.chart.plot.Plot.ZERO) == null; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Chart25
### Patch Diff Hash-SHA-256:

daccc6654e3260f08da114652d9194d5bb8d5cac0f01633327e4b24db6ad234e

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; dataset instanceof org.jfree.chart.plot.ValueMarker; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Chart25
### Patch Diff Hash-SHA-256:

d1532bb73852b2d90e74fdef59dcfc7fd3a51684b9765f61e701592811c7bffc

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (result instanceof org.jfree.data.xy.XYCoordinate) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Chart25
### Patch Diff Hash-SHA-256:

1620b70acba49074aa0865e02c017a3a76cd4c7143a554f213953c55cfd7ea9d

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			rows.contains(rowKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Chart25
### Patch Diff Hash-SHA-256:

9702e90af4a37585973105f7b11537681cc42f77af76f06898b29892bf1719fe

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = !((domainGridlinePaint) instanceof org.jfree.data.DefaultKeyedValue);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Chart25
### Patch Diff Hash-SHA-256:

21a6ade74ae7218ebd87eb8962f08c3cf5e7b5d5900f23556faa575409fb11f2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((super.equals(org.jfree.chart.plot.CategoryPlot.localizationResources)) && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Chart25
### Patch Diff Hash-SHA-256:

f12756ef624329a946ceab53d54555ae3afe50707f04233d40214806d0530528

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (row > 0) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Chart25
### Patch Diff Hash-SHA-256:

ab64c3302812eb7ffe61aaf51624b892d633a3439265fc77e9a12f3467ad9d00

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (((DEFAULT_CROSSHAIR_STROKE) instanceof org.jfree.chart.annotations.XYPolygonAnnotation) && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Chart25
### Patch Diff Hash-SHA-256:

199fb77a962c0d7a403f07236351288ed915164e677d79dd944a270bff9598cb

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if ((rowCount == 0) || (!(dataset instanceof org.jfree.data.general.Series))) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Chart25
### Patch Diff Hash-SHA-256:

bd8f2ba0917fe6bccdaa28c114101fca39ac37e83519a32ec6c79e9648bf62ad

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (domainGridlinePaint) instanceof org.jfree.chart.labels.AbstractPieItemLabelGenerator; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Chart25
### Patch Diff Hash-SHA-256:

e93f3e952d050affb0e90993a967b4ffa41d47553cce8930e06a11bf76b39878

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; columnCount < 1; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Chart25
### Patch Diff Hash-SHA-256:

f751e660f80f5d8de9b2ecd496831765423e3e2618f3e3f7cb71856b3a66a472

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1329,7 +1329,7 @@
 		org.jfree.chart.renderer.category.CategoryItemRenderer renderer = getRenderer(index);
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
-		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
+		boolean hasData = !(rangeAxis.getRange().contains(anchorValue));
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Chart25
### Patch Diff Hash-SHA-256:

ae6fda0bca4a656a8a8a078f1b0662f51b4a12037fc8d0e4a4520fb07962aca9

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			columnKeys.contains(rowKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Chart25
### Patch Diff Hash-SHA-256:

c3ce73effe75d3e989d47bc0eab850ecba4458f2cea508a32a922625b2487357

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (anchorValue = java.lang.Math.abs(rangeCrosshairValue)) < 1.0;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Chart25
### Patch Diff Hash-SHA-256:

81b839360476539603ca14d56bdc70f4542728c40192d7af1fa77f5f2bdd06e6

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; columnCount == (-1); c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Chart25
### Patch Diff Hash-SHA-256:

dba5280e6e29eb62f3f59f00c0a84f80071d314e4b26822e04a24bb2d09588c1

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; rowCount == 2; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Chart25
### Patch Diff Hash-SHA-256:

19dceb9b1c3f1e2ce0e8a583d55c07377f00828a7a0d627142fbd095548cef94

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (result instanceof org.jfree.chart.axis.SymbolAxis) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Chart25
### Patch Diff Hash-SHA-256:

ff1a5ce009e1814481be4b40b64d9941f11f656b47a66e7cc5845aa23071f537

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((columnKeys) instanceof org.jfree.chart.util.AbstractObjectList) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Chart25
### Patch Diff Hash-SHA-256:

6d268c54e22793a621c483c1a85bc981dee77b4d3853dc5f67bf9b2b70634f71

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (rangeCrosshairVisible) || (drawSharedDomainAxis); row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Chart25
### Patch Diff Hash-SHA-256:

212a550df0b1c5a6596ba29e911e0b214046dc850c5e196d6ddb01be76a0e525

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (anchorValue) >= (anchorValue);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Chart25
### Patch Diff Hash-SHA-256:

ccf1ab9f9974985e1792b4d1304c02bb792e00ffd0796212a77f06ef56922e61

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((weight) == ((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) - 1)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Chart25
### Patch Diff Hash-SHA-256:

408cf8ee2d9d27074ce80b82ce48ed4a39368df4af632c6d70c73450a3b106d9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (java.lang.Math.sin(java.lang.Math.toRadians(anchorValue))) < 0.0; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Chart25
### Patch Diff Hash-SHA-256:

c7c92f215be0f170e4620a57a825c32a4ef6b11bca9ea2219c135648112c345d

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (row == 5) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Chart25
### Patch Diff Hash-SHA-256:

374ecc4a46eb9c068e2f9af14f0232c1623b327e700d43355828bcd955bdaa22

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (row == 1) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Chart25
### Patch Diff Hash-SHA-256:

1e87233ad495681fe8fa7c86c91e4d2986dc9f8b08a7cf3ca812a4087b32c118

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((rangeCrosshairValue) < 0.0) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Chart25
### Patch Diff Hash-SHA-256:

cfc08629c06be9b1c288be4cc6483e2911a255c0a3fb30f484ab8b36e87f0f61

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((maximumRangeValue) < 0.0) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Chart25
### Patch Diff Hash-SHA-256:

c8c00ec8ca09156f2db08cbbd267b30f561935242f65b98fe476263e65679f7a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey == null) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Chart25
### Patch Diff Hash-SHA-256:

2b5361ada904965c8fa8e280e79c0f30bbb1da7588dd4a24e5ba8f329bd68f69

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (object instanceof org.jfree.data.time.TimeSeriesCollection) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Chart25
### Patch Diff Hash-SHA-256:

629b774e9c73529917c94731ca78cd51013f399c116e52c4d00c0c413648c915

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((columnKeys) instanceof org.jfree.chart.title.CompositeTitle) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Chart25
### Patch Diff Hash-SHA-256:

36d6decfa329a7c79d5a555c228858a69c540eebfea4919d660adde1d620b346

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (rangeCrosshairValue) <= 0.0;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Chart25
### Patch Diff Hash-SHA-256:

3727f808f6f85e1eb0ddb639fa3bdb77a2d932b95595d97890f96e46dd7e12ad

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				rangeCrosshairVisible = false;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Chart25
### Patch Diff Hash-SHA-256:

549ade048a1e56d1e251139f0dd30ce2a1089ac069a16b94fd621e076df6b3bb

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (!(dataset instanceof org.jfree.data.statistics.BoxAndWhiskerItem)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Chart25
### Patch Diff Hash-SHA-256:

b10f7526d9bcc8ac818d329e6d3dfce414f8996af1c01f660d5bf8f46793ca47

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) != 0) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Chart25
### Patch Diff Hash-SHA-256:

e5dbc7818e8fe6b87b505c9d7a84a4649418704b4900dec1d1ff30a3ed9d6927

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rowKeys) instanceof org.jfree.chart.renderer.xy.XYDotRenderer) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Chart25
### Patch Diff Hash-SHA-256:

e55015b75d29cffa440db781c1550e9297906adac34766313849f870b4e23ecb

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; ((rangeCrosshairValue) > 135) && ((rangeCrosshairValue) < 225); i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Chart25
### Patch Diff Hash-SHA-256:

8da3b6a41ece5e1a81b1a61c41efe3dc768c1d2a00db14abe3461a8f487c15f9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((rangeCrosshairValue) <= ((anchorValue) + (area.getWidth()))) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Chart25
### Patch Diff Hash-SHA-256:

004542814d4275b6054fd1aa27e17dd0ff9d6fceaf858e332750d572e8ecc668

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (true) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Chart25
### Patch Diff Hash-SHA-256:

4de92effd5762e1062d629dcc4b6a6be93f685566a7a3aa3b19233ace3baa847

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (((int) (area.getMinY())) < (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW)) && ((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) < ((int) (area.getMaxY())));
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Chart25
### Patch Diff Hash-SHA-256:

99f2b0061c12d1f919d2b34211875c092a95185ebb6a360b5972acd2be41b1ea

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; dataset instanceof org.jfree.data.category.IntervalCategoryDataset; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Chart25
### Patch Diff Hash-SHA-256:

4e0c613c1ab662a9cac29ce1c48dedf12360de57ed6ff499019e87640f9ec4d0

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			rowKey.equals(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Chart25
### Patch Diff Hash-SHA-256:

07d5a574a7cfc97d0689e3516dd2452c95265a9c219c32dc07df501c79549002

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if ((rowCount == 0) || (rowCount < columnCount)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Chart25
### Patch Diff Hash-SHA-256:

16b0e5b7a938ba9c65f495cf8100ad274e465297e7efd54ba4599e694c7adbee

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; columnCount < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Chart25
### Patch Diff Hash-SHA-256:

3e787d60c0727b38cb8ae36b7960a3d4d593927db391dbbfbc9bfaf5f9107e99

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((maximumRangeValueIncStdDev) - (maximumRangeValueIncStdDev)) < (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Chart25
### Patch Diff Hash-SHA-256:

b3ef98a8cce5b703a19f6abb7764c816c49d42b342260f1b795a4799dd29900a

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if ((rowCount == 0) || (dataset instanceof org.jfree.data.RangeInfo)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Chart25
### Patch Diff Hash-SHA-256:

f971887ba2a6fee3c37c8e00fb435b077aa8c73149df669b5e9bd481433685b2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (org.jfree.chart.plot.CategoryPlot.this.domainGridlinesVisible) != (DEFAULT_DOMAIN_GRIDLINES_VISIBLE); row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Chart25
### Patch Diff Hash-SHA-256:

93aa612a5243db873dc0eee1026360265f9c36c3b24070f66b7ea99b3070463b

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (annotations) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Chart25
### Patch Diff Hash-SHA-256:

14d1800275ced32262c521a613741922f042f18302d1a5cc429c16b57bb70c02

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowIndex < columnIndex) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Chart25
### Patch Diff Hash-SHA-256:

5da65fb421183de1c44ab860b3c0dd76b0de440220f9a02b18e9d739f5acc185

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (hasData && ((org.jfree.chart.plot.Plot.DEFAULT_BACKGROUND_PAINT) == (org.jfree.chart.plot.CategoryPlot.this))) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Chart25
### Patch Diff Hash-SHA-256:

27202ba1c5c6708bb643a1ba75dde57467666f18da6a7e4fb367d805d6a2a224

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValue)) || ((minimumRangeValue) < (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Chart25
### Patch Diff Hash-SHA-256:

acdb52b4a888d397dfc416eac1cf9363de0c2530ae2f73d416cc2864cfbe94a2

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (columnCount < columnCount) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Chart25
### Patch Diff Hash-SHA-256:

484a997b8b166d7246944e01ae45188e40a384bcfcb5b0a7e2910aa39a19228c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				org.jfree.chart.plot.CategoryPlot.this.domainGridlinesVisible = DEFAULT_RANGE_GRIDLINES_VISIBLE;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Chart25
### Patch Diff Hash-SHA-256:

17c0994bdf19811f48049be1d12a27de290e445b20ac05726491f95a36af4e88

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = true;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Chart25
### Patch Diff Hash-SHA-256:

11d6774d2b3673ceafc5b27e12901b51a5a0a452cef42f300a3b1a5d16740769

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (axisOffset) == null; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Chart25
### Patch Diff Hash-SHA-256:

9c478e722d8c67efebd40bc43ddf3d65110232d2f8c358dbf8365dbec904356f

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			rows.equals(row);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Chart25
### Patch Diff Hash-SHA-256:

836881b553d3a7b2cfd5c3eb00a7a111e844577c554e8f3b3307718547f50748

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; columnCount < columnCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Chart25
### Patch Diff Hash-SHA-256:

eee292d0a59a3b8189a31e388360ff6fa7863946952b0406b3a837be8b206c16

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				org.jfree.chart.plot.CategoryPlot.this.domainGridlinesVisible = org.jfree.chart.plot.CategoryPlot.DEFAULT_DOMAIN_GRIDLINES_VISIBLE;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Chart25
### Patch Diff Hash-SHA-256:

237ea2ac379b75f00c9f5e47e02b4ed4608509694a488ef274fc88aaf4da7e6b

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.data.Range) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Chart25
### Patch Diff Hash-SHA-256:

7ca4438e34b16aabc707d8630b7efeb6742297b7e11d00f77b75dd0cef28f20f

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if ((rowCount == 0) || (columnCount == 0)) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Chart25
### Patch Diff Hash-SHA-256:

eb6d5489eecfb152a2e6ba4d1f416c561847640ac33f6b319bff87d7e7c009e3

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; rowCount < (dataset.getRowCount()); c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Chart25
### Patch Diff Hash-SHA-256:

46ab2db1b40491c58eb1df2f541dbecf0e1cca1db7c814c2836ca48eab6f2c44

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (column < column) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Chart25
### Patch Diff Hash-SHA-256:

f0d66cf1e361e1cb8974727278f5b5538990d8193e18881069b1f424be181f42

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; currentDataset instanceof org.jfree.chart.plot.CategoryPlot; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Chart25
### Patch Diff Hash-SHA-256:

c81e20f940fa3f60fc67d8d239b2f614d8e012421da3dffd9a10624369fd65f1

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowKey instanceof org.jfree.data.KeyedObjects2D) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Chart25
### Patch Diff Hash-SHA-256:

a3efca2f4a6e4a2cfc4752c155cb03c2023652e18060d48140c7095b09b6097a

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (rowCount < (dataset.getRowCount())) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Chart25
### Patch Diff Hash-SHA-256:

cc0abf35d8481e470000b781988ed740558c196b750449da0f3773d4811d3d73

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; columnCount < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Chart25
### Patch Diff Hash-SHA-256:

3359c6e969361500aed3704ed852ce39406fa9b75335b19fa241a76a567ddbee

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -89,7 +89,7 @@
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
 		if (columnIndex < 0) {
-			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
+			rowKey.equals(row);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Chart25
### Patch Diff Hash-SHA-256:

f64bb43b70c3a3d39082fbb0ee8c49df11fa12a0f76ccc358d915e0ebd99cffd

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				org.jfree.chart.plot.CategoryPlot.this.rangeGridlinesVisible = org.jfree.chart.plot.CategoryPlot.DEFAULT_RANGE_GRIDLINES_VISIBLE;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Chart25
### Patch Diff Hash-SHA-256:

4ea0b7c7c75f55a23a10b05483984e7915f7d0a66a1e486420c386469671ae9b

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValueIncStdDev)) || (((maximumRangeValueIncStdDev) - (maximumRangeValue)) < (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Chart25
### Patch Diff Hash-SHA-256:

55c0e095e8911b2eb386d6ca79b2320a10fb48cd2174c8cfb5a8744ae5d2e2a4

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (columnCount < (dataset.getRowCount())) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Chart25
### Patch Diff Hash-SHA-256:

3483257822a62c1bb35dad7192abf0712be0600aa47b5c5b9c7d9acd110fca77

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (result instanceof org.jfree.data.KeyedObject) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Chart25
### Patch Diff Hash-SHA-256:

698637f1c5698c1aac337d313b10231ce4971339e1a333b98962dc2fab9620b4

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				org.jfree.chart.plot.CategoryPlot.this.drawSharedDomainAxis = false;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Chart25
### Patch Diff Hash-SHA-256:

5f630463f417982d6350bcf82bf71a5eeef474c707e032d1e5cb84dddc0ed73a

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((minimumRangeValue) + (minimumRangeValueIncStdDev)) > (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.maximumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Chart25
### Patch Diff Hash-SHA-256:

83163c0f1469f7dc12ad1a18c7b43d1e4b4e8609c37acdc690b78306b39229ae

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.maximumRangeValue)) || ((minimumRangeValue) > (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.maximumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Chart25
### Patch Diff Hash-SHA-256:

6490b8307dec5f54ef4a9514d037a1a43eacb80ab99f39c83b135510783c3d63

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((org.jfree.chart.plot.CategoryPlot.this.backgroundDomainMarkers) != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Chart25
### Patch Diff Hash-SHA-256:

55f140fac374a2566dd8df91af0b63f371fafd0f677c2d3fea1a0634b25cd86d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) < (weight); pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Chart25
### Patch Diff Hash-SHA-256:

11a4c229cad14a8d1c37f46e188f411a5b7fbd4e9b53381cef926c5d74614e6b

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rows) instanceof org.jfree.data.KeyedObjects2D) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Chart25
### Patch Diff Hash-SHA-256:

f6bf3da2a657ee61e92c95bc4113a87531775904d5da4f453438d7ccced5c0a2

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((columnIndex >= 0) && (columnIndex < (rows.size()))) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Chart25
### Patch Diff Hash-SHA-256:

0b2bcde6c76e39de3881dd84baf37ab57764bc1d1ec1fb8bacd0cfe82822dfab

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.maximumRangeValueIncStdDev)) || (((maximumRangeValueIncStdDev) + (minimumRangeValueIncStdDev)) > (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.maximumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Chart25
### Patch Diff Hash-SHA-256:

183fcc203bbbd04d11e70f65ec77c5e6782cd0b6efce4766f4986d1070449f16

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; columnCount < (dataset.getRowCount()); r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Chart25
### Patch Diff Hash-SHA-256:

ff8b6167f6c86f106ce340b16483d994fe7c76f3d941fb588605f1668a56ee07

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; rowCount < (org.jfree.chart.plot.CategoryPlot.this.datasets.size()); column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Chart25
### Patch Diff Hash-SHA-256:

65c049aed597bb16857ea2c684438b0a7400382db0011a6151ce5734db6024cf

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (DEFAULT_GRIDLINE_PAINT) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Chart25
### Patch Diff Hash-SHA-256:

32052cb998bef3b0fba150bfb5db999e1ed17ecec67305c23fa2b570f18f6095

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) >= 0) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Chart25
### Patch Diff Hash-SHA-256:

8714db86229a1809f9d817461874361e9cdc7f6c77521e627e50c899aed2613b

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (columnKey instanceof org.jfree.data.KeyedObjects) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Chart25
### Patch Diff Hash-SHA-256:

30d55fb502ad5e80930a695726932672f1f0bda0ff1944efe8de29f3b36b93fc

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rowKeys) == null) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Chart25
### Patch Diff Hash-SHA-256:

1b6d80ee8e19022750ad97550b71455c9d035e3c0281844745fe679f0563118e

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((maximumRangeValueIncStdDev) - (minimumRangeValue)) < (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Chart25
### Patch Diff Hash-SHA-256:

abde9fa726641c8b140b03b9ebc9d1d91d44649320a34a2ad398b952bfa79477

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (rowCount < columnCount) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Chart25
### Patch Diff Hash-SHA-256:

57e1ae58e5cbb1e0530c1298c0404c52abddcd9786b88fd60c79b41f482c3b94

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((renderingOrder) == (org.jfree.chart.plot.DatasetRenderingOrder.FORWARD)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Chart25
### Patch Diff Hash-SHA-256:

bf08b5273dd4de9cee1b02edebad5c4326326f57ec0dc95b543e6aadab5169ef

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (columnIndex >= 0) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Chart25
### Patch Diff Hash-SHA-256:

b1d6c104753d802eaf10bbcc832851ada185b851e8c8eec728b412e713eb6f62

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; rowCount < ((dataset.getColumnCount()) - 1); r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Chart25
### Patch Diff Hash-SHA-256:

82ce414723e744dd75e68f7b46c97db1970b3c881473f2b2a090001234f37112

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((minimumRangeValue) - (minimumRangeValue)) < (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Chart25
### Patch Diff Hash-SHA-256:

19a01adf793fc03121383f41016209fb68acb1d168ece0d96ae7a72e05a1df9f

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (weight) == 0;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Chart25
### Patch Diff Hash-SHA-256:

5f7aa835cb808af07661ae71c5d842f183969679612db132b7b470b566d329ce

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (dataset instanceof org.jfree.data.category.IntervalCategoryDataset) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Chart25
### Patch Diff Hash-SHA-256:

1597a4a6af9552525cf9ac285517168691695d4623850ddeebd1ff05139d9918

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; rowCount < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Chart25
### Patch Diff Hash-SHA-256:

43308ad6cba200b9e02c75644a7d83c17d34d8a5ce4dee68b5ab547610bf275e

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; columnCount <= rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Chart25
### Patch Diff Hash-SHA-256:

56256bfeee0099f4c512ebda71cff6a7ccdfdffb1eaf81f7cba5a76c43d68eb0

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (object == (org.jfree.data.KeyedObjects2D.this)) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Chart25
### Patch Diff Hash-SHA-256:

e7de9fb4659bef4ba29440e4dc60f219101655aed31d10429207da9769806bbf

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; renderer == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Chart25
### Patch Diff Hash-SHA-256:

48093eef42395625824a937a540e0d6201cbe38a80dc109de06cdd63643ec2bc

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((minimumRangeValue) > (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.maximumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Chart25
### Patch Diff Hash-SHA-256:

3a0cccdac7023eb4b4268471cb839c8ba7d4b29099aa6242db81c92439e5526b

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1329,7 +1329,7 @@
 		org.jfree.chart.renderer.category.CategoryItemRenderer renderer = getRenderer(index);
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
-		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
+		boolean hasData = !(axisOffset.equals(axisOffset));
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Chart25
### Patch Diff Hash-SHA-256:

fdecb0664c37398bd11a0b76ad46eb0ffabab6676e6c34c21607fc3aa536504e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; rangeAxis == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Chart25
### Patch Diff Hash-SHA-256:

5b8b043dfabc3ed39e4a0667c3cb26235fe8049e97f284a5849b1c8b7c54f8a6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; !foundData; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Chart25
### Patch Diff Hash-SHA-256:

6e89d688c8e1fd7ca09d77e86bee8608889322f3045fc37c81d4f54bf4302c2e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (hasData && (index < index)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Chart25
### Patch Diff Hash-SHA-256:

da5f2d28a3f5f04c22c40607bec80775dbd536c409afaef2a2af6eb554203fc7

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; super.equals(g2); i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Chart25
### Patch Diff Hash-SHA-256:

7a65804a933e87c92bfda20aa3b10ae1e6d6a84b948d3cf873788f2b03c7bbc2

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if ((!(dataset instanceof org.jfree.chart.labels.AbstractPieItemLabelGenerator)) || (columnCount == 0)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Chart25
### Patch Diff Hash-SHA-256:

74e096c17ea24910f96a1b61c7e5baedc80e02c0f781924b1a5df074a488cbc8

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; index < 0; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Chart25
### Patch Diff Hash-SHA-256:

a573bc615674991e131bc7a75b9995c2341828ee92e838a27ca52c209141a23d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((foundData || foundData) && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Chart25
### Patch Diff Hash-SHA-256:

8eb0dbd52ff3a19b162178bebde9f133d35729fe0c0d21ef0fb0bdc8ca9834a3

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; dataset instanceof org.jfree.chart.plot.MultiplePiePlot; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Chart25
### Patch Diff Hash-SHA-256:

1e06016737faff9e270ed1dc521e0158a52c7b63d87cdb4b1de16937da3955eb

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((java.lang.Double.isNaN(anchorValue)) || (java.lang.Double.isNaN(anchorValue))) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Chart25
### Patch Diff Hash-SHA-256:

ac59dff57f62bdb9f3c9729394a9c52480a8b0aae098515b78007bcc89f0808b

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (dataset instanceof org.jfree.chart.plot.CombinedRangeXYPlot) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Chart25
### Patch Diff Hash-SHA-256:

d5208f5a1712dbf14e2cfd69f82da9ec644b85a0876f1141df8336ed3041a081

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (super.equals(columnKey)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Chart25
### Patch Diff Hash-SHA-256:

968c4582a4cd1b72664ea3209340aa34d584e643630cec95725e1fab8273e08c

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return columnCount != 0;
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Chart25
### Patch Diff Hash-SHA-256:

1b5eacd783f024cfa93dca2941c3000ab71a33851f960459b0753c1503a4e1c5

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = drawSharedDomainAxis = !(drawSharedDomainAxis);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Chart25
### Patch Diff Hash-SHA-256:

c9be68b17b9d7fc24cbe11c57abce4cb95ad5849937b9bd340ea7689e037d77d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = (isRangeCrosshairVisible()) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Chart25
### Patch Diff Hash-SHA-256:

0557dfd68be89473ca1f47682531c6f2b4f37673662c08be26cd08988cdbd093

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = false;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Chart25
### Patch Diff Hash-SHA-256:

12e24f8bbbeeb3a4cf000606fc054a326efd6206b4237c68222de38c19a15ab0

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (columnKey instanceof org.jfree.data.statistics.HistogramType) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Chart25
### Patch Diff Hash-SHA-256:

7202e4c8c0a747d16f444a3c6ada5fae02b5743300ee3a8821124d1b2fe32516

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; dataset instanceof org.jfree.chart.annotations.XYImageAnnotation; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Chart25
### Patch Diff Hash-SHA-256:

4b44336f84615d89ef12b5f00ce9996cf7e5ee4bfd31c0135315399bd9fd6a60

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (columnCount > columnCount) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Chart25
### Patch Diff Hash-SHA-256:

b07e69c92275efafddb8890ca5e9f807d7495911f757ccbe7bdf7ff9b895d6d2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (anchorValue) > 0.0; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Chart25
### Patch Diff Hash-SHA-256:

f761ea33222e86b2bd776b9336ef670b0b932c730fb7db02891850a6c0b9398e

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.data.time.ohlc.OHLC) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Chart25
### Patch Diff Hash-SHA-256:

42c4f141f0e6c1f55daaeb06a91105f52fdcefcff61a1161ca646db986a29f0d

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return columnCount >= 0;
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Chart25
### Patch Diff Hash-SHA-256:

23d15d7a688216c953202562abdc570893efafd2d547c0cee73ce46a925aed75

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; !foundData; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Chart25
### Patch Diff Hash-SHA-256:

01b202552fec89acded35e7015602f80bbec772fc95a54b4acf2d305194821e7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (false) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Chart25
### Patch Diff Hash-SHA-256:

10a882c1ae18f2b9895a42ee8883c8da36052debfcbc3e8e5c86e50d7ebb337f

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowIndex < rowIndex) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Chart25
### Patch Diff Hash-SHA-256:

fefbe78d61156888bf7aceecee5543d09aab5003e394d2e593a3f4d762422c1d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = drawSharedDomainAxis = true;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Chart25
### Patch Diff Hash-SHA-256:

f7ea81be1cbb00cc6327702b5a7d7bb089952f16359a83f619ab82016fb36883

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				drawSharedDomainAxis = true;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Chart25
### Patch Diff Hash-SHA-256:

630d29b0e57e1ce3679968e687779530b229ec44dc5fc82b0da8013c68bf163f

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Chart25
### Patch Diff Hash-SHA-256:

8870c58d852341fbdb1b180b0720927b1f6955941246f4968d59f99f926c9c05

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -215,7 +215,7 @@
 	}
 
 	public static boolean isEmptyOrNull(org.jfree.data.category.CategoryDataset dataset) {
-		if (dataset == null) {
+		if (!(dataset instanceof org.jfree.chart.annotations.TextAnnotation)) {
 			return true;
 		}
 		int rowCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Chart25
### Patch Diff Hash-SHA-256:

131bd298d806045b8e961265e60ccb622068064d4cc502a2932e23a90953358c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; java.lang.Double.isNaN(anchorValue); i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Chart25
### Patch Diff Hash-SHA-256:

f430b648742440a5c753eeb56f8edd277429fb34f4b9f2a86665279e0acd683a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (index >= 1) && (index <= (org.jfree.data.time.SerialDate.lastDayOfMonth(index, index))); row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Chart25
### Patch Diff Hash-SHA-256:

908f5f2392c97ef4947878e1bbedfd59710f672122fa78164b789a656797cf1b

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; foundData = false; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Chart25
### Patch Diff Hash-SHA-256:

ea16c41ab776449252119a0324964e8bdc9a89bc241d4a54b922530383d9808c

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (rowIndex > 1) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Chart25
### Patch Diff Hash-SHA-256:

c8c83dac988e8f63702101d20aef7cfd0e7c525210ad6c7e0af62610ea1d2393

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (domainGridlinePaint) == null; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Chart25
### Patch Diff Hash-SHA-256:

d2b93069bdb6b3e8493256531b7168233360be900e9f474e047c2bd2ac97418a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (anchorValue) > index; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Chart25
### Patch Diff Hash-SHA-256:

ea8910c3b957910ca8faf5cd29c68321fa913529626646270230244a8be98fc4

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; index != 0; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Chart25
### Patch Diff Hash-SHA-256:

1430b6bda619bf79f4f31055b2c35316e975095925d09f1ef78153d97df6fad8

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = (foundData) ? (anchorValue) > 0.0 : (anchorValue) >= 0.0;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Chart25
### Patch Diff Hash-SHA-256:

a770b00c689b736d62365c550a51e5591b45f03ff6dd12027b5771c166ecf932

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (org.jfree.chart.util.ObjectUtilities.equal(annotations, annotations)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Chart25
### Patch Diff Hash-SHA-256:

144a547f0c430140c19aa2130111cf0b0696c2a8fff1b4d0e0bc609ec8e12d4e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (!(super.equals(g2))) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Chart25
### Patch Diff Hash-SHA-256:

dc2bcbf20e0839273a2a6df462785d558755223cd3117ad401b92fae81073a15

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if ((rowIndex & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.LINES)) != 0) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Chart25
### Patch Diff Hash-SHA-256:

693362f7ce0fb911e5cdbc0fc00763b7a5ba9e25b0937b50aa0b91241990e231

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return columnCount <= 59;
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Chart25
### Patch Diff Hash-SHA-256:

51ae183469554f783141ac579f395341ea793d38d4c800cb09b48e6710f6aba6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (domainGridlinePaint) == null; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Chart25
### Patch Diff Hash-SHA-256:

0788b3020c29c209138b134a156c7e8cb456e357bff11840e96551a275ba4332

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.chart.renderer.xy.CandlestickRenderer) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Chart25
### Patch Diff Hash-SHA-256:

d98f88f167f77513edf16049d5dfbc87016773efd17c8dabea25f74191e6fa76

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; dataset instanceof org.jfree.chart.util.StandardGradientPaintTransformer; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Chart25
### Patch Diff Hash-SHA-256:

b2bcbef0ec5f42439b0ee727cfcbe014b802f7825f019fc6b0a1c3f88aed4805

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				drawSharedDomainAxis = drawSharedDomainAxis;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Chart25
### Patch Diff Hash-SHA-256:

e75b16f686943bb4455dbfe372bd755c60c5e78d65f38d56483c2ef31faf8ca9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (index < (annotations.size())) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Chart25
### Patch Diff Hash-SHA-256:

09ae0aada4d55910f37386eb3c91df514b28c137cfeaab87cd473d68c7a0eef1

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; ((anchorValue) > 0.0) || ((!foundData) && ((anchorValue) >= 0.0)); row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Chart25
### Patch Diff Hash-SHA-256:

4ac727b999d7ea703606890514ebe534f9cdfd1edeabe72fe9579f5c82ee7035

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; index < index; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Chart25
### Patch Diff Hash-SHA-256:

8dc1f9daf6221f056f7069e761fbf8cf2eab6ccbc68a7e2269ccd121ba8d3a84

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; datasetCount < datasetCount; i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Chart25
### Patch Diff Hash-SHA-256:

6e8e981cdce4a31dafd6b8042b505f8325f44d833f891c5066b302b2ca1d224e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				domainGridlinesVisible = domainGridlinesVisible;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Chart25
### Patch Diff Hash-SHA-256:

8fec6af58e0573b5ae1f1abc1726b3b570c592f25c1a4b0d949d5a225af90778

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1329,7 +1329,7 @@
 		org.jfree.chart.renderer.category.CategoryItemRenderer renderer = getRenderer(index);
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
-		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
+		boolean hasData = !(org.jfree.chart.plot.ThermometerPlot.isValidNumber(anchorValue));
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Chart25
### Patch Diff Hash-SHA-256:

5980e07ed16b6d46b2bcc1c42d7bd38499a79c9fe06b9604a7470c407dd44ea6

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -223,7 +223,7 @@
 		if ((rowCount == 0) || (columnCount == 0)) {
 			return true;
 		}
-		for (int r = 0; r < rowCount; r++) {
+		for (int r = 0; dataset instanceof org.jfree.data.gantt.Task; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Chart25
### Patch Diff Hash-SHA-256:

7c392f436ce03d0b7c93cda48257f10476c1f033ae8d84e0621485148d8e475c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (foundData = foundData) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Chart25
### Patch Diff Hash-SHA-256:

62867fd8f36e60e506f6b63611fbe33134bfbc013838e5528a226cea52c96b68

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.chart.axis.Tick) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Chart25
### Patch Diff Hash-SHA-256:

1e79ab73986aef5c7433f49dd5b8dadec5304d6cb090f1b52b192857aa7818e6

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (column == (row - 1)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Chart25
### Patch Diff Hash-SHA-256:

de1f7f4d2a43f71b91edf71748f92d04953d04682331a976115deb9318dba254

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return columnCount != (org.jfree.chart.plot.CompassPlot.VALUE_LABELS);
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Chart25
### Patch Diff Hash-SHA-256:

9710faea727ede6efa14b96784fded84171415f97e41427cc7158cc5162e8add

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (drawSharedDomainAxis = true) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Chart25
### Patch Diff Hash-SHA-256:

11a79e768e33d526123cc7cd760b963c79c6756d2e7a8de0848b6098361a4df1

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if (foundData = ((!foundData) && ((anchorValue) < 10.0)) && ((anchorValue) > 0.0)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Chart25
### Patch Diff Hash-SHA-256:

7dcdb0025bf6d55a9797780bd2ee248de090280533b96fa773f9616f19377e90

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; index < index; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Chart25
### Patch Diff Hash-SHA-256:

f52012cee8c1fb3f23fe875def24dc4a1856007048c54a48eb8afc51dbf94126

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return !(dataset instanceof org.jfree.chart.axis.CyclicNumberAxis);
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Chart25
### Patch Diff Hash-SHA-256:

fc93c2f497893e559dd3e5f2568d2da4063dae28e05525f6ce2bf608c9468c30

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((anchorValue) == (anchorValue)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Chart25
### Patch Diff Hash-SHA-256:

d96a7ff6903a14788b47c8d42e86ed9a63fedfc28dd264b070b784e69b7e579d

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.chart.labels.StandardXYSeriesLabelGenerator) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Chart25
### Patch Diff Hash-SHA-256:

0b4d4addc7774bd8cf8fcf9575d7488fad5112a4a0b89fdc8df0e9b3dd5baace

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				domainGridlinesVisible = true;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Chart25
### Patch Diff Hash-SHA-256:

112a309f32eae73e151e72f18ade6d8083dcce8c5ced6f4016197f23f4fe7c69

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.chart.entity.StandardEntityCollection) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Chart25
### Patch Diff Hash-SHA-256:

31cf4f893b3de0a8b9db868df834f4ad19fe47be00ad8a8bc23d2601e076280a

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (!(dataset instanceof org.jfree.chart.urls.StandardCategoryURLGenerator)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Chart25
### Patch Diff Hash-SHA-256:

6082a44e727d70b38893635ce90384428c3d98f6b34edeebd505e81a1061f52d

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValue)) || (java.lang.Double.isInfinite(minimumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Chart25
### Patch Diff Hash-SHA-256:

0b8ba2a11805066eb01336f3f058d0d9cf8b2eabb1525721a618ea0a08c0743c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; (annotations) == null; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Chart25
### Patch Diff Hash-SHA-256:

7fb047d7706770c85a057754cb72d185f4be307189eed98e98303563555da175

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -224,7 +224,7 @@
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
-			for (int c = 0; c < columnCount; c++) {
+			for (int c = 0; dataset instanceof org.jfree.chart.util.RectangleInsets; c++) {
 				if ((dataset.getValue(r, c)) != null) {
 					return false;
 				}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Chart25
### Patch Diff Hash-SHA-256:

b853e978dec7f374529e92e3c9861d4aa40c679b2f8e07d6d805b20b2db40d13

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -215,7 +215,7 @@
 	}
 
 	public static boolean isEmptyOrNull(org.jfree.data.category.CategoryDataset dataset) {
-		if (dataset == null) {
+		if (true) {
 			return true;
 		}
 		int rowCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Chart25
### Patch Diff Hash-SHA-256:

afcd08fc6e1f1f88093665831d8bdf48630f4aca161a06ba3743820c00586461

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (row > 0) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Chart25
### Patch Diff Hash-SHA-256:

0b8bed614af454eeba29863e8e3c232281f3f99f45fec082fd404ddd292b26d5

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; foundData = foundData; i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Chart25
### Patch Diff Hash-SHA-256:

0980dbc70bf1442cf16f3725d651089103afd7e79c2c8952aeaaa5028a78d183

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1152,7 +1152,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (anchorValue) < 1.0;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Chart25
### Patch Diff Hash-SHA-256:

9f2945d819291181d6b294dd53471714cb7573ceb21320d8fe88e6c5ea3e7793

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.chart.renderer.category.LevelRenderer) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Chart25
### Patch Diff Hash-SHA-256:

d216ebece89a3d4d7d26f2ac690b325fc225a2db5136075555b5f261fb91d886

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1336,7 +1336,7 @@
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
-			for (int pass = 0; pass < passCount; pass++) {
+			for (int pass = 0; foundData != foundData; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Chart25
### Patch Diff Hash-SHA-256:

7bfaf5a4d6bbe8a698879775ffc0899ee61a4d90995d2a20d28ee2da908f7f88

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; (datasetCount == (datasetCount - 1)) || (java.lang.Double.isNaN(anchorValue)); i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Chart25
### Patch Diff Hash-SHA-256:

105f5f435473761fa0c8fc85e4695988096d343bac0d2bc7376956c8b5ce49a5

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -88,7 +88,7 @@
 		}
 		row.setObject(columnKey, object);
 		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
-		if (columnIndex < 0) {
+		if (columnKey instanceof org.jfree.data.time.TimePeriod) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Chart25
### Patch Diff Hash-SHA-256:

dff74b7e58502a74b4b570b6630dc4cde6387ec701f410d9a1973e125827b344

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((row < 0) || (row > (rows.size()))) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Chart25
### Patch Diff Hash-SHA-256:

a352722d476345fa465ebea8661f8ff0ebe08e9918532491368c055563b78e73

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -226,7 +226,7 @@
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
 				if ((dataset.getValue(r, c)) != null) {
-					return false;
+					return !(dataset instanceof org.jfree.data.time.ohlc.OHLCSeriesCollection);
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Chart25
### Patch Diff Hash-SHA-256:

a2e3edfe6ca6905cf468253c5b25dcad7d0c351963f3af4f28b7b1e9b05128e7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((row > row) && (row < row)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Chart25
### Patch Diff Hash-SHA-256:

484585ab39911607bed5abf6fcb6f90cc9404d646fb0a6842553e268b6d0046d

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (column < row) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Chart25
### Patch Diff Hash-SHA-256:

658e0b9c8e9f8f29231fd8b83b33aa471f7c4b2d26b5f4b54a0aa4162648909a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; super.equals(g2); row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Chart25
### Patch Diff Hash-SHA-256:

26b0ed1aaac0feddbe1fdc651795da7b03639cc4946b2131d059dcd49ef2049e

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -225,7 +225,7 @@
 		}
 		for (int r = 0; r < rowCount; r++) {
 			for (int c = 0; c < columnCount; c++) {
-				if ((dataset.getValue(r, c)) != null) {
+				if (false) {
 					return false;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Chart25
### Patch Diff Hash-SHA-256:

3a79cdefd507e3b794762a1e1e87c1bf84369babc52246356bc2c097b3c1a283

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1340,7 +1340,7 @@
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-							for (int row = 0; row < rowCount; row++) {
+							for (int row = 0; (domainGridlinePaint) instanceof java.awt.GradientPaint; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
 							}
 						}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Chart25
### Patch Diff Hash-SHA-256:

80ad0cbde44071fabd840792e5feb5cd036a6162f0c3727d6a00127eb2f238ad

### Patch Diff:
```
--- /original/org/jfree/data/general/DatasetUtilities.java	
+++ /fixed/org/jfree/data/general/DatasetUtilities.java	
@@ -220,7 +220,7 @@
 		}
 		int rowCount = dataset.getRowCount();
 		int columnCount = dataset.getColumnCount();
-		if ((rowCount == 0) || (columnCount == 0)) {
+		if (!(dataset instanceof org.jfree.chart.StrokeMap)) {
 			return true;
 		}
 		for (int r = 0; r < rowCount; r++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Chart25
### Patch Diff Hash-SHA-256:

93ecc3f978f5b717f2578b717085864390beb165722548c5c5ea9b51ae8a2ff3

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1227,7 +1227,7 @@
 				}
 			}
 			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
-				foundData = (render(g2, dataArea, i, state)) || foundData;
+				foundData = (domainGridlineStroke) == null;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
 				org.jfree.chart.renderer.category.CategoryItemRenderer r = getRenderer(i);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Chart25
### Patch Diff Hash-SHA-256:

7d80e1388d291ff71a7ab5ee08bc9d457e63940bf714e110121aa06c67ae5e9e

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -95,7 +95,7 @@
 	}
 
 	public int getColumnCount() {
-		return org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getColumnCount();
+		return data.getRowCount();
 	}
 
 	public void add(double mean, double standardDeviation, java.lang.Comparable rowKey, java.lang.Comparable columnKey) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Chart25
### Patch Diff Hash-SHA-256:

1c1cd424e1684c920ce7166d128d27533f0cd602e4343d98f02348bec685f83c

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (area.getMinX()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Chart25
### Patch Diff Hash-SHA-256:

db34ab326a9561e845ab198269746695a0008e6f0eacccb419be6479a3a57520

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1154,7 +1154,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (((domainGridlineStroke) != null) && ((domainGridlinePaint) != null)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Chart25
### Patch Diff Hash-SHA-256:

bc25981847996ffa14df60561baa999bf66ee1955a9258ccb5a9c5fbdf314a18

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1226,7 +1226,7 @@
 					r.drawAnnotations(g2, dataArea, domainAxis, rangeAxis, org.jfree.chart.util.Layer.BACKGROUND, state);
 				}
 			}
-			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; i >= 0; i--) {
+			for (int i = (org.jfree.chart.plot.CategoryPlot.this.datasets.size()) - 1; (isRangeCrosshairVisible()) && foundData; i--) {
 				foundData = (render(g2, dataArea, i, state)) || foundData;
 			}
 			for (int i = datasetCount - 1; i >= 0; i--) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Chart25
### Patch Diff Hash-SHA-256:

afc1706d310da1449eeaeca7b84247234973a185e10a4b408f95a7e3b82c93e2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (orientation) == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Chart25
### Patch Diff Hash-SHA-256:

2c7d555af20d7cd73c2e8201aa59f6a3ac095ae16e1a1e5d053c21f34dd9070e

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -87,7 +87,7 @@
 			org.jfree.data.KeyedObjects2D.this.rows.add(row);
 		}
 		row.setObject(columnKey, object);
-		int columnIndex = org.jfree.data.KeyedObjects2D.this.columnKeys.indexOf(columnKey);
+		int columnIndex = rowKeys.size();
 		if (columnIndex < 0) {
 			org.jfree.data.KeyedObjects2D.this.columnKeys.add(columnKey);
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Chart25
### Patch Diff Hash-SHA-256:

babd89fb9464884ae360d0682f9fe99706ef1aa0c48b650705debc1b61045413

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1333,7 +1333,7 @@
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
-			int columnCount = currentDataset.getColumnCount();
+			int columnCount = rangeAxes.indexOf(rangeAxis);
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Chart25
### Patch Diff Hash-SHA-256:

9e8241843dcee6f5592d76fb5bf1235585bda30c3d4404d25c314658ed3890b2

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.data.KeyedObjects) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Chart25
### Patch Diff Hash-SHA-256:

86be312d6d35e6d636cb1247919a3e03dce2db5069b3577386493981149daa9d

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -554,7 +552,7 @@
 	public java.awt.image.BufferedImage createBufferedImage(int width, int height, int imageType, org.jfree.chart.ChartRenderingInfo info) {
 		java.awt.image.BufferedImage image = new java.awt.image.BufferedImage(width, height, imageType);
 		java.awt.Graphics2D g2 = image.createGraphics();
-		draw(g2, new java.awt.geom.Rectangle2D.Double(0, 0, width, height), null, info);
+		clearSubtitles();
 		g2.dispose();
 		return image;
 	}
@@ -733,31 +731,3 @@
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Chart25
### Patch Diff Hash-SHA-256:

ae2ada5dd5b5f37261edce55765a8ce17beba2c40bf2b7be47a155c8c5befd97

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.data.KeyedObject) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Chart25
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Chart25
### Patch Diff Hash-SHA-256:

87f2d852cf377ccde38854e6c40df884620004c1a5f8e5e17d67aed74ffef994

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1153,7 +1153,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (fixedDomainAxisSpace) == null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Chart25
### Patch Diff Hash-SHA-256:

85ce24d85c6bb0b07993b364dcc4b3c78c5e822206fcbb6e9f30c830d5da18aa

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1330,7 +1330,7 @@
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
 		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
-		if (hasData && (renderer != null)) {
+		if ((domainGridlineStroke) == null) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Chart25
### Patch Diff Hash-SHA-256:

6db21d709a5e539861a824b98780f29bf7ac3068e200c2faf6f7014a9df913e4

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) == null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Chart25
### Patch Diff Hash-SHA-256:

437996187d15fe9c190f7b19a2e6f4b684a598896fbf46f2e1ea553fd39772bf

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -554,7 +552,7 @@
 	public java.awt.image.BufferedImage createBufferedImage(int width, int height, int imageType, org.jfree.chart.ChartRenderingInfo info) {
 		java.awt.image.BufferedImage image = new java.awt.image.BufferedImage(width, height, imageType);
 		java.awt.Graphics2D g2 = image.createGraphics();
-		draw(g2, new java.awt.geom.Rectangle2D.Double(0, 0, width, height), null, info);
+		g2.setPaint(backgroundPaint);
 		g2.dispose();
 		return image;
 	}
@@ -733,31 +731,3 @@
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Chart25
### Patch Diff Hash-SHA-256:

a1a4a52168a08465180d63727188d7553d1e9f5dbfd60fc52a352f6fe8fdd0cc

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; (domainGridlinePaint) == null; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Chart25
### Patch Diff Hash-SHA-256:

cd2f360fbd66aef23d2106a2892487b4eda1b5dd6a9e0a6af48cdcd4ccc8173a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) == (org.jfree.data.KeyedObjects2D.this)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Chart25
### Patch Diff Hash-SHA-256:

85b0896cf55bc631ad55d515d564e162bbd43b995024cc65827aa1dd80883b31

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1338,7 +1338,7 @@
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
-					for (int column = 0; column < columnCount; column++) {
+					for (int column = 0; index < 0; column++) {
 						if ((org.jfree.chart.plot.CategoryPlot.this.rowRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 							for (int row = 0; row < rowCount; row++) {
 								renderer.drawItem(g2, state, dataArea, org.jfree.chart.plot.CategoryPlot.this, domainAxis, rangeAxis, currentDataset, row, column, pass);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Chart25
### Patch Diff Hash-SHA-256:

38ba5bfd4ef7fd284f041cb92f379b9f0ec97349d9347653f82be97876ccda09

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1334,7 +1334,7 @@
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
-			int rowCount = currentDataset.getRowCount();
+			int rowCount = renderers.indexOf(renderer);
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Chart25
### Patch Diff Hash-SHA-256:

ca872dbc55f069e3b2abfba0a8a1ddbee4440018ebb087ddc384cbb7038f9103

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1335,7 +1335,7 @@
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
 			int columnCount = currentDataset.getColumnCount();
 			int rowCount = currentDataset.getRowCount();
-			int passCount = renderer.getPassCount();
+			int passCount = domainAxes.indexOf(domainAxis);
 			for (int pass = 0; pass < passCount; pass++) {
 				if ((org.jfree.chart.plot.CategoryPlot.this.columnRenderingOrder) == (org.jfree.chart.util.SortOrder.ASCENDING)) {
 					for (int column = 0; column < columnCount; column++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Chart25
### Patch Diff Hash-SHA-256:

b0c1f2142995c63c9ba0e38592536602c602e5fe02038d20b6c82e33ff6aa554

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1333,7 +1333,7 @@
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
-			int columnCount = currentDataset.getColumnCount();
+			int columnCount = annotations.size();
 			int rowCount = currentDataset.getRowCount();
 			int passCount = renderer.getPassCount();
 			for (int pass = 0; pass < passCount; pass++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Chart25
### Patch Diff Hash-SHA-256:

481e970f67e8c2aefab5c6055b519cbaae2f939e83ff967ac0afd70a94795b26

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1329,7 +1329,7 @@
 		org.jfree.chart.renderer.category.CategoryItemRenderer renderer = getRenderer(index);
 		org.jfree.chart.axis.CategoryAxis domainAxis = getDomainAxisForDataset(index);
 		org.jfree.chart.axis.ValueAxis rangeAxis = getRangeAxisForDataset(index);
-		boolean hasData = !(org.jfree.data.general.DatasetUtilities.isEmptyOrNull(currentDataset));
+		boolean hasData = !(org.jfree.chart.plot.Plot.DEFAULT_INSETS.equals(org.jfree.chart.plot.Plot.DEFAULT_INSETS));
 		if (hasData && (renderer != null)) {
 			foundData = true;
 			org.jfree.chart.renderer.category.CategoryItemRendererState state = renderer.initialise(g2, dataArea, org.jfree.chart.plot.CategoryPlot.this, index, info);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Chart25
### Patch Diff Hash-SHA-256:

edcc956164fba890099e8ebb38d06a4b51fe016281d1ec730a7b1c1cf064a39b

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.data.KeyedObjects2D) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Chart25
### Patch Diff Hash-SHA-256:

283ffb8589a7379551c49979d604649487d70b241dee8b4ecfad72145141d346

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(minimumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Chart25
### Patch Diff Hash-SHA-256:

c8e4b1f86097b28dbf6f6ed8a2b27ba640d3209cb5cbe712eee27411e3ac57a0

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((minimumRangeValue) + (minimumRangeValue)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Chart25
### Patch Diff Hash-SHA-256:

56f6aed76f013a07ce28979bd974515453065ad5d8322dd611227be63f4347b1

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -32,7 +32,7 @@
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
-				result = rowData.getObject(columnKey);
+				result = rowData.getObject(row);
 			}
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Chart25
### Patch Diff Hash-SHA-256:

17f0cf4cded6516ac0d8cad9f36300a6f7ff6076e569aadff6a874e80dfb3f5a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (!(rowKeys.equals(rowKeys))) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Chart25
### Patch Diff Hash-SHA-256:

a8adefc9ce900d56ec379450b79ec7f70dfef26b4990599bc2d23a007b56f4a1

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (!(columnKeys.equals(columnKeys))) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Chart25
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Chart25
### Patch Diff Hash-SHA-256:

cce1e8d8d82574d79782d1c3222f015832115145564d248cb49408637d2ac757

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (row < row) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Chart25
### Patch Diff Hash-SHA-256:

a718a38204d1dc410fa850db270d010aa6641a86a542f415a25ed3498934ec94

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(maximumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Chart25
### Patch Diff Hash-SHA-256:

d915dda10c7a57889781bd4f0e37c9e087d75608f1a41a5985b582a06a30f1d9

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.data.Range) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Chart25
### Patch Diff Hash-SHA-256:

aec139fae583c81bb8619c4c6b3c3d995319377234599808ea702bb57efe523c

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((minimumRangeValue) > (minimumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Chart25
### Patch Diff Hash-SHA-256:

9c32c837d1ecdd38e9b5a6bc8658e008573ce75883d9f34caa2d0a12aea89456

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Chart25
### Patch Diff Hash-SHA-256:

c85fed8fa0c8c95c853125acb33ef10c8db27b6811d34729d52caba235ea1622

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -19,7 +19,7 @@
 	}
 
 	public int getRowCount() {
-		return org.jfree.data.KeyedObjects2D.this.rowKeys.size();
+		return -1;
 	}
 
 	public int getColumnCount() {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Chart25
### Patch Diff Hash-SHA-256:

b86e92b581fcf4075fd0208c22a3063967f1584d06afa87a00f37e756dd590aa

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey == (org.jfree.data.KeyedObjects2D.this)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Chart25
### Patch Diff Hash-SHA-256:

274f29c0fce48d912aa4dc09909af194e32bdd51eb85ac0d0c4c00086dcaa68c

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((maximumRangeValue) > (maximumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Chart25
### Patch Diff Hash-SHA-256:

42b5b93d34e3d316b7e7af375dcd8ddf04b6d5cff628c5a0c2c4ff0f2665c663

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValue)) || ((minimumRangeValue) < (minimumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Chart25
### Patch Diff Hash-SHA-256:

79a968ce70a3ab9391d2e54ff65d9402e89eca53e64c29ad77dcb9cd4f3d59ac

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rowKeys) instanceof org.jfree.data.Range) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Chart25
### Patch Diff Hash-SHA-256:

17017ce484645136b75437c161f5b722b8e2367ff1c9e43b6aceb58e609593a1

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rowKeys) instanceof org.jfree.data.KeyedObjects2D) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Chart25
### Patch Diff Hash-SHA-256:

4751ffe4f165c3b082cee9406538d50892b57ddfd186dbe2520a3ee66051af38

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((minimumRangeValueIncStdDev) > (minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Chart25
### Patch Diff Hash-SHA-256:

406f041235669344a71b69f91f275411a95e953f9ebf647072c09a2fdcf03990

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rowKeys) instanceof org.jfree.data.KeyedObjects2D) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Chart25
### Patch Diff Hash-SHA-256:

7f489e9648ed215d9e6e2b4dc913009ffc27b07bcd96b583d05524a53d332494

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((columnKeys) instanceof org.jfree.data.Range) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Chart25
### Patch Diff Hash-SHA-256:

08cfefa71ab5b79cfa84268aeec5348eff2ac14faeb67d95bd663b1d2106a33a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((columnKeys) instanceof org.jfree.data.KeyedObjects2D) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Chart25
### Patch Diff Hash-SHA-256:

d569e2ed2703e2d8e1d45a760109e9f22375383bdd4f273b8e0b763006958946

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((maximumRangeValue) + (maximumRangeValue)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Chart25
### Patch Diff Hash-SHA-256:

6cb2854cda71191d4e25bbff17a7efaee509da9f77d26fd6abcb48131f97b477

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(maximumRangeValue)) || ((maximumRangeValue) < (maximumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Chart25
### Patch Diff Hash-SHA-256:

e387db6d5b658246ea1e0f5fdee815aa3162a1846632fd276e3be3871e23073d

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((columnKeys) == null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Chart25
### Patch Diff Hash-SHA-256:

5f5559c1efc870f14cdc86532cc83be6c715600730fb6a15b2baae7c6725763f

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((columnKeys) instanceof org.jfree.data.Range) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Chart25
### Patch Diff Hash-SHA-256:

069c6a221e284589075972b6868c59ce5e4b925d8f17dc42c6afbe16ac353fa6

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (!(masd instanceof org.jfree.data.statistics.MeanAndStandardDeviation)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Chart25
### Patch Diff Hash-SHA-256:

1524745f9527a564d943e76e5f6301198545fe330228d43eff71819cf5af99dc

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(maximumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Chart25
### Patch Diff Hash-SHA-256:

0cef62ff9e3dac56d22710df3ed5e48ef664b706c01f27e73eebe7ab67097efd

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (row < 0) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Chart25
### Patch Diff Hash-SHA-256:

c7341d14cad356fce2d1064379338cdeed1896f4ba6ee8197989b05482a4edcf

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((minimumRangeValueIncStdDev) + (minimumRangeValueIncStdDev)) > (minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Chart25
### Patch Diff Hash-SHA-256:

f742e10826ce44a74163f0af5037a08187ff5f4230a969a1028f0a8c6d078c91

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValue)) || ((minimumRangeValue) > (minimumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Chart25
### Patch Diff Hash-SHA-256:

9af642a8aaf11599f7f922ca11b89bae9077044276044eda2c9fe4e5cc8c7c26

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (column < row) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Chart25
### Patch Diff Hash-SHA-256:

f09185028ebf03c24804c208851f6dadaeee92ad2f23633fb5782e5b877bbe5f

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((minimumRangeValue) - (minimumRangeValue)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Chart25
### Patch Diff Hash-SHA-256:

1b1a4ccb193ab8f3696d478d6cd070e7e7fbf36c4002f63c261b4da3badf16bc

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((minimumRangeValueIncStdDev) + (minimumRangeValueIncStdDev)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Chart25
### Patch Diff Hash-SHA-256:

562ad0bfa03cd10241a13f367080b9c111383905f93db8b951bf0bbcf2c1d48d

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValueIncStdDev)) || ((minimumRangeValueIncStdDev) < (minimumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Chart25
### Patch Diff Hash-SHA-256:

0e62c59909be8c030e2516b2ab0df2d6797bde64c9e907f2e4a1942fa9ed2601

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((maximumRangeValueIncStdDev) > (maximumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Chart25
### Patch Diff Hash-SHA-256:

2e7d04b063de21643d518ad45c5845076072409d600e8546b936dd4cedcf7d21

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (!(org.jfree.chart.util.ObjectUtilities.equal(result, result))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Chart25
### Patch Diff Hash-SHA-256:

43954ced32e5a88546eaba3519dd7f2ba4bf09476ff42d1468e379011b1178ac

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (result instanceof org.jfree.data.KeyedObjects2D) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Chart25
### Patch Diff Hash-SHA-256:

e12ae15a8ac528e21952e24b971f99751e57df9e0bfdea5f8d9ed7887d4a0cb8

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValueIncStdDev)) || (((minimumRangeValueIncStdDev) + (minimumRangeValueIncStdDev)) > (minimumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Chart25
### Patch Diff Hash-SHA-256:

ead06fb6b55f2c3b4cab544fb18f5199e2d3d991d3c44f2a1286ff23dd1f0d84

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rowKeys) == (org.jfree.data.KeyedObjects2D.this)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Chart25
### Patch Diff Hash-SHA-256:

03caaa79ebe09612fe093c2e5ed225af136439220d7f94f1bd675ace1624020b

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((maximumRangeValue) - (maximumRangeValue)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Chart25
### Patch Diff Hash-SHA-256:

6623b38ba72d29370307bd6a5d3ba5e156418cf6b74fd84e686d9bb821f203d7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -30,7 +30,7 @@
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
-			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
+			java.lang.Comparable columnKey = ((java.lang.Comparable) (rowKeys.get(row)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Chart25
### Patch Diff Hash-SHA-256:

acda3c240025c49f2879e87a63cf457769ef8ce61cca06696177f70574d7d744

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((minimumRangeValue) > (maximumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Chart25
### Patch Diff Hash-SHA-256:

d55fd49643470601050f0033b60185fd92873593e799d1705b6ed70f55ed0579

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValueIncStdDev)) || (((minimumRangeValueIncStdDev) - (minimumRangeValueIncStdDev)) < (minimumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Chart25
### Patch Diff Hash-SHA-256:

310753c0397f10230fd5befce4153ae4a6556b7ce8d1bb9d350ce6756beedcdf

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((maximumRangeValueIncStdDev) + (maximumRangeValueIncStdDev)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Chart25
### Patch Diff Hash-SHA-256:

43d5bc94e0d2ef03113756032a60bd7e1a33e84adac83c9e2bae894eb755e3f8

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(maximumRangeValueIncStdDev)) || ((maximumRangeValueIncStdDev) < (maximumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Chart25
### Patch Diff Hash-SHA-256:

eb141ccc77dfea612c0be15684175f6db9055a40863535c37ab37d28347a70f7

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((minimumRangeValueIncStdDev) - (minimumRangeValueIncStdDev)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Chart25
### Patch Diff Hash-SHA-256:

42670a12b5857a4ad60b0f54428b51b8b78447fa2b0fb3a5f690f55c4ba9008d

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (column < 0) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Chart25
### Patch Diff Hash-SHA-256:

22b5b8fa868a324f19858a5de6161301d28b0ae3cf90b682d65faac2879d955c

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValue)) || (((maximumRangeValue) - (minimumRangeValue)) < (minimumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Chart25
### Patch Diff Hash-SHA-256:

adf9becb658d70d1d481577a84108eaffc47174a563c4c26ddd1012001d18991

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((columnKeys) instanceof org.jfree.data.KeyedObjects2D) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Chart25
### Patch Diff Hash-SHA-256:

211129e64cd8fefc6df1f6ec34612501aad90d5e5f3a978ea48d63715f08e9bd

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((minimumRangeValue) + (maximumRangeValue)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Chart25
### Patch Diff Hash-SHA-256:

f5b641145eff756326059ce0b3c15ea4b0befb05eada714b2fb9d9ce1a2acf05

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(maximumRangeValue)) || ((maximumRangeValue) > (maximumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Chart25
### Patch Diff Hash-SHA-256:

b92ea289fa564971ce2721cbccc9d7ff6cb6de05a5ae34af8c86734dd1a5b267

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValueIncStdDev)) || ((minimumRangeValueIncStdDev) > (minimumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Chart25
### Patch Diff Hash-SHA-256:

9067681b72291ce3ff36a9e56c39e9c0feb76f4b8e00359f42ef107890531742

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((columnKeys) == (org.jfree.data.KeyedObjects2D.this)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Chart25
### Patch Diff Hash-SHA-256:

1f355ba005f842f32ea261a052e9a59e32c2e4106c0557fb088d0712f93ce458

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((maximumRangeValue) + (minimumRangeValue)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Chart25
### Patch Diff Hash-SHA-256:

8c0e4dbec7134dc7f0ead067a75e64fc13ef9a525b10e82ab0a19688784be7c0

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (result == (org.jfree.data.KeyedObjects2D.this)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Chart25
### Patch Diff Hash-SHA-256:

f0add8cedc54b78118675caaff6dc9f66582c9f178e160fb0924f84bd0c39251

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (rowData == null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Chart25
### Patch Diff Hash-SHA-256:

f8f289af7193242df672f3138c07213ebd4d0736cf2ef4f028586a9637517c77

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rows) == (org.jfree.data.KeyedObjects2D.this)) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Chart25
### Patch Diff Hash-SHA-256:

b5d8321702781304ee68e3a8a02a80f17485396ca807dc0fa570d4a4b4cdd845

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (result == (org.jfree.data.KeyedObjects2D.this)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Chart25
### Patch Diff Hash-SHA-256:

85aa3f5f43980598d18c06bb82f821c5b173220869c5183603e9f7d6cac2def0

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (!(rows.equals(rows))) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Chart25
### Patch Diff Hash-SHA-256:

8d9e2b9cc0b7f36058daada182b5390df20c76e6ae3b5ac70bebde28fa42d987

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (!(rowKeys.equals(rowKeys))) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Chart25
### Patch Diff Hash-SHA-256:

e105593879a852d49147e28893897b5d01845c273309a862bcb002acd028adbb

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((minimumRangeValue) < (minimumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Chart25
### Patch Diff Hash-SHA-256:

f886ac495b516badf10c3f151763ac97d2ee439178553aea03d67d71038009b9

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(maximumRangeValueIncStdDev)) || ((maximumRangeValueIncStdDev) > (maximumRangeValueIncStdDev))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Chart25
### Patch Diff Hash-SHA-256:

c77ecf036103dc82851b9cdf6a313278a202f33ac985dda3ef6d0c42675d96ae

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((minimumRangeValue) + (minimumRangeValue)) > (maximumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Chart25
### Patch Diff Hash-SHA-256:

f17aa7d2f240c449494c5043ed5330dd2e8e9f6f67699246747bd503e2b8d038

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((columnKeys) instanceof org.jfree.data.KeyedObjects) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Chart25
### Patch Diff Hash-SHA-256:

61a4f861fb41318ad1dd8c2e0ea9f89002b0496a0f216659a6686e1204780083

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (row < 0) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Chart25
### Patch Diff Hash-SHA-256:

f8c16fd369d41ac00f7ad4b1af87ea9c377420b9923ccb3cca4eb0bf38d04f91

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (result instanceof org.jfree.data.Range) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Chart25
### Patch Diff Hash-SHA-256:

ae15c89b33f9f5401b683fe176f76cff0a60776c6d8b1bc76c493afa446f2914

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((minimumRangeValueIncStdDev) - (minimumRangeValueIncStdDev)) < (minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Chart25
### Patch Diff Hash-SHA-256:

c425d9d24fad74c29eab24eb462e20b5378750b115445527d37394390c72bb0c

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((maximumRangeValue) < (maximumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Chart25
### Patch Diff Hash-SHA-256:

43ef3e9c6e743734dc9642c5579002439675dab035d52311eb8c89c187170cda

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (column < 0) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Chart25
### Patch Diff Hash-SHA-256:

5544bf68fdf72f9ea4251216e1797a1ae65b11cff5abf81d5975abdc849d8e88

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (columnKey instanceof org.jfree.data.KeyedObjects) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Chart25
### Patch Diff Hash-SHA-256:

7b06032919fb1b1d493ac30ea6715c2136f1daf14ac0e119d51306a492f9efd5

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((minimumRangeValueIncStdDev) < (minimumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Chart25
### Patch Diff Hash-SHA-256:

6e1ef957e1b9aa843bbb0bc2f87396352d71730f1f448b50cd8b69db17374565

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (columnKeys.equals(result)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Chart25
### Patch Diff Hash-SHA-256:

acf260f13f4fa3a61b97003d91923b319aa8814fd7ba6104e880b4515dbafa36

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rows) == (org.jfree.data.KeyedObjects2D.this)) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Chart25
### Patch Diff Hash-SHA-256:

dd816a4c58ddb7569cfd6ec62a5eaa63ded55c95c1c8555dcb799f77ca62f0c9

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(minimumRangeValue)) || ((maximumRangeValue) < (minimumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Chart25
### Patch Diff Hash-SHA-256:

2c22f98ffc821a57fe9ba2d67f448d1b6e5366f101ec5db05ad5f578235bbfba

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((maximumRangeValueIncStdDev) < (maximumRangeValueIncStdDev)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Chart25
### Patch Diff Hash-SHA-256:

fae01e688da10e13e51c4430e09a110f6e2076ebc670ee71a71d75943aabbc65

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (java.lang.Double.isNaN(((maximumRangeValueIncStdDev) - (maximumRangeValueIncStdDev)))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Chart25
### Patch Diff Hash-SHA-256:

c168475e947c1370b071c28ff701bfd55107b6672364763534a6b2f8c9d89a7e

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (result instanceof org.jfree.data.KeyedObjects2D) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Chart25
### Patch Diff Hash-SHA-256:

d0a2ab5a610c20178f74b36360556e905146d765a4b6fb618889451953735a5a

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if (result != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Chart25
### Patch Diff Hash-SHA-256:

dbca1e0474fcb582034c9152c175392802bea718a7fc9b78133033a93adf10fa

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((columnKeys) == null) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Chart25
### Patch Diff Hash-SHA-256:

1b7d7bf52fa5c0c102e0635310b3adee6a9f2881d736ea46218c5b709f8115f6

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rowKeys) instanceof org.jfree.data.KeyedObjects) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Chart25
### Patch Diff Hash-SHA-256:

ddeb86f4b678c07b68329d64352a4b8507a083c18ef0f2b014760856a90c575c

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if (((maximumRangeValue) - (minimumRangeValue)) < (minimumRangeValue)) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Chart25
### Patch Diff Hash-SHA-256:

a4015665379de47b6681e15579a3821f55c65a190c517e91276cafe9a1f764cc

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((columnKeys) instanceof org.jfree.data.KeyedObjects) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Chart25
### Patch Diff Hash-SHA-256:

6dcb0d6d275810ab7c8f68873cd09200bb4f5004c535a527acc8a60cd5de348c

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -29,7 +29,7 @@
 	public java.lang.Object getObject(int row, int column) {
 		java.lang.Object result = null;
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
-		if (rowData != null) {
+		if ((rows) instanceof org.jfree.data.Range) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
 			if (columnKey != null) {
 				result = rowData.getObject(columnKey);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Chart25
### Patch Diff Hash-SHA-256:

b7743a77197e5f281874078071b3539e586319e75a92c5201e3d18f88d2badf7

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if ((rows) == null) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Chart25
### Patch Diff Hash-SHA-256:

5fe3099ce52700c9b8de990a0676356d48f673b8315cec4d816d64f45fc0f34b

### Patch Diff:
```
--- /original/org/jfree/data/KeyedObjects2D.java	
+++ /fixed/org/jfree/data/KeyedObjects2D.java	
@@ -31,7 +31,7 @@
 		org.jfree.data.KeyedObjects rowData = ((org.jfree.data.KeyedObjects) (org.jfree.data.KeyedObjects2D.this.rows.get(row)));
 		if (rowData != null) {
 			java.lang.Comparable columnKey = ((java.lang.Comparable) (org.jfree.data.KeyedObjects2D.this.columnKeys.get(column)));
-			if (columnKey != null) {
+			if (result != null) {
 				result = rowData.getObject(columnKey);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Chart25
### Patch Diff Hash-SHA-256:

a9f508396834f329ab57b2056b3cb109fba00f86fee84726bf5160cf2164778b

### Patch Diff:
```
--- /original/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
+++ /fixed/org/jfree/data/statistics/DefaultStatisticalCategoryDataset.java	
@@ -25,7 +25,7 @@
 	public java.lang.Number getMeanValue(int row, int column) {
 		java.lang.Number result = null;
 		org.jfree.data.statistics.MeanAndStandardDeviation masd = ((org.jfree.data.statistics.MeanAndStandardDeviation) (org.jfree.data.statistics.DefaultStatisticalCategoryDataset.this.data.getObject(row, column)));
-		if (masd != null) {
+		if ((java.lang.Double.isNaN(maximumRangeValue)) || ((minimumRangeValue) > (maximumRangeValue))) {
 			result = masd.getMean();
 		}
 		return result;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---