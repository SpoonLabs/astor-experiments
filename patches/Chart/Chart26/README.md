
# Patches of Chart26 from Defects4J 
Total patches 138
## Patch 1 of bug id Chart26
### Patch Diff Hash-SHA-256:

5625f7624f4ae1e1e08ea8b562e1fae8dedb6fd649d62204c62d1f4269c0cbd5

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (((fixedDimension) > 0.0) && (hotspot != null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart26
### Patch Diff Hash-SHA-256:

74a93a391b7712b0f648416c6b045300c95a5b50f095cfaa88d2a24b3a621c18

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((plotState != null) && ((plotState != null) && ((plotState.getOwner()) != null))) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart26
### Patch Diff Hash-SHA-256:

ebcbb9dbeee5ab54b348af38503157b94b9d445214eba0b2ba1a290c2c334f26

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((plotState != null) && ((labelAngle) > 0.0)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart26
### Patch Diff Hash-SHA-256:

824fa56d179e9a18c4445919cb799ffec6b39c81bd9888f18cb3313b7600287d

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (((labelAngle) > 0.0) && (hotspot != null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart26
### Patch Diff Hash-SHA-256:

a5828ca7b70cef78afe224d27695d62ed602a73adb9c5334359fcb4d46c934d8

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (rangeCrosshairStroke) != null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart26
### Patch Diff Hash-SHA-256:

da48cf8d6ccb3e88f6294eaea99d918e8c26e6c787fb783cbd5fd94c54a5ea66

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((labelURL) != null) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart26
### Patch Diff Hash-SHA-256:

4866312d8941c1a774b93f016678a824f5e303e66bd14313fa39fc7bcf3339d5

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if (label != null) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart26
### Patch Diff Hash-SHA-256:

8a582bd6de825519f3c49021182e2566b0de675558495e853c70081b482c9c2f

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (weight) < (org.jfree.chart.plot.CategoryPlot.this.domainAxes.size());
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart26
### Patch Diff Hash-SHA-256:

d1bae23f1f1c251ead9089c229e02440c0a79c59a02a21cf7a7d9712e175b335

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (DEFAULT_GRIDLINE_STROKE) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart26
### Patch Diff Hash-SHA-256:

dfbcfba14a67c520ddc176b0efdc629383fd6911ee8f3f797af0aae5aeb54964

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (state == null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart26
### Patch Diff Hash-SHA-256:

24a6c432fe0315401143b7e649b116b31a3906751746b7576e390d716f0c751d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (((org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) - (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW)) >= 0) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart26
### Patch Diff Hash-SHA-256:

4d05901947e1734838d46e32619b7e6c5fd607a650edf36cfdad10f502063129

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) >= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart26
### Patch Diff Hash-SHA-256:

efaedadad6f673756d39e3142ebd2c3f69df81ef9fe6c930059b01ba43d6b5d7

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (((rangeCrosshairValue) > 135) && ((rangeCrosshairValue) < 225)) || (((rangeCrosshairValue) < 45) && ((rangeCrosshairValue) > (-45)));
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart26
### Patch Diff Hash-SHA-256:

3750c2e7be6301eb2d05c1ae98305e521a013ececc63192daa73c08c26e8e5c6

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if (!((labelPaint) instanceof org.jfree.data.xy.XYIntervalSeriesCollection)) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart26
### Patch Diff Hash-SHA-256:

1c3c741b517bcd79a6cf2cc14c76328ff08e4298c9aec256b81990a80e85750d

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (!((domainGridlineStroke) instanceof org.jfree.chart.block.BlockContainer)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart26
### Patch Diff Hash-SHA-256:

392d98b1c0a0ab6fc6ec8dba2c029630762907d98f7c81e305b6432ab79dd67a

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (((tickMarkOutsideLength) < (tickMarkOutsideLength)) && (hotspot != null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart26
### Patch Diff Hash-SHA-256:

566e1638344e703b08a6a5a7812865888ecaecc80b47454494a52f2c6b04b509

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (super.equals(DEFAULT_AXIS_LABEL_FONT)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart26
### Patch Diff Hash-SHA-256:

b5e97a27c76cabf42c13beb10d6e3359dd108b2c310ce4f3d1e3b16781cbb347

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW) == (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart26
### Patch Diff Hash-SHA-256:

bd6182edc1177b03f6e7e4e709eac0beb226ebdc873196dd8d1eba8340edb964

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (dataArea == null) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Chart26
### Patch Diff Hash-SHA-256:

6b392e78368fb40d7bffa6a096e7bef6f1f293b2ac5ecf3309243058b0d771eb

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = !((domainGridlinePaint) instanceof org.jfree.chart.plot.ThermometerPlot);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Chart26
### Patch Diff Hash-SHA-256:

241a35cc945bab2f06eea98be23d7f07f8c60aa507a757cec2cf1ae54ea277d9

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = true;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Chart26
### Patch Diff Hash-SHA-256:

58776af0e9eefca9eea851c0d74bf5e2026984d4888e975775fa256c268b22bb

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (foregroundRangeMarkers) != null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Chart26
### Patch Diff Hash-SHA-256:

47afaa4993f99a04e8f242b62c9569106dd5b4056beb112fec8f067d2dc3b47f

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -108,7 +108,7 @@
 	}
 
 	public boolean isVisible() {
-		return org.jfree.chart.axis.Axis.this.visible;
+		return (plot) instanceof org.jfree.chart.plot.PiePlot3D;
 	}
 
 	public void setVisible(boolean flag) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Chart26
### Patch Diff Hash-SHA-256:

4f001fa5279e7f78ae8de5aa25e125a32f53c1116c71dedc8ce4b46c32990283

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = ((((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) < 1) || (((weight) < 1) && ((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) < 5))) || ((org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW) < (4 - (weight)))) || ((anchorValue) >= (anchorValue));
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Chart26
### Patch Diff Hash-SHA-256:

985a101c2ba70c34f3b1ce674d6005652557d297a84691c0dea66391304463cb

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((fixedDimension) >= (fixedDimension)) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Chart26
### Patch Diff Hash-SHA-256:

87332a4379b5f1900619ed7f655b16bdd57b1978bb6e5df8c4a354ec6129af28

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (rangeCrosshairPaint) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Chart26
### Patch Diff Hash-SHA-256:

8f54738b7275002cb17e2ef0793db1e7b753445961f3608914fd8892cfd4e542

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = ((rangeCrosshairVisible) || (DEFAULT_RANGE_GRIDLINES_VISIBLE)) || (DEFAULT_RANGE_GRIDLINES_VISIBLE);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Chart26
### Patch Diff Hash-SHA-256:

a32afb0066559e9158ac630f91ac3bb684522cd8383d3d0eada872701a5d764f

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = !((org.jfree.chart.plot.Plot.DEFAULT_LEGEND_ITEM_CIRCLE) instanceof org.jfree.chart.urls.StandardXYURLGenerator);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Chart26
### Patch Diff Hash-SHA-256:

051a119ecd765724544549052ab76f27aba9c39ec917694970b1fe90e9585245

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (rangeCrosshairValue) >= (rangeCrosshairValue);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Chart26
### Patch Diff Hash-SHA-256:

9ebd34c864298f179745f75212a32d35afce384674fc353d08a27ef737721cc3

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (!(java.lang.Double.isNaN(((rangeCrosshairValue) - (rangeCrosshairValue))))) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Chart26
### Patch Diff Hash-SHA-256:

bb576ecc6b05d33aec8b8692beca651c40f5afe0725fed55fd21a3833d6991c1

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (getOutlinePaint()) != null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Chart26
### Patch Diff Hash-SHA-256:

158131055dbb460a00b434b4b9d71351d24dd0de0fac45cb346d22881401aac5

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = !((rangeCrosshairStroke) instanceof org.jfree.chart.needle.LongNeedle);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Chart26
### Patch Diff Hash-SHA-256:

501ca7bc72d740dd5117e5dc2dc5d9cf2eda77b60d310af17d961a21665ac948

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (java.lang.Double.isNaN(((labelAngle) - (fixedDimension)))) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Chart26
### Patch Diff Hash-SHA-256:

cb03e0243faaf0c9fca299c155efbf9b3b0b50ce40286cc14c7ed3d9380fdd33

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (anchor == null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Chart26
### Patch Diff Hash-SHA-256:

c161bdc525e815c451ef70b3499726ddd833631bc5f0e3806fc1cb64db630f61

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (((fixedDimension) == 90) || ((fixedDimension) == 270)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Chart26
### Patch Diff Hash-SHA-256:

36c8db7568ea6738e053c93c48e22b948f219e2ef8b17ec60c96ca4979775e26

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -108,7 +108,7 @@
 	}
 
 	public boolean isVisible() {
-		return org.jfree.chart.axis.Axis.this.visible;
+		return (DEFAULT_TICK_LABEL_PAINT) instanceof org.jfree.chart.axis.SegmentedTimeline.Segment;
 	}
 
 	public void setVisible(boolean flag) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Chart26
### Patch Diff Hash-SHA-256:

991f00de73f6164e651396b67461af258d8feef629bf2263c77b134d408b8ce4

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = parentState == null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Chart26
### Patch Diff Hash-SHA-256:

5cbfa0f141407b845f52dec6212c744de876e9e313c317c450818536c285066a

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -108,7 +108,7 @@
 	}
 
 	public boolean isVisible() {
-		return org.jfree.chart.axis.Axis.this.visible;
+		return false;
 	}
 
 	public void setVisible(boolean flag) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Chart26
### Patch Diff Hash-SHA-256:

efe71c2f2517be99241da13e3637b9ea43a35116a3974f0f9a1b21650ac8182e

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -108,7 +108,7 @@
 	}
 
 	public boolean isVisible() {
-		return org.jfree.chart.axis.Axis.this.visible;
+		return (DEFAULT_TICK_MARK_STROKE) instanceof org.jfree.data.xy.XYDataItem;
 	}
 
 	public void setVisible(boolean flag) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Chart26
### Patch Diff Hash-SHA-256:

1a9b2518f788ed84ac0a9bb7fc19c3503ece649bae6e22012e0270fcb9390a66

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (super.equals(labelToolTip)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Chart26
### Patch Diff Hash-SHA-256:

a2032ec9801c750fc75bb5bb73e4fd08137c92fe4546da893c2b46d6585a52a5

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((DEFAULT_AXIS_LABEL_INSETS) == null) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Chart26
### Patch Diff Hash-SHA-256:

3be186cc6cc4a72110ee56c90983a60ee7ff607a05a9b63dfbd66c4ff0d68ee3

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = isRangeGridlinesVisible();
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Chart26
### Patch Diff Hash-SHA-256:

8ac9099b0f7b81912493638a51def1eb5f20c05d75996feac626892fba58e181

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if (((tickMarkOutsideLength) - (tickMarkInsideLength)) != 0.0) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Chart26
### Patch Diff Hash-SHA-256:

f3ff61ca67a441fb13745e2d448e042f45522b82d285a94442768652a3a680f3

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((weight) >= 0) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Chart26
### Patch Diff Hash-SHA-256:

8ff475499a17b86b42a1819d5673d41d9920d2d4e8f59a1c1b91ae38bd4db280

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((tickMarkStroke) == null) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Chart26
### Patch Diff Hash-SHA-256:

be4e1fc6120c8159b9310707c6a82041a05f5c3e7b5e6b1cb842ddb03285b47f

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = area != null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Chart26
### Patch Diff Hash-SHA-256:

a15a53f315bfcadf264e8ca82c90809135b8a12bbca2629b1e014cb485a161d8

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (org.jfree.chart.plot.Plot.DEFAULT_LEGEND_ITEM_BOX) != null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Chart26
### Patch Diff Hash-SHA-256:

3cfdee46ede14e253d5370b31822a37891bb1156b399a202c92edb5caa0fcfe2

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = true;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Chart26
### Patch Diff Hash-SHA-256:

9ef7cb59e5fcb7fc4325d4d49120b4fc7a74cf7bb9b470e13c834e721f86e5b3

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (true) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Chart26
### Patch Diff Hash-SHA-256:

3252959645a0d55ec4baaefcff69fbf85ba329b06b89684e1b063c3793693988

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (!(org.jfree.data.time.SerialDate.isValidWeekdayCode(org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW))) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Chart26
### Patch Diff Hash-SHA-256:

5c86aff7d24f7eff01acb79948e06dd93c53407e172ec38958b53ef33b0e6366

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((domainGridlinePosition) != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Chart26
### Patch Diff Hash-SHA-256:

25ce13705b300e6a3276f358996657285ae4788ee268b1128ebfee54adf3fbcf

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (!((rangeCrosshairStroke) instanceof org.jfree.chart.title.PaintScaleLegend)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Chart26
### Patch Diff Hash-SHA-256:

6ecb2d25b0c6677f04ce6ca557e144553c8f94992157bdd43fd3496fed21e506

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = ((rangeCrosshairValue) < 45) && ((rangeCrosshairValue) > (-45));
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Chart26
### Patch Diff Hash-SHA-256:

fe45ed9e4309ce82e9f2dc94fb4677890c60a8134285c2bd1ec883f635ccd83a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = !((backgroundDomainMarkers) instanceof org.jfree.data.xy.YIntervalSeriesCollection);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Chart26
### Patch Diff Hash-SHA-256:

d7ef3890588f7a40548b10b910be3a1facd6a75a171088a05503a75d6cbc5128

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = 0 == (weight);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Chart26
### Patch Diff Hash-SHA-256:

3fbf90f17798eb03c3b0dec5d8f52aecc2eaf03072deed443a298dfc9715ec31

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((org.jfree.chart.plot.Plot.DEFAULT_OUTLINE_STROKE) != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Chart26
### Patch Diff Hash-SHA-256:

486399430837689d6044ac84a7639c30c7efe44b2e5ac1af53485c39dd2f4461

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (((plotState != null) && ((plotState.getOwner()) != null)) && (hotspot != null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Chart26
### Patch Diff Hash-SHA-256:

2ce03c9143e5e70a914dfac544550ad303f775d3769cb0867b2b28176f4527fb

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
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
## Patch 59 of bug id Chart26
### Patch Diff Hash-SHA-256:

fd165301092ecb7423708c93a21bf6af9c90ac3cff76e10127920f31bc9c6b0d

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((DEFAULT_AXIS_LINE_STROKE) instanceof org.jfree.chart.axis.TickUnit) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Chart26
### Patch Diff Hash-SHA-256:

469b9d85a7004d30739bfc7a4aa0e5ece59535d0367036a37f18c27840b42808

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (org.jfree.chart.plot.CategoryPlot.this.foregroundDomainMarkers) != null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Chart26
### Patch Diff Hash-SHA-256:

9331d0651880e4b4df4e372dd84825497d8fae4b2cb00e7a5981778e67268a6c

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((getLabel()) != null) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Chart26
### Patch Diff Hash-SHA-256:

52ec98667993dc63cb541a3544d7c99ed24fb28da078cca07ca38fae68a97fa2

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((DEFAULT_AXIS_VISIBLE) != (DEFAULT_TICK_LABELS_VISIBLE)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Chart26
### Patch Diff Hash-SHA-256:

c32fc7feab59615fc071b21514e99657413d6946403f68e2aabef96ae63be8a1

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((DEFAULT_CROSSHAIR_PAINT) != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Chart26
### Patch Diff Hash-SHA-256:

00e22fd588c77e23fae8bea209bd79c15f5ace56f827be20a532b2664435454f

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((tickLabelInsets) == null) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Chart26
### Patch Diff Hash-SHA-256:

ed6bc870a99515099b43859b179b7aa1c1939950e5474d6d7cdce9aab9c7d564

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = ((domainGridlineStroke) != null) && ((domainGridlinePaint) != null);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Chart26
### Patch Diff Hash-SHA-256:

a8b75211d3b874883e0892921127d7492f3465c25cbad008fc11be8e96fa4b75

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (weight) >= 0;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Chart26
### Patch Diff Hash-SHA-256:

71ed3968dc546a3a18e0a38347834ef5ae5ae413a41747ee59bf071da880e09e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((org.jfree.chart.plot.CategoryPlot.this.backgroundRangeMarkers) != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Chart26
### Patch Diff Hash-SHA-256:

0ba67066c06ea10f3b2c9ef22f107d11a7032dd54016af3293bba1ba9a8f7043

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
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
## Patch 69 of bug id Chart26
### Patch Diff Hash-SHA-256:

101b8f763cc46fb895a0f5fd1079e94deb1e08c080c727daf45fd66df99385cf

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (insets == null) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Chart26
### Patch Diff Hash-SHA-256:

203173ae5f773b4b4c3f8dbed24544397853f88141ca74101fd321d083cfd057

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((fixedDimension) <= 0.0) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Chart26
### Patch Diff Hash-SHA-256:

ed40e3c70f0c708648b82a791c50c6dc2e42ff481ca99cd734914a60ec127bff

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((((plotArea.getWidth()) + (DEFAULT_TICK_LABEL_INSETS.getLeft())) + (DEFAULT_TICK_LABEL_INSETS.getRight())) > (fixedDimension)) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Chart26
### Patch Diff Hash-SHA-256:

e3dde8d24fae3dc7189e34ae17c37e3f3e74a95af37fd5277b582d658f63ff3b

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -108,7 +108,7 @@
 	}
 
 	public boolean isVisible() {
-		return org.jfree.chart.axis.Axis.this.visible;
+		return (labelAngle) < (labelAngle);
 	}
 
 	public void setVisible(boolean flag) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Chart26
### Patch Diff Hash-SHA-256:

d5944160aa7223e9fe99680e1ab340bbf48b68a4afb2a9c141b2d82f4eb43741

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((label == null) || (labelInsets.equals(org.jfree.chart.axis.Axis.this.labelInsets))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Chart26
### Patch Diff Hash-SHA-256:

eebaa21692b6ef7338467a2ee9c37d671669dc219b94548b9d4eb80eaa7d1c78

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if (((visible) && (visible)) || (label.equals(""))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Chart26
### Patch Diff Hash-SHA-256:

350c6e4821d0481a30ee78e992a24a5b18c8cfb4d6cbcb00a01d8b5a08d317c8

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (labelBounds instanceof org.jfree.data.general.ValueDataset) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Chart26
### Patch Diff Hash-SHA-256:

0e66988a32acd27aefdad48bbd5a2302b0b28ecdf8c350fa86ee4e781e3acb38

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (weight) <= 180;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Chart26
### Patch Diff Hash-SHA-256:

5da4848e1b9a112d694607f2828a12dbdc6cd36c187f33a0d99b93d1384a604e

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
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
## Patch 78 of bug id Chart26
### Patch Diff Hash-SHA-256:

b2808b54e58d09247d7b6b8fa9e057489019ecf0f88ca5d0c272fefc9cd6d19a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((domainGridlineStroke) != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Chart26
### Patch Diff Hash-SHA-256:

812c564a0a7f37b17a0bf775e18f9495ee0f7a99866443ed38091ecbcd1b07fe

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if ((weight) == 0) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Chart26
### Patch Diff Hash-SHA-256:

bf7fe9c7da908591423259a2584000f25fe676b9b4dd30781ae31f7c80144070

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (((domainGridlinePaint) != null) && ((domainGridlineStroke) != null)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Chart26
### Patch Diff Hash-SHA-256:

478d899748aaea31b26482740fb19074d51f653b86f73e8f09a44dcfbffafb71

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if (!(java.lang.Double.isNaN(labelAngle))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Chart26
### Patch Diff Hash-SHA-256:

1dc24408b7f53f353e5718695d26cd4b968dfbc959b8e24dacc56fb16e67355a

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if (!(java.lang.Double.isNaN(fixedDimension))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Chart26
### Patch Diff Hash-SHA-256:

8f1955568a0a4b8158ada819f322240064ec8e3cae249248978fa5b75ff1367a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (anchorValue) >= 0.0;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Chart26
### Patch Diff Hash-SHA-256:

e3566dfdcce1fd801fa8c1ac2950844225dba4a71c3e8dc5569e19fb6cf4e16a

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((labelFont.equals(labelFont)) || (label.equals(""))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Chart26
### Patch Diff Hash-SHA-256:

1e9794f08f8df93b40dbfb2bda205182b889a07ecfdc786ba61f08866ffe39fa

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (b1 || ((org.jfree.chart.plot.Plot.ZERO) != null)) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Chart26
### Patch Diff Hash-SHA-256:

acd6291263214c8b459ab025e0ec808dc8ee9ad69cf5c91a628e953a21033db9

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((label == null) || (org.jfree.chart.axis.Axis.this.labelFont.equals(labelFont))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Chart26
### Patch Diff Hash-SHA-256:

b3de3e3b062214c37745b1e3b1018525c7e17dec1e620edebf751048154a1608

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -108,7 +108,7 @@
 	}
 
 	public boolean isVisible() {
-		return org.jfree.chart.axis.Axis.this.visible;
+		return (labelInsets) == null;
 	}
 
 	public void setVisible(boolean flag) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Chart26
### Patch Diff Hash-SHA-256:

5a946f42ae9bb3368caa4204c09c4531fa1ce25f4fae7aea575e7387784dee8a

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1142,7 +1142,7 @@
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
-		if (b1 || b2) {
+		if (g2 != null) {
 			return ;
 		}
 		if (state == null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Chart26
### Patch Diff Hash-SHA-256:

d59983f5e4a96d668ba934756e9c1d0b782632397f49d9b18780e352bb3702cb

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -265,7 +265,7 @@
 		double w = area.getWidth();
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
-		double r = calculateRightInset(w);
+		double r = area.getMaxX();
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
 		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Chart26
### Patch Diff Hash-SHA-256:

8aa71fcdcfe82aa1cc00cc8df0c7a323e4d4fe171b3e64147d2a3d8f62a0a840

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (java.lang.Math.abs(anchorValue)) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Chart26
### Patch Diff Hash-SHA-256:

6d7759230002f30e49eeb8469dafbc3e6478bfaf9ac80ae8131ba8f0ee0cfc57

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((1 - (top)) - b));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Chart26
### Patch Diff Hash-SHA-256:

390c2a3fb0facde5c8202fc9e157100d08b7c15410b96e14e289bf7738b10e16

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -262,7 +262,7 @@
 	}
 
 	public void trim(java.awt.geom.Rectangle2D area) {
-		double w = area.getWidth();
+		double w = calculateBottomOutset(top);
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Chart26
### Patch Diff Hash-SHA-256:

a2aea9813f5ba72a79b5d319b626697a959d4c809e0c48f95dd1bc41abb9f716

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -266,7 +266,7 @@
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
-		double t = calculateTopInset(h);
+		double t = (area.getX()) + h;
 		double b = calculateBottomInset(h);
 		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Chart26
### Patch Diff Hash-SHA-256:

2aa3878fede55b668859edcbbe40b96e88eb8b772f8de86a908454ccfda16d67

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), calculateLeftInset(area.getWidth()), ((h - t) - b));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Chart26
### Patch Diff Hash-SHA-256:

5a7ecf120c66918c1f29d53e51836cfc50810a61e8d1fa1049e78c568513a7e6

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -263,7 +263,7 @@
 
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
-		double h = area.getHeight();
+		double h = calculateBottomOutset(left);
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Chart26
### Patch Diff Hash-SHA-256:

5f03992838e14ffdf102e922943d19ca3640e71b5476b02a20f279c426e3424f

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -262,7 +262,7 @@
 	}
 
 	public void trim(java.awt.geom.Rectangle2D area) {
-		double w = area.getWidth();
+		double w = calculateTopInset(area.getHeight());
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Chart26
### Patch Diff Hash-SHA-256:

9df266410118c91b2a37e56b86cb0d4de8eeef8fb274c7d96dbea60cc305b082

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + (top)), ((area.getY()) + (top)), (((top) - (top)) - (top)), (((top) - (top)) - (top)));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Chart26
### Patch Diff Hash-SHA-256:

d053afdcafc8471e35a9681dc14378756eb85f8784c2ad3cbee0b64a48c512b6

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (fixedDomainAxisSpace) == null;
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Chart26
### Patch Diff Hash-SHA-256:

d6de31592b2a3df38862f1f3c752182155bae3e787f9bca43640b74ead7703c2

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((plotState != null) && (labelBounds == null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Chart26
### Patch Diff Hash-SHA-256:

e285044d4ad1ef052618a87092c68f97c4a63ffef14323178b65a95382244c9e

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -262,7 +262,7 @@
 	}
 
 	public void trim(java.awt.geom.Rectangle2D area) {
-		double w = area.getWidth();
+		double w = java.lang.Math.max(area.getMinY(), java.lang.Math.min(top, area.getMaxY()));
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Chart26
### Patch Diff Hash-SHA-256:

8a29b0545a67b4a8a2ed37dee7c9d76764315d75604cc1264de15eb0037d813b

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -263,7 +263,7 @@
 
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
-		double h = area.getHeight();
+		double h = calculateTopInset(area.getHeight());
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Chart26
### Patch Diff Hash-SHA-256:

cc0f71c4b7b42da014a0995f7b38f12b054abf94307906b811576d94b59f53d8

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -263,7 +263,7 @@
 
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
-		double h = area.getHeight();
+		double h = calculateBottomInset(area.getHeight());
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Chart26
### Patch Diff Hash-SHA-256:

9fc0b4734f4378d0cf4225d62bdf4b6fc9b2015e155fe70df33dd4edbbd59e74

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -446,7 +444,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		plot.addChangeListener(org.jfree.chart.JFreeChart.this);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -727,31 +725,3 @@
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
## Patch 104 of bug id Chart26
### Patch Diff Hash-SHA-256:

cc5e928d7df5b9f4a47179d34dc3f762199360d4cb403e594a1613ccfc68c391

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((font == null) && (hotspot != null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Chart26
### Patch Diff Hash-SHA-256:

70ab282e15028ab0a22c1dfd8dca2083978ddc40f0fb7542c2c795042b5f7103

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -263,7 +263,7 @@
 
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
-		double h = area.getHeight();
+		double h = calculateBottomInset(top);
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Chart26
### Patch Diff Hash-SHA-256:

ba40899307f80ea82b6716b88ff2cfaa91cd193061829c4483ec1d255e400eea

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
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
## Patch 107 of bug id Chart26
### Patch Diff Hash-SHA-256:

f04200fbcc2c0cb395aaa61380c0666104d83c643baeca79a5e61fcff0f0dc41

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), (((area.getWidth()) - h) - w));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Chart26
### Patch Diff Hash-SHA-256:

8aca610a95e87630371f77c31e5edc6464331f59162fbf16644e4220ceda4c5d

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -263,7 +263,7 @@
 
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
-		double h = area.getHeight();
+		double h = calculateBottomOutset(area.getHeight());
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Chart26
### Patch Diff Hash-SHA-256:

2562bbb8d1058eeb7a167909c4d1e7e62f0d6cf5e02b1fcc15ebd31b303da1dd

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((label == null) || (labelFont.equals(labelFont))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Chart26
### Patch Diff Hash-SHA-256:

585b7ee287ebdc3c9c407acb765205e9fa0baca64c8ccaaf7b340df3599be821

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if (((getLabel()) != null) || (label.equals(""))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Chart26
### Patch Diff Hash-SHA-256:

93817fbb3f746c9f83b874611f613efb34c82dc8ef117ef54866a121a2e8fe2d

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((top) / ((1 - (top)) - (top))), ((h - t) - b));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Chart26
### Patch Diff Hash-SHA-256:

9a164378589c77f005a1a1a1e65c30025da4264bf097ad080c5e24f62da9f8c6

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((top) - (top)));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Chart26
### Patch Diff Hash-SHA-256:

3e560cfaa411fd5d4480686a36fed7decb3e0efc614c466e9a3de81dd37cc41b

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (axisOffset.calculateTopOutset(area.getHeight())) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Chart26
### Patch Diff Hash-SHA-256:

8cb3f814e1cced099bfc28fea020c00f60d7e8fdc3b9bb556ae31ffe642a3692

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((tickMarkInsideLength) <= 0.0) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Chart26
### Patch Diff Hash-SHA-256:

73b0e048ea17a3601f33bfec3724f441f3b8f24be8cb193afd688fde287e7150

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -262,7 +262,7 @@
 	}
 
 	public void trim(java.awt.geom.Rectangle2D area) {
-		double w = area.getWidth();
+		double w = calculateBottomInset(top);
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Chart26
### Patch Diff Hash-SHA-256:

d296dc72a0d8f760865d2d83265a7f3fb4d6d2af680b653c556f65fcd80bd893

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -263,7 +263,7 @@
 
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
-		double h = area.getHeight();
+		double h = calculateBottomOutset(top);
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Chart26
### Patch Diff Hash-SHA-256:

0d39cb4ef21be87eda71327d03643cab034be462035785d086fab58aa7ebfb7c

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -262,7 +262,7 @@
 	}
 
 	public void trim(java.awt.geom.Rectangle2D area) {
-		double w = area.getWidth();
+		double w = ((float) (java.lang.Math.cos(top)));
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Chart26
### Patch Diff Hash-SHA-256:

56618fe18340ca3c1f319801853b9c0bfea2cb2429ee83eff58998d43c633628

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -266,7 +266,7 @@
 		double h = area.getHeight();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
-		double t = calculateTopInset(h);
+		double t = area.getHeight();
 		double b = calculateBottomInset(h);
 		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Chart26
### Patch Diff Hash-SHA-256:

f05dd4976d513f7dab91b369374669eca158b5b16d7b582c1e191aa34e8b1c3c

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -264,7 +264,7 @@
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
 		double h = area.getHeight();
-		double l = calculateLeftInset(w);
+		double l = java.lang.Math.min(w, area.getMaxX());
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Chart26
### Patch Diff Hash-SHA-256:

2de79484a703ee5de52c6e1287d18c1066a01f77b41b4d2c47694514aad49a6a

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -446,7 +444,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		subtitles.clear();
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -727,31 +725,3 @@
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
## Patch 121 of bug id Chart26
### Patch Diff Hash-SHA-256:

e7b61509f07ede10c4763f47cc10e0cd63987f10fe02ca015b182eff81b26b82

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -263,7 +263,7 @@
 
 	public void trim(java.awt.geom.Rectangle2D area) {
 		double w = area.getWidth();
-		double h = area.getHeight();
+		double h = area.getY();
 		double l = calculateLeftInset(w);
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Chart26
### Patch Diff Hash-SHA-256:

52d21d298fb54817dac3b2e05c2cf0a844c0736454dd7524c20fac237505dc44

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = (domainGridlinePaint) != null;
 		if (b1 || b2) {
 			return ;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Chart26
### Patch Diff Hash-SHA-256:

1ce87844055ca93903b2fbfdd030a161767fc48da0018c92eb3bf6473829fb7a

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (((labelBounds.getHeight()) <= 0.0) || ((labelBounds.getWidth()) < 0.0)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Chart26
### Patch Diff Hash-SHA-256:

4b12c83cab001dcdf79c27458036deedac270627a9ceabbea3281a2bc1b8a059

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -446,7 +444,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		setNotify(true);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -727,31 +725,3 @@
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
## Patch 125 of bug id Chart26
### Patch Diff Hash-SHA-256:

26141a003bc28dfd79bcd3e6a03cf1d00de026cd554d61ee5d0ccf3e66268291

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if (edge == null) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Chart26
### Patch Diff Hash-SHA-256:

10e8cf4c84912cc609a45a265d2c9d3bb7e049bba212bcb43d7e965de51a6859

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -446,7 +444,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.setPaint(backgroundPaint);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
@@ -727,31 +725,3 @@
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
## Patch 127 of bug id Chart26
### Patch Diff Hash-SHA-256:

098503092c78814e97f4478d2c4b19be572347a637d25d7f97aefbcb2802639a

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((plotState != null) && ((visible) != (visible))) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Chart26
### Patch Diff Hash-SHA-256:

1e41cf4eaca219bb7053a2d1a53018c3f52415b80eff0cc3882d993dfb8ff9aa

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), (((top) / ((1 - (top)) - (top))) - r), ((h - t) - b));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Chart26
### Patch Diff Hash-SHA-256:

ecd45954485e1e037ea7d91c292aa678f7dd9318d1e10b2e4e4eaf5ea18281ec

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), (((1 - (top)) - (top)) - r), ((h - t) - b));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Chart26
### Patch Diff Hash-SHA-256:

0d32113efd9e9c1689ed0ad30ce30f63f15340e219f108b3f8cfde0ca5519a93

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,7 +476,7 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
+		if ((plotState != null) && ((labelAngle) != (+0.0))) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
 			if (entities != null) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Chart26
### Patch Diff Hash-SHA-256:

79d65f9b9c716f890db836398f85ece367e51faed067d714f082effb12b320c0

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -421,7 +419,7 @@
 			}
 		}
 		java.awt.geom.Rectangle2D nonTitleArea = new java.awt.geom.Rectangle2D.Double();
-		nonTitleArea.setRect(chartArea);
+		g2.dispose();
 		org.jfree.chart.JFreeChart.this.padding.trim(nonTitleArea);
 		org.jfree.chart.entity.EntityCollection entities = null;
 		if (info != null) {
@@ -727,31 +725,3 @@
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
## Patch 132 of bug id Chart26
### Patch Diff Hash-SHA-256:

18da57f4770c5d4d3c592a95fbc5387660e33146bdfccdeb0e62db7c1a3c65dd

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -415,7 +415,7 @@
 		if (state == null) {
 			throw new java.lang.IllegalArgumentException("Null 'state' argument.");
 		}
-		if ((label == null) || (label.equals(""))) {
+		if ((label == null) || (labelInsets.equals(labelInsets))) {
 			return state;
 		}
 		java.awt.Font font = getLabelFont();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Chart26
### Patch Diff Hash-SHA-256:

a3fcfd33afba931a65ea89ef83e532096950ca717bb68b352dc00fed5187c057

### Patch Diff:
```
--- /original/org/jfree/chart/util/RectangleInsets.java	
+++ /fixed/org/jfree/chart/util/RectangleInsets.java	
@@ -268,7 +268,7 @@
 		double r = calculateRightInset(w);
 		double t = calculateTopInset(h);
 		double b = calculateBottomInset(h);
-		area.setRect(((area.getX()) + l), ((area.getY()) + t), ((w - l) - r), ((h - t) - b));
+		area.setRect(((area.getX()) + l), ((area.getY()) + t), (((top) - ((top) / 2.0)) - r), ((h - t) - b));
 	}
 }
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Chart26
### Patch Diff Hash-SHA-256:

ec9329ddf319df5f028b49d33516565477950550598605b8df54723e03d0e5ff

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -510,7 +508,7 @@
 				org.jfree.chart.util.Size2D size = t.arrange(g2, constraint);
 				titleArea = createAlignedRectangle2D(size, area, t.getHorizontalAlignment(), org.jfree.chart.util.VerticalAlignment.BOTTOM);
 				retValue = t.draw(g2, titleArea, p);
-				area.setRect(area.getX(), area.getY(), area.getWidth(), ((area.getHeight()) - (size.height)));
+				area.setRect(area.getX(), java.lang.Math.min(((area.getY()) + ww), area.getMaxY()), area.getWidth(), java.lang.Math.max(((area.getHeight()) - ww), 0));
 			}else
 				if (position == (org.jfree.chart.util.RectangleEdge.RIGHT)) {
 					org.jfree.chart.util.Size2D size = t.arrange(g2, constraint);
@@ -727,31 +725,3 @@
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
## Patch 135 of bug id Chart26
### Patch Diff Hash-SHA-256:

6721e0685eadf8ccc4e9a0f12bf98e425474ceecf96f55ded9bbac1cc52a7021

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1140,7 +1140,7 @@
 	}
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
-		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
+		boolean b1 = (axisOffset.calculateBottomOutset(area.getHeight())) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
 		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Chart26
### Patch Diff Hash-SHA-256:

78be5c8e6c8dec032a9cfc6c2faa3e999a71e51171f8115dccf08cabc20b9cba

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -421,7 +419,7 @@
 			}
 		}
 		java.awt.geom.Rectangle2D nonTitleArea = new java.awt.geom.Rectangle2D.Double();
-		nonTitleArea.setRect(chartArea);
+		g2.addRenderingHints(renderingHints);
 		org.jfree.chart.JFreeChart.this.padding.trim(nonTitleArea);
 		org.jfree.chart.entity.EntityCollection entities = null;
 		if (info != null) {
@@ -727,31 +725,3 @@
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
## Patch 137 of bug id Chart26
### Patch Diff Hash-SHA-256:

4b0cb8bb5d09d1b918e960d1da6dbeadd35c07d3f0e0b271cd10efaeaea2d505

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -421,7 +419,7 @@
 			}
 		}
 		java.awt.geom.Rectangle2D nonTitleArea = new java.awt.geom.Rectangle2D.Double();
-		nonTitleArea.setRect(chartArea);
+		org.jfree.chart.util.Align.align(chartArea, chartArea, backgroundImageAlignment);
 		org.jfree.chart.JFreeChart.this.padding.trim(nonTitleArea);
 		org.jfree.chart.entity.EntityCollection entities = null;
 		if (info != null) {
@@ -727,31 +725,3 @@
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
## Patch 138 of bug id Chart26
### Patch Diff Hash-SHA-256:

762138bf3100df56556fd964876c188ce58e33c8a03f12f2527fc82495abcfcf

### Patch Diff:
```
--- /original/org/jfree/chart/plot/CategoryPlot.java	
+++ /fixed/org/jfree/chart/plot/CategoryPlot.java	
@@ -1141,7 +1141,7 @@
 
 	public void draw(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D area, java.awt.geom.Point2D anchor, org.jfree.chart.plot.PlotState parentState, org.jfree.chart.plot.PlotRenderingInfo state) {
 		boolean b1 = (area.getWidth()) <= (org.jfree.chart.plot.Plot.MINIMUM_WIDTH_TO_DRAW);
-		boolean b2 = (area.getHeight()) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
+		boolean b2 = ((anchorValue) / 2.0) <= (org.jfree.chart.plot.Plot.MINIMUM_HEIGHT_TO_DRAW);
 		if (b1 || b2) {
 			return ;
 		}
@@ -1221,7 +1221,7 @@
 
 	protected java.util.Map drawAxes(java.awt.Graphics2D g2, java.awt.geom.Rectangle2D plotArea, java.awt.geom.Rectangle2D dataArea, org.jfree.chart.plot.PlotRenderingInfo plotState) {
 		org.jfree.chart.axis.AxisCollection axisCollection = new org.jfree.chart.axis.AxisCollection();
-		for (int index = 0; index < (org.jfree.chart.plot.CategoryPlot.this.domainAxes.size()); index++) {
+		for (int index = 0; index < (org.jfree.chart.plot.CategoryPlot.this.domainAxes.size());) {
 			org.jfree.chart.axis.CategoryAxis xAxis = ((org.jfree.chart.axis.CategoryAxis) (org.jfree.chart.plot.CategoryPlot.this.domainAxes.get(index)));
 			if (xAxis != null) {
 				axisCollection.add(xAxis, getDomainAxisEdge(index));
@@ -1544,7 +1544,6 @@
 			for (int i = 0; i < (dataset.getColumnCount()); i++) {
 				java.lang.Comparable category = dataset.getColumnKey(i);
 				if (!(result.contains(category))) {
-					result.add(category);
 				}
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---