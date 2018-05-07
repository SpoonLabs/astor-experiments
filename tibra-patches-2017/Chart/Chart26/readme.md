
# Patches of Chart26 from Defects4J 
Total patches 10
## Patch 1 of bug id Chart26
### Patch Diff Hash-SHA-256:

179d96b28b05d8e46d05be0ea31c0e2701e80516354ead7aea7f3c2096e624e0

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -423,57 +423,6 @@
 		java.awt.FontMetrics fm = g2.getFontMetrics();
 		java.awt.geom.Rectangle2D labelBounds = org.jfree.chart.text.TextUtilities.getTextBounds(label, g2, fm);
 		java.awt.Shape hotspot = null;
-		if (edge == (org.jfree.chart.util.RectangleEdge.TOP)) {
-			java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(getLabelAngle(), labelBounds.getCenterX(), labelBounds.getCenterY());
-			java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-			labelBounds = rotatedLabelBounds.getBounds2D();
-			float w = ((float) (labelBounds.getWidth()));
-			float h = ((float) (labelBounds.getHeight()));
-			float labelx = ((float) (dataArea.getCenterX()));
-			float labely = ((float) (((state.getCursor()) - (insets.getBottom())) - (h / 2.0)));
-			org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, getLabelAngle(), org.jfree.chart.text.TextAnchor.CENTER);
-			hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-			state.cursorUp((((insets.getTop()) + (labelBounds.getHeight())) + (insets.getBottom())));
-		}else
-			if (edge == (org.jfree.chart.util.RectangleEdge.BOTTOM)) {
-				java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(getLabelAngle(), labelBounds.getCenterX(), labelBounds.getCenterY());
-				java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-				labelBounds = rotatedLabelBounds.getBounds2D();
-				float w = ((float) (labelBounds.getWidth()));
-				float h = ((float) (labelBounds.getHeight()));
-				float labelx = ((float) (dataArea.getCenterX()));
-				float labely = ((float) (((state.getCursor()) + (insets.getTop())) + (h / 2.0)));
-				org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, getLabelAngle(), org.jfree.chart.text.TextAnchor.CENTER);
-				hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-				state.cursorDown((((insets.getTop()) + (labelBounds.getHeight())) + (insets.getBottom())));
-			}else
-				if (edge == (org.jfree.chart.util.RectangleEdge.LEFT)) {
-					java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(((getLabelAngle()) - ((java.lang.Math.PI) / 2.0)), labelBounds.getCenterX(), labelBounds.getCenterY());
-					java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-					labelBounds = rotatedLabelBounds.getBounds2D();
-					float w = ((float) (labelBounds.getWidth()));
-					float h = ((float) (labelBounds.getHeight()));
-					float labelx = ((float) (((state.getCursor()) - (insets.getRight())) - (w / 2.0)));
-					float labely = ((float) (dataArea.getCenterY()));
-					org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, ((getLabelAngle()) - ((java.lang.Math.PI) / 2.0)), org.jfree.chart.text.TextAnchor.CENTER);
-					hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-					state.cursorLeft((((insets.getLeft()) + (labelBounds.getWidth())) + (insets.getRight())));
-				}else
-					if (edge == (org.jfree.chart.util.RectangleEdge.RIGHT)) {
-						java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(((getLabelAngle()) + ((java.lang.Math.PI) / 2.0)), labelBounds.getCenterX(), labelBounds.getCenterY());
-						java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-						labelBounds = rotatedLabelBounds.getBounds2D();
-						float w = ((float) (labelBounds.getWidth()));
-						float h = ((float) (labelBounds.getHeight()));
-						float labelx = ((float) (((state.getCursor()) + (insets.getLeft())) + (w / 2.0)));
-						float labely = ((float) ((dataArea.getY()) + ((dataArea.getHeight()) / 2.0)));
-						org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, ((getLabelAngle()) + ((java.lang.Math.PI) / 2.0)), org.jfree.chart.text.TextAnchor.CENTER);
-						hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-						state.cursorRight((((insets.getLeft()) + (labelBounds.getWidth())) + (insets.getRight())));
-					}
-
-
-
 		if ((plotState != null) && (hotspot != null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
```


---
## Patch 2 of bug id Chart26
### Patch Diff Hash-SHA-256:

e4cd0653f0159a620191917d993233b961e7ec56ef4f1ec3fcb76b694b773a71

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -417,7 +417,7 @@
 			}
 		}
 		java.awt.geom.Rectangle2D nonTitleArea = new java.awt.geom.Rectangle2D.Double();
-		nonTitleArea.setRect(chartArea);
+		renderingHints.clear();
 		this.padding.trim(nonTitleArea);
 		org.jfree.chart.entity.EntityCollection entities = null;
 		if (info != null) {
```


---
## Patch 3 of bug id Chart26
### Patch Diff Hash-SHA-256:

1d6095d99bc5bcf6133da42a290ad7e0fd213272fef7da1a73fc68777be8b28f

### Patch Diff:
```
--- /original/org/jfree/chart/axis/AxisCollection.java	
+++ /fixed/org/jfree/chart/axis/AxisCollection.java	
@@ -40,21 +40,6 @@
 		if (edge == null) {
 			throw new java.lang.IllegalArgumentException("Null 'edge' argument.");
 		}
-		if (edge == (org.jfree.chart.util.RectangleEdge.TOP)) {
-			this.axesAtTop.add(axis);
-		}else
-			if (edge == (org.jfree.chart.util.RectangleEdge.BOTTOM)) {
-				this.axesAtBottom.add(axis);
-			}else
-				if (edge == (org.jfree.chart.util.RectangleEdge.LEFT)) {
-					this.axesAtLeft.add(axis);
-				}else
-					if (edge == (org.jfree.chart.util.RectangleEdge.RIGHT)) {
-						this.axesAtRight.add(axis);
-					}
-
-
-
 	}
 }
```


---
## Patch 4 of bug id Chart26
### Patch Diff Hash-SHA-256:

8e2e7859776ecc4998cc1e6994a975d2c8caf5cce9ad131bb88c47cca02ad216

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -474,13 +474,17 @@
 
 
 
-		if ((plotState != null) && (hotspot != null)) {
-			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
-			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
-			if (entities != null) {
-				entities.add(new org.jfree.chart.entity.AxisLabelEntity(this, hotspot, this.labelToolTip, this.labelURL));
-			}
+		if (edge == (org.jfree.chart.util.RectangleEdge.BOTTOM)) {
+			labelAngle = state.getMax();
+		}else
+			if (edge == (org.jfree.chart.util.RectangleEdge.LEFT)) {
+				fixedDimension = state.getMax();
+			}else
+				if (edge == (org.jfree.chart.util.RectangleEdge.RIGHT)) {
+					fixedDimension = state.getMax();
 		}
+
+
 		return state;
 	}
```


---
## Patch 5 of bug id Chart26
### Patch Diff Hash-SHA-256:

a1e98bfc365ac2126380d5854dc25cd67e8853d1b9798b3ca53cc21e49c49608

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -474,13 +474,6 @@
 
 
 
-		if ((plotState != null) && (hotspot != null)) {
-			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
-			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
-			if (entities != null) {
-				entities.add(new org.jfree.chart.entity.AxisLabelEntity(this, hotspot, this.labelToolTip, this.labelURL));
-			}
-		}
 		return state;
 	}
```


---
## Patch 6 of bug id Chart26
### Patch Diff Hash-SHA-256:

2179634e310db2e6c082427723d25b7823b9f0559ce8caacf40f64036467d29c

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -474,12 +474,9 @@
 
 
 
-		if ((plotState != null) && (hotspot != null)) {
-			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
-			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
-			if (entities != null) {
-				entities.add(new org.jfree.chart.entity.AxisLabelEntity(this, hotspot, this.labelToolTip, this.labelURL));
-			}
+		if (!(insets.equals(this.labelInsets))) {
+			this.labelInsets = insets;
+			notifyListeners(new org.jfree.chart.event.AxisChangeEvent(this));
 		}
 		return state;
 	}
```


---
## Patch 7 of bug id Chart26
### Patch Diff Hash-SHA-256:

c9d98de043e61594cb25d5cc4dff7d2f5bf20baca390b31f6914fb7be184f151

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -442,7 +442,6 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		this.plot.draw(g2, plotArea, anchor, null, plotInfo);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(this, this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
```


---
## Patch 8 of bug id Chart26
### Patch Diff Hash-SHA-256:

9a8d486b2af859d63a3c4e8270a6d0c2ed8076ae400167ee6c60167187ef30c2

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -442,7 +442,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		removeSubtitle(getLegend());
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(this, this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
 	}
```


---
## Patch 9 of bug id Chart26
### Patch Diff Hash-SHA-256:

fff8ba133eba0ae3639e0e1cd557e03a5c1150e3211adfd893c8f4b25e28709c

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -417,7 +417,6 @@
 			}
 		}
 		java.awt.geom.Rectangle2D nonTitleArea = new java.awt.geom.Rectangle2D.Double();
-		nonTitleArea.setRect(chartArea);
 		this.padding.trim(nonTitleArea);
 		org.jfree.chart.entity.EntityCollection entities = null;
 		if (info != null) {
```


---
## Patch 10 of bug id Chart26
### Patch Diff Hash-SHA-256:

f122b3c991465acb256a58b6f1c7500614e0e71cea6b9ee3cb4df3c2b4f277af

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -423,57 +423,9 @@
 		java.awt.FontMetrics fm = g2.getFontMetrics();
 		java.awt.geom.Rectangle2D labelBounds = org.jfree.chart.text.TextUtilities.getTextBounds(label, g2, fm);
 		java.awt.Shape hotspot = null;
-		if (edge == (org.jfree.chart.util.RectangleEdge.TOP)) {
-			java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(getLabelAngle(), labelBounds.getCenterX(), labelBounds.getCenterY());
-			java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-			labelBounds = rotatedLabelBounds.getBounds2D();
-			float w = ((float) (labelBounds.getWidth()));
-			float h = ((float) (labelBounds.getHeight()));
-			float labelx = ((float) (dataArea.getCenterX()));
-			float labely = ((float) (((state.getCursor()) - (insets.getBottom())) - (h / 2.0)));
-			org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, getLabelAngle(), org.jfree.chart.text.TextAnchor.CENTER);
-			hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-			state.cursorUp((((insets.getTop()) + (labelBounds.getHeight())) + (insets.getBottom())));
-		}else
-			if (edge == (org.jfree.chart.util.RectangleEdge.BOTTOM)) {
-				java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(getLabelAngle(), labelBounds.getCenterX(), labelBounds.getCenterY());
-				java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-				labelBounds = rotatedLabelBounds.getBounds2D();
-				float w = ((float) (labelBounds.getWidth()));
-				float h = ((float) (labelBounds.getHeight()));
-				float labelx = ((float) (dataArea.getCenterX()));
-				float labely = ((float) (((state.getCursor()) + (insets.getTop())) + (h / 2.0)));
-				org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, getLabelAngle(), org.jfree.chart.text.TextAnchor.CENTER);
-				hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-				state.cursorDown((((insets.getTop()) + (labelBounds.getHeight())) + (insets.getBottom())));
-			}else
-				if (edge == (org.jfree.chart.util.RectangleEdge.LEFT)) {
-					java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(((getLabelAngle()) - ((java.lang.Math.PI) / 2.0)), labelBounds.getCenterX(), labelBounds.getCenterY());
-					java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-					labelBounds = rotatedLabelBounds.getBounds2D();
-					float w = ((float) (labelBounds.getWidth()));
-					float h = ((float) (labelBounds.getHeight()));
-					float labelx = ((float) (((state.getCursor()) - (insets.getRight())) - (w / 2.0)));
-					float labely = ((float) (dataArea.getCenterY()));
-					org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, ((getLabelAngle()) - ((java.lang.Math.PI) / 2.0)), org.jfree.chart.text.TextAnchor.CENTER);
-					hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-					state.cursorLeft((((insets.getLeft()) + (labelBounds.getWidth())) + (insets.getRight())));
-				}else
-					if (edge == (org.jfree.chart.util.RectangleEdge.RIGHT)) {
-						java.awt.geom.AffineTransform t = java.awt.geom.AffineTransform.getRotateInstance(((getLabelAngle()) + ((java.lang.Math.PI) / 2.0)), labelBounds.getCenterX(), labelBounds.getCenterY());
-						java.awt.Shape rotatedLabelBounds = t.createTransformedShape(labelBounds);
-						labelBounds = rotatedLabelBounds.getBounds2D();
-						float w = ((float) (labelBounds.getWidth()));
-						float h = ((float) (labelBounds.getHeight()));
-						float labelx = ((float) (((state.getCursor()) + (insets.getLeft())) + (w / 2.0)));
-						float labely = ((float) ((dataArea.getY()) + ((dataArea.getHeight()) / 2.0)));
-						org.jfree.chart.text.TextUtilities.drawRotatedString(label, g2, labelx, labely, org.jfree.chart.text.TextAnchor.CENTER, ((getLabelAngle()) + ((java.lang.Math.PI) / 2.0)), org.jfree.chart.text.TextAnchor.CENTER);
-						hotspot = new java.awt.geom.Rectangle2D.Float((labelx - (w / 2.0F)), (labely - (h / 2.0F)), w, h);
-						state.cursorRight((((insets.getLeft()) + (labelBounds.getWidth())) + (insets.getRight())));
+		if (labelFont == null) {
+			throw new java.lang.IllegalArgumentException("Null 'labelFont' argument.");
 					}
-
-
-
 		if ((plotState != null) && (hotspot != null)) {
 			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
 			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
```


---