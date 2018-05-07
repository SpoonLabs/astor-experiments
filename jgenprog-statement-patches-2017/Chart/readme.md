
## Patch 1 of bug id Chart7
### Patch Diff Hash-SHA-256:

d540be86b958421e69c8bb811e5659cc4382a9976e03abd080fcf55220801c1d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -257,7 +257,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex;
+		return org.jfree.data.time.TimePeriodValues.this.maxStartIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 2 of bug id Chart7
### Patch Diff Hash-SHA-256:

7886030f1bb5dba0f59e2f9b299afeb5d27fae884de7f07b7765463e1a379b0c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -257,7 +257,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex;
+		return org.jfree.data.time.TimePeriodValues.this.maxEndIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
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
## Patch 1 of bug id Chart19
### Patch Diff Hash-SHA-256:

0347cb9bfcaf3cd2adb8faabf30c9ac6386a9a433558d5741c3f55d33c2b26b6

### Patch Diff:
```
--- /original/org/jfree/chart/util/AbstractObjectList.java	
+++ /fixed/org/jfree/chart/util/AbstractObjectList.java	
@@ -63,6 +63,9 @@
 				return index;
 			}
 		}
+		if (object == null) {
+			throw new java.lang.IllegalArgumentException("Null 'object' argument.");
+		}
 		return -1;
 	}
```


---
## Patch 1 of bug id Chart26
### Patch Diff Hash-SHA-256:

0c1380068ca70fc2bd13c42a08ebb9b75c89f49d28c31f31f933b4256badbf84

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -425,57 +425,6 @@
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

3692954a80597d09bb36c6b36a82976b63786560cf9088769e199d7a733eaff1

### Patch Diff:
```
--- /original/org/jfree/chart/axis/AxisCollection.java	
+++ /fixed/org/jfree/chart/axis/AxisCollection.java	
@@ -42,21 +42,6 @@
 		if (edge == null) {
 			throw new java.lang.IllegalArgumentException("Null 'edge' argument.");
 		}
-		if (edge == (org.jfree.chart.util.RectangleEdge.TOP)) {
-			org.jfree.chart.axis.AxisCollection.this.axesAtTop.add(axis);
-		}else
-			if (edge == (org.jfree.chart.util.RectangleEdge.BOTTOM)) {
-				org.jfree.chart.axis.AxisCollection.this.axesAtBottom.add(axis);
-			}else
-				if (edge == (org.jfree.chart.util.RectangleEdge.LEFT)) {
-					org.jfree.chart.axis.AxisCollection.this.axesAtLeft.add(axis);
-				}else
-					if (edge == (org.jfree.chart.util.RectangleEdge.RIGHT)) {
-						org.jfree.chart.axis.AxisCollection.this.axesAtRight.add(axis);
-					}
-				
-			
-		
 	}
 }
```


---
## Patch 3 of bug id Chart26
### Patch Diff Hash-SHA-256:

1a7db941e94b98628282893b0340716cbc2cdf0c90f0c7152fe22565f1140270

### Patch Diff:
```
--- /original/org/jfree/chart/axis/Axis.java	
+++ /fixed/org/jfree/chart/axis/Axis.java	
@@ -476,13 +476,6 @@
 				
 			
 		
-		if ((plotState != null) && (hotspot != null)) {
-			org.jfree.chart.ChartRenderingInfo owner = plotState.getOwner();
-			org.jfree.chart.entity.EntityCollection entities = owner.getEntityCollection();
-			if (entities != null) {
-				entities.add(new org.jfree.chart.entity.AxisLabelEntity(org.jfree.chart.axis.Axis.this, hotspot, org.jfree.chart.axis.Axis.this.labelToolTip, org.jfree.chart.axis.Axis.this.labelURL));
-			}
-		}
 		return state;
 	}
```


---
## Patch 4 of bug id Chart26
### Patch Diff Hash-SHA-256:

6ea522ea8f91fc838b64d5a2265b7b621185b358a83d33cc84251f3bcb95897d

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
+		setNotify(false);
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


---
## Patch 5 of bug id Chart26
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


---
## Patch 6 of bug id Chart26
### Patch Diff Hash-SHA-256:

d32ea633537339b506f6cf91bbc36678ae123d3570458c287bdc1fec6764abeb

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -421,7 +419,6 @@
 			}
 		}
 		java.awt.geom.Rectangle2D nonTitleArea = new java.awt.geom.Rectangle2D.Double();
-		nonTitleArea.setRect(chartArea);
 		org.jfree.chart.JFreeChart.this.padding.trim(nonTitleArea);
 		org.jfree.chart.entity.EntityCollection entities = null;
 		if (info != null) {
@@ -727,31 +724,3 @@
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
## Patch 1 of bug id Chart15
### Patch Diff Hash-SHA-256:

c81af134472b6e752af143a442acf15c62bf3dfa6550a33975dbb848cbb6401b

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,6 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
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
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
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
## Patch 2 of bug id Chart15
### Patch Diff Hash-SHA-256:

7382c22eea3c92b124d046d96118c514a33739ca195c6abc7237b0605aa69860

### Patch Diff:
```
--- /original/org/jfree/chart/plot/PiePlot3D.java	
+++ /fixed/org/jfree/chart/plot/PiePlot3D.java	
@@ -69,12 +69,11 @@
 		double linkY = (plotArea.getY()) + (gapVertical / 2);
 		double linkW = (plotArea.getWidth()) - gapHorizontal;
 		double linkH = (plotArea.getHeight()) - gapVertical;
-		if (isCircular()) {
-			double min = (java.lang.Math.min(linkW, linkH)) / 2;
-			linkX = (((linkX + linkX) + linkW) / 2) - min;
-			linkY = (((linkY + linkY) + linkH) / 2) - min;
-			linkW = 2 * min;
-			linkH = 2 * min;
+		if (org.jfree.data.general.DatasetUtilities.isEmptyOrNull(getDataset())) {
+			drawNoDataMessage(g2, plotArea);
+			g2.setClip(savedClip);
+			drawOutline(g2, plotArea);
+			return ;
 		}
 		org.jfree.chart.plot.PiePlotState state = initialise(g2, plotArea, org.jfree.chart.plot.PiePlot3D.this, null, info);
 		java.awt.geom.Rectangle2D linkAreaXX = new java.awt.geom.Rectangle2D.Double(linkX, linkY, linkW, (linkH * (1 - (org.jfree.chart.plot.PiePlot3D.this.depthFactor))));
```


---
## Patch 3 of bug id Chart15
### Patch Diff Hash-SHA-256:

87bd6b057bd8bbcaa62b195c1e0c01eb6310975b6fb6e674e8d96e4242198586

### Patch Diff:
```
--- /original/org/jfree/chart/plot/PiePlot3D.java	
+++ /fixed/org/jfree/chart/plot/PiePlot3D.java	
@@ -50,8 +50,11 @@
 		g2.clip(plotArea);
 		double gapPercent = getInteriorGap();
 		double labelPercent = 0.0;
-		if ((getLabelGenerator()) != null) {
-			labelPercent = (getLabelGap()) + (getMaximumLabelWidth());
+		if (org.jfree.data.general.DatasetUtilities.isEmptyOrNull(getDataset())) {
+			drawNoDataMessage(g2, plotArea);
+			g2.setClip(savedClip);
+			drawOutline(g2, plotArea);
+			return ;
 		}
 		double gapHorizontal = ((plotArea.getWidth()) * (gapPercent + labelPercent)) * 2.0;
 		double gapVertical = ((plotArea.getHeight()) * gapPercent) * 2.0;
```


---
## Patch 4 of bug id Chart15
### Patch Diff Hash-SHA-256:

5e8d16f2644c2df73dc24d544b42086f0f2e74fb4649e456ae247d9d2f2cfd11

### Patch Diff:
```
--- /original/org/jfree/chart/JFreeChart.java	
+++ /fixed/org/jfree/chart/JFreeChart.java	
@@ -1,7 +1,5 @@
 
 
-
-
 package org.jfree.chart;
 
 
@@ -452,7 +450,7 @@
 		if (info != null) {
 			plotInfo = info.getPlotInfo();
 		}
-		org.jfree.chart.JFreeChart.this.plot.draw(g2, plotArea, anchor, null, plotInfo);
+		g2.setPaintMode();
 		g2.setClip(savedClip);
 		notifyListeners(new org.jfree.chart.event.ChartProgressEvent(org.jfree.chart.JFreeChart.this, org.jfree.chart.JFreeChart.this, org.jfree.chart.event.ChartProgressEvent.DRAWING_FINISHED, 100));
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
-		setContributors(java.util.Arrays.asList(new org.jfree.chart.ui.Contributor[]{ new org.jfree.chart.ui.Contributor("Eric Alexander", "-") , new org.jfree.chart.ui.Contributor("Richard Atkinson", "richard_c_atkinson@ntlworld.com") , new org.jfree.chart.ui.Contributor("David Basten", "-") , new org.jfree.chart.ui.Contributor("David Berry", "-") , new org.jfree.chart.ui.Contributor("Chris Boek", "-") , new org.jfree.chart.ui.Contributor("Zoheb Borbora", "-") , new org.jfree.chart.ui.Contributor("Anthony Boulestreau", "-") , new org.jfree.chart.ui.Contributor("Jeremy Bowman", "-") , new org.jfree.chart.ui.Contributor("Nicolas Brodu", "-") , new org.jfree.chart.ui.Contributor("Jody Brownell", "-") , new org.jfree.chart.ui.Contributor("David Browning", "-") , new org.jfree.chart.ui.Contributor("Soren Caspersen", "-") , new org.jfree.chart.ui.Contributor("Chuanhao Chiu", "-") , new org.jfree.chart.ui.Contributor("Brian Cole", "-") , new org.jfree.chart.ui.Contributor("Pascal Collet", "-") , new org.jfree.chart.ui.Contributor("Martin Cordova", "-") , new org.jfree.chart.ui.Contributor("Paolo Cova", "-") , new org.jfree.chart.ui.Contributor("Mike Duffy", "-") , new org.jfree.chart.ui.Contributor("Don Elliott", "-") , new org.jfree.chart.ui.Contributor("David Forslund", "-") , new org.jfree.chart.ui.Contributor("Jonathan Gabbai", "-") , new org.jfree.chart.ui.Contributor("David Gilbert", "david.gilbert@object-refinery.com") , new org.jfree.chart.ui.Contributor("Serge V. Grachov", "-") , new org.jfree.chart.ui.Contributor("Daniel Gredler", "-") , new org.jfree.chart.ui.Contributor("Hans-Jurgen Greiner", "-") , new org.jfree.chart.ui.Contributor("Joao Guilherme Del Valle", "-") , new org.jfree.chart.ui.Contributor("Aiman Han", "-") , new org.jfree.chart.ui.Contributor("Cameron Hayne", "-") , new org.jfree.chart.ui.Contributor("Jon Iles", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Irler", "-") , new org.jfree.chart.ui.Contributor("Sergei Ivanov", "-") , new org.jfree.chart.ui.Contributor("Adriaan Joubert", "-") , new org.jfree.chart.ui.Contributor("Darren Jung", "-") , new org.jfree.chart.ui.Contributor("Xun Kang", "-") , new org.jfree.chart.ui.Contributor("Bill Kelemen", "-") , new org.jfree.chart.ui.Contributor("Norbert Kiesel", "-") , new org.jfree.chart.ui.Contributor("Gideon Krause", "-") , new org.jfree.chart.ui.Contributor("Pierre-Marie Le Biot", "-") , new org.jfree.chart.ui.Contributor("Arnaud Lelievre", "-") , new org.jfree.chart.ui.Contributor("Wolfgang Lenhard", "-") , new org.jfree.chart.ui.Contributor("David Li", "-") , new org.jfree.chart.ui.Contributor("Yan Liu", "-") , new org.jfree.chart.ui.Contributor("Tin Luu", "-") , new org.jfree.chart.ui.Contributor("Craig MacFarlane", "-") , new org.jfree.chart.ui.Contributor("Achilleus Mantzios", "-") , new org.jfree.chart.ui.Contributor("Thomas Meier", "-") , new org.jfree.chart.ui.Contributor("Jim Moore", "-") , new org.jfree.chart.ui.Contributor("Jonathan Nash", "-") , new org.jfree.chart.ui.Contributor("Barak Naveh", "-") , new org.jfree.chart.ui.Contributor("David M. O'Donnell", "-") , new org.jfree.chart.ui.Contributor("Krzysztof Paz", "-") , new org.jfree.chart.ui.Contributor("Tomer Peretz", "-") , new org.jfree.chart.ui.Contributor("Xavier Poinsard", "-") , new org.jfree.chart.ui.Contributor("Andrzej Porebski", "-") , new org.jfree.chart.ui.Contributor("Viktor Rajewski", "-") , new org.jfree.chart.ui.Contributor("Eduardo Ramalho", "-") , new org.jfree.chart.ui.Contributor("Michael Rauch", "-") , new org.jfree.chart.ui.Contributor("Cameron Riley", "-") , new org.jfree.chart.ui.Contributor("Klaus Rheinwald", "-") , new org.jfree.chart.ui.Contributor("Dan Rivett", "d.rivett@ukonline.co.uk") , new org.jfree.chart.ui.Contributor("Scott Sams", "-") , new org.jfree.chart.ui.Contributor("Michel Santos", "-") , new org.jfree.chart.ui.Contributor("Thierry Saura", "-") , new org.jfree.chart.ui.Contributor("Andreas Schneider", "-") , new org.jfree.chart.ui.Contributor("Jean-Luc SCHWAB", "-") , new org.jfree.chart.ui.Contributor("Bryan Scott", "-") , new org.jfree.chart.ui.Contributor("Tobias Selb", "-") , new org.jfree.chart.ui.Contributor("Mofeed Shahin", "-") , new org.jfree.chart.ui.Contributor("Pady Srinivasan", "-") , new org.jfree.chart.ui.Contributor("Greg Steckman", "-") , new org.jfree.chart.ui.Contributor("Roger Studner", "-") , new org.jfree.chart.ui.Contributor("Irv Thomae", "-") , new org.jfree.chart.ui.Contributor("Eric Thomas", "-") , new org.jfree.chart.ui.Contributor("Rich Unger", "-") , new org.jfree.chart.ui.Contributor("Daniel van Enckevort", "-") , new org.jfree.chart.ui.Contributor("Laurence Vanhelsuwe", "-") , new org.jfree.chart.ui.Contributor("Sylvain Vieujot", "-") , new org.jfree.chart.ui.Contributor("Jelai Wang", "-") , new org.jfree.chart.ui.Contributor("Mark Watson", "www.markwatson.com") , new org.jfree.chart.ui.Contributor("Alex Weber", "-") , new org.jfree.chart.ui.Contributor("Matthew Wright", "-") , new org.jfree.chart.ui.Contributor("Benoit Xhenseval", "-") , new org.jfree.chart.ui.Contributor("Christian W. Zuckschwerdt", "Christian.Zuckschwerdt@Informatik.Uni-Oldenburg.de") , new org.jfree.chart.ui.Contributor("Hari", "-") , new org.jfree.chart.ui.Contributor("Sam (oldman)", "-") }));
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
## Patch 1 of bug id Chart3
### Patch Diff Hash-SHA-256:

836688492bf66f9caa0199e30c9e076d1a037d68466d3570f1f3e83dc5f15e09

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -196,6 +196,7 @@
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
+		findBoundsByIteration();
 		if ((org.jfree.data.time.TimeSeries.this.timePeriodClass) == null) {
 			org.jfree.data.time.TimeSeries.this.timePeriodClass = c;
 		}else
```


---
## Patch 2 of bug id Chart3
### Patch Diff Hash-SHA-256:

295e07501b1d2f33ce7029a91b150b70a309d9cab4b3b3c168b13ab130b49053

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -194,6 +194,7 @@
 		if (item == null) {
 			throw new java.lang.IllegalArgumentException("Null 'item' argument.");
 		}
+		findBoundsByIteration();
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
 		if ((org.jfree.data.time.TimeSeries.this.timePeriodClass) == null) {
```


---
## Patch 3 of bug id Chart3
### Patch Diff Hash-SHA-256:

277a515c59d99ba6a31a7903a61a8c561231e68e908025f08514fe8881a4f9b9

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -238,7 +238,7 @@
 			}
 		}
 		if (added) {
-			updateBoundsForAddedItem(item);
+			findBoundsByIteration();
 			if ((getItemCount()) > (org.jfree.data.time.TimeSeries.this.maximumItemCount)) {
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (org.jfree.data.time.TimeSeries.this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
```


---
## Patch 4 of bug id Chart3
### Patch Diff Hash-SHA-256:

17e5021ca3aa20676cd5a367165aa5ab4794012061c581bbdb2c9d478ff0e608

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -370,6 +370,7 @@
 
 	public void removeAgedItems(boolean notify) {
 		if ((getItemCount()) > 1) {
+			findBoundsByIteration();
 			long latest = getTimePeriod(((getItemCount()) - 1)).getSerialIndex();
 			boolean removed = false;
 			while ((latest - (getTimePeriod(0).getSerialIndex())) > (org.jfree.data.time.TimeSeries.this.maximumItemAge)) {
```


---
## Patch 5 of bug id Chart3
### Patch Diff Hash-SHA-256:

84e620e973f635066e81c1b456a337e87e1001ca7ca996c463f8933917f35b41

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -188,6 +188,7 @@
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item) {
 		add(item, true);
+		findBoundsByIteration();
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item, boolean notify) {
```


---
## Patch 6 of bug id Chart3
### Patch Diff Hash-SHA-256:

6cae1123ff9b333b1516dd18db3572d48bec2af0d7451ce2a99e3778294a9a34

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -188,6 +188,7 @@
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item) {
 		add(item, true);
+		updateBoundsForRemovedItem(item);
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item, boolean notify) {
```


---
## Patch 7 of bug id Chart3
### Patch Diff Hash-SHA-256:

d94600a8fba1c029574d8947a3732857c83f6fa4353e2507efdf58ccdfae7a6e

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -245,7 +245,7 @@
 			}
 			removeAgedItems(false);
 			if (notify) {
-				fireSeriesChanged();
+				updateBoundsForRemovedItem(item);
 			}
 		}
 	}
```


---
## Patch 8 of bug id Chart3
### Patch Diff Hash-SHA-256:

ec8cd1f9af8ebe36a8509983a9158b5c9a547caaf4c1aaaa8520ec824fa2b938

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -245,7 +245,7 @@
 			}
 			removeAgedItems(false);
 			if (notify) {
-				fireSeriesChanged();
+				findBoundsByIteration();
 			}
 		}
 	}
```


---
## Patch 9 of bug id Chart3
### Patch Diff Hash-SHA-256:

3af41a93b9fe7f6d81353a7f75e72a7b15ed9effe87622756a3c09cb79a5c790

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -239,6 +239,7 @@
 		}
 		if (added) {
 			updateBoundsForAddedItem(item);
+			findBoundsByIteration();
 			if ((getItemCount()) > (org.jfree.data.time.TimeSeries.this.maximumItemCount)) {
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (org.jfree.data.time.TimeSeries.this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
```


---
## Patch 10 of bug id Chart3
### Patch Diff Hash-SHA-256:

62d0996007ce43ab8f024735aef5f31501a4f7f30c68d11f17666a079c9f80c3

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -219,6 +219,7 @@
 			org.jfree.data.time.RegularTimePeriod last = getTimePeriod(((getItemCount()) - 1));
 			if ((item.getPeriod().compareTo(last)) > 0) {
 				org.jfree.data.time.TimeSeries.this.data.add(item);
+				findBoundsByIteration();
 				added = true;
 			}else {
 				int index = java.util.Collections.binarySearch(org.jfree.data.time.TimeSeries.this.data, item);
```


---
## Patch 11 of bug id Chart3
### Patch Diff Hash-SHA-256:

4eee630b5726a6172f69bd35e2efe1f4e6c6229a361ab566641fd1873cce694a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -247,6 +247,7 @@
 			if (notify) {
 				fireSeriesChanged();
 			}
+			updateBoundsForRemovedItem(item);
 		}
 	}
```


---
## Patch 12 of bug id Chart3
### Patch Diff Hash-SHA-256:

a7f01f4172494551a20e41f62e2dd9dff75a295c4da6f654791fe948469d48d5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -211,6 +211,7 @@
 			}
 		
 		boolean added = false;
+		updateBoundsForRemovedItem(item);
 		int count = getItemCount();
 		if (count == 0) {
 			org.jfree.data.time.TimeSeries.this.data.add(item);
```


---
## Patch 13 of bug id Chart3
### Patch Diff Hash-SHA-256:

43963f639e14be43d3383b95e219a7ed59a27946233c46e8a5b79c4c5d4f9e9c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -214,6 +214,7 @@
 		int count = getItemCount();
 		if (count == 0) {
 			org.jfree.data.time.TimeSeries.this.data.add(item);
+			findBoundsByIteration();
 			added = true;
 		}else {
 			org.jfree.data.time.RegularTimePeriod last = getTimePeriod(((getItemCount()) - 1));
```


---
## Patch 14 of bug id Chart3
### Patch Diff Hash-SHA-256:

6a9e12667eae65a8e1b95b8ceb1b06047deac35c6097eea0d6ee7e7d1a28f5e7

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,6 +243,7 @@
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (org.jfree.data.time.TimeSeries.this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
 			}
+			org.jfree.data.time.TimeSeriesDataItem oldItem = addOrUpdate(item.getPeriod(), item.getValue());
 			removeAgedItems(false);
 			if (notify) {
 				fireSeriesChanged();
```


---
## Patch 1 of bug id Chart12
### Patch Diff Hash-SHA-256:

c9d085fb22d1668a8e3d902bcab4bb056c6488c6aa32a311bc7c248d1420c3f9

### Patch Diff:
```
--- /original/org/jfree/data/general/AbstractDataset.java	
+++ /fixed/org/jfree/data/general/AbstractDataset.java	
@@ -36,7 +36,7 @@
 
 	public boolean hasListener(java.util.EventListener listener) {
 		java.util.List list = java.util.Arrays.asList(org.jfree.data.general.AbstractDataset.this.listenerList.getListenerList());
-		return list.contains(listener);
+		return true;
 	}
 
 	protected void fireDatasetChanged() {
```


---
## Patch 1 of bug id Chart13
### Patch Diff Hash-SHA-256:

54d06e41edac66f80e5cdeb64507757f6e3b566ba0bb93920e554e8e523f136e

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -267,10 +267,8 @@
 			h[1] = size.height;
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
-		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.centerBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.centerBlock.setBounds(new java.awt.geom.Rectangle2D.Double(w[2], h[0], w[4], h[4]));
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 2 of bug id Chart13
### Patch Diff Hash-SHA-256:

47fe4566395d7bdf98344f92986a17771faf8cfec21161f6114ce7d9b28c0212

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -254,7 +254,7 @@
 	protected org.jfree.chart.util.Size2D arrangeFF(org.jfree.chart.block.BlockContainer container, java.awt.Graphics2D g2, org.jfree.chart.block.RectangleConstraint constraint) {
 		double[] w = new double[5];
 		double[] h = new double[5];
-		w[0] = constraint.getWidth();
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c1 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, constraint.getHeight()), org.jfree.chart.block.LengthConstraintType.RANGE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.topBlock.arrange(g2, c1);
```


---
## Patch 3 of bug id Chart13
### Patch Diff Hash-SHA-256:

00d1064ad040287804190c6ac980e0c14d537dd239baedcb688d5eaab30ad797

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -273,10 +273,8 @@
 			w[2] = size.width;
 		}
 		h[3] = h[2];
-		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
-			w[3] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.leftBlock.setBounds(new java.awt.geom.Rectangle2D.Double(0.0, h[0], w[2], h[2]));
 		}
 		h[4] = h[2];
 		w[4] = ((constraint.getWidth()) - (w[3])) - (w[2]);
```


---
## Patch 4 of bug id Chart13
### Patch Diff Hash-SHA-256:

38e33270d5b755fd3a88f3b5ae7be8e4a549f3de60f891f737ba6d2a5853b9ac

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			h[3] = h[2];
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 5 of bug id Chart13
### Patch Diff Hash-SHA-256:

ebde7ec085fa13d67b009df998121731a6adfa80b9f0a8303952d6c86aad0b98

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -170,7 +170,7 @@
 		org.jfree.chart.block.RectangleConstraint c2 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, width), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c2);
-			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 			h[2] = size.height;
 		}
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 6 of bug id Chart13
### Patch Diff Hash-SHA-256:

c2aeb0e5afa8a7bff0f6a7f5540203e1fd52b504f9736779a72a1a3cf92625b6

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -177,7 +177,7 @@
 			double maxW = java.lang.Math.max((width - (w[2])), 0.0);
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(java.lang.Math.min(w[2], maxW), maxW), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c3);
-			w[3] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 			h[3] = size.height;
 		}
 		h[2] = java.lang.Math.max(h[2], h[3]);
```


---
## Patch 7 of bug id Chart13
### Patch Diff Hash-SHA-256:

aa5a745a1bfe5084d5032936e41c7860bb200c871a58b93beefd7c457143ddf8

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -180,6 +180,7 @@
 			w[3] = size.width;
 			h[3] = size.height;
 		}
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		h[2] = java.lang.Math.max(h[2], h[3]);
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.centerBlock) != null) {
```


---
## Patch 8 of bug id Chart13
### Patch Diff Hash-SHA-256:

c7db783401f9941cf4a49aef3e35b2e8b0950ab4370bef0aff4636cd3abd8c79

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -273,11 +273,6 @@
 			w[2] = size.width;
 		}
 		h[3] = h[2];
-		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
-			w[3] = size.width;
-		}
 		h[4] = h[2];
 		w[4] = ((constraint.getWidth()) - (w[3])) - (w[2]);
 		org.jfree.chart.block.RectangleConstraint c5 = new org.jfree.chart.block.RectangleConstraint(w[4], h[4]);
```


---
## Patch 9 of bug id Chart13
### Patch Diff Hash-SHA-256:

8f82195f1029bce34c107664ae0647a07f57e0507d73cc7a9f1af233c89c27c0

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -260,7 +260,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.topBlock.arrange(g2, c1);
 			h[0] = size.height;
 		}
-		w[1] = w[0];
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.bottomBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c2 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, ((constraint.getHeight()) - (h[0]))), org.jfree.chart.block.LengthConstraintType.RANGE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.bottomBlock.arrange(g2, c2);
```


---
## Patch 10 of bug id Chart13
### Patch Diff Hash-SHA-256:

fb3a4886fe9ad56703e8eb73c76089c7348882ff47be6edadc876e44212014a1

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -267,11 +267,6 @@
 			h[1] = size.height;
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
-		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
-		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
```


---
## Patch 11 of bug id Chart13
### Patch Diff Hash-SHA-256:

f10522a01ecc92ba3db3c039e58d4ccf894870a4e7a65c1d7dc98d3f8f202dd4

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -177,7 +177,7 @@
 			double maxW = java.lang.Math.max((width - (w[2])), 0.0);
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(java.lang.Math.min(w[2], maxW), maxW), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c3);
-			w[3] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 			h[3] = size.height;
 		}
 		h[2] = java.lang.Math.max(h[2], h[3]);
```


---
## Patch 12 of bug id Chart13
### Patch Diff Hash-SHA-256:

dddbc8f2d142b65bef2aaf11606c9694632ef5ce7e28dd91c244a752cd8ac112

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -63,7 +63,8 @@
 			if (w == (org.jfree.chart.block.LengthConstraintType.FIXED)) {
 				if (h == (org.jfree.chart.block.LengthConstraintType.NONE)) {
 					contentSize = arrangeFN(container, g2, constraint.getWidth());
-				}else
+				}else {
+					org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 					if (h == (org.jfree.chart.block.LengthConstraintType.FIXED)) {
 						contentSize = arrangeFF(container, g2, constraint);
 					}else
@@ -71,7 +72,7 @@
 							contentSize = arrangeFR(container, g2, constraint);
 						}
 					
-				
+				}
 			}else
 				if (w == (org.jfree.chart.block.LengthConstraintType.RANGE)) {
 					if (h == (org.jfree.chart.block.LengthConstraintType.NONE)) {
```


---
## Patch 13 of bug id Chart13
### Patch Diff Hash-SHA-256:

d0364576b300c722d719cfaacf14c2c05dd9ae2df7018369c6def38056a1c8f5

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -267,10 +267,8 @@
 			h[1] = size.height;
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
-		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.topBlock.setBounds(new java.awt.geom.Rectangle2D.Double(0.0, 0.0, w[0], h[0]));
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 14 of bug id Chart13
### Patch Diff Hash-SHA-256:

7cc1a703216c16c11f30b70169a88a11ea48ba1215d5ffa71052851028ae680f

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -272,6 +272,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
 			w[2] = size.width;
 		}
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
```


---
## Patch 15 of bug id Chart13
### Patch Diff Hash-SHA-256:

8cc6369328d48217a9642f2b8827805639af5614343e9b4b2cf319c4299f1360

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -268,9 +268,7 @@
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.leftBlock.setBounds(new java.awt.geom.Rectangle2D.Double(0.0, h[0], w[2], h[2]));
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 16 of bug id Chart13
### Patch Diff Hash-SHA-256:

a8418ab572466c113c1a47e0fe3a73b9bcfce1dc02c5eacba587b6c63a047f4c

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -255,6 +255,7 @@
 		double[] w = new double[5];
 		double[] h = new double[5];
 		w[0] = constraint.getWidth();
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c1 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, constraint.getHeight()), org.jfree.chart.block.LengthConstraintType.RANGE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.topBlock.arrange(g2, c1);
```


---
## Patch 17 of bug id Chart13
### Patch Diff Hash-SHA-256:

aff26eb2bfbe96fa9f41e644770cad107ef8ee41d38aa5b03ad1962acee5cf83

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -273,10 +273,8 @@
 			w[2] = size.width;
 		}
 		h[3] = h[2];
-		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
-			w[3] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.bottomBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.bottomBlock.setBounds(new java.awt.geom.Rectangle2D.Double(0.0, ((h[0]) + (h[2])), w[1], h[1]));
 		}
 		h[4] = h[2];
 		w[4] = ((constraint.getWidth()) - (w[3])) - (w[2]);
```


---
## Patch 18 of bug id Chart13
### Patch Diff Hash-SHA-256:

e47ea762562789ca8e0e3a518b0617dd69a74dc78bbaa28d526e369a126da4a6

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,6 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 19 of bug id Chart13
### Patch Diff Hash-SHA-256:

a50f631a121f3a1ce8e821f1d9ee4be2d75f746cab2d4c37e97088bd070da02f

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -267,10 +267,8 @@
 			h[1] = size.height;
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
-		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.bottomBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.bottomBlock.setBounds(new java.awt.geom.Rectangle2D.Double(0.0, ((h[0]) + (h[2])), w[1], h[1]));
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 20 of bug id Chart13
### Patch Diff Hash-SHA-256:

1965002925d35e4305293f4d2d6d9436c93fb318c69450898a601d30ba0a0e7d

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -266,7 +266,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.bottomBlock.arrange(g2, c2);
 			h[1] = size.height;
 		}
-		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
```


---
## Patch 21 of bug id Chart13
### Patch Diff Hash-SHA-256:

bb4bf0aa4a423527baec74ab590a6350e9ca6df6835e15331eb9ae8ef57dc872

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			w[1] = w[0];
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 22 of bug id Chart13
### Patch Diff Hash-SHA-256:

20ecf353562afe5ef003df2d4bc75dba8a6ae3e602d66914d97fdeb1133cb6f1

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -178,6 +178,7 @@
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(java.lang.Math.min(w[2], maxW), maxW), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c3);
 			w[3] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 			h[3] = size.height;
 		}
 		h[2] = java.lang.Math.max(h[2], h[3]);
```


---
## Patch 23 of bug id Chart13
### Patch Diff Hash-SHA-256:

373794aa666f96e6b9e94e841ff310a4f4fee9bafdf5c90ba90cd21a33e0bcdd

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -252,6 +252,7 @@
 	}
 
 	protected org.jfree.chart.util.Size2D arrangeFF(org.jfree.chart.block.BlockContainer container, java.awt.Graphics2D g2, org.jfree.chart.block.RectangleConstraint constraint) {
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		double[] w = new double[5];
 		double[] h = new double[5];
 		w[0] = constraint.getWidth();
```


---
## Patch 24 of bug id Chart13
### Patch Diff Hash-SHA-256:

60ee95418de2b1e275022e975d67162fbfe9cf438d7cad644f1f6814fc27ff1c

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -260,6 +260,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.topBlock.arrange(g2, c1);
 			h[0] = size.height;
 		}
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		w[1] = w[0];
 		if ((org.jfree.chart.block.BorderArrangement.this.bottomBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c2 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, ((constraint.getHeight()) - (h[0]))), org.jfree.chart.block.LengthConstraintType.RANGE);
```


---
## Patch 25 of bug id Chart13
### Patch Diff Hash-SHA-256:

3ffdd7499595b0a93cd7df9656e3fbf5b5a8e9ce1989677a02863bc7cd2ae4b9

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -260,7 +260,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.topBlock.arrange(g2, c1);
 			h[0] = size.height;
 		}
-		w[1] = w[0];
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.bottomBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c2 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, ((constraint.getHeight()) - (h[0]))), org.jfree.chart.block.LengthConstraintType.RANGE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.bottomBlock.arrange(g2, c2);
```


---
## Patch 26 of bug id Chart13
### Patch Diff Hash-SHA-256:

2ce6b9a031aceb95e6707b2723a0379287082627b6fbfc6d12da1db592f6eb39

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -274,9 +274,7 @@
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
-			w[3] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.rightBlock.setBounds(new java.awt.geom.Rectangle2D.Double(((w[2]) + (w[4])), h[0], w[3], h[3]));
 		}
 		h[4] = h[2];
 		w[4] = ((constraint.getWidth()) - (w[3])) - (w[2]);
```


---
## Patch 27 of bug id Chart13
### Patch Diff Hash-SHA-256:

529c29d9fe1a204d92e3f767fbfa3e5ed3bc3e5dc33ce976a42034bc3f35a667

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -180,6 +180,7 @@
 			w[3] = size.width;
 			h[3] = size.height;
 		}
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		h[2] = java.lang.Math.max(h[2], h[3]);
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.centerBlock) != null) {
```


---
## Patch 28 of bug id Chart13
### Patch Diff Hash-SHA-256:

6e27e8d7a701fe89373d046807c696516acb1d002439d56f26df9a5eea28deaf

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 29 of bug id Chart13
### Patch Diff Hash-SHA-256:

a2377f5be16a7a0c1720a5d35d1045388c838824edebfc181b4e4735235293e1

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -267,10 +267,8 @@
 			h[1] = size.height;
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
-		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.rightBlock.setBounds(new java.awt.geom.Rectangle2D.Double(((w[2]) + (w[4])), h[0], w[3], h[3]));
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 30 of bug id Chart13
### Patch Diff Hash-SHA-256:

36669a64768418e72a049eb528ae8418f21104aa452e611d72f307d703365b99

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -181,7 +181,7 @@
 			h[3] = size.height;
 		}
 		h[2] = java.lang.Math.max(h[2], h[3]);
-		h[3] = h[2];
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.centerBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(((width - (w[2])) - (w[3])), null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.centerBlock.arrange(g2, c4);
```


---
## Patch 31 of bug id Chart13
### Patch Diff Hash-SHA-256:

b8af9e7bfd5d2a64f6dc59265b22ef8ab2e42c35fd55721d96813f5cf351bc2c

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -181,7 +181,7 @@
 			h[3] = size.height;
 		}
 		h[2] = java.lang.Math.max(h[2], h[3]);
-		h[3] = h[2];
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.centerBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(((width - (w[2])) - (w[3])), null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.centerBlock.arrange(g2, c4);
```


---
## Patch 32 of bug id Chart13
### Patch Diff Hash-SHA-256:

2bd086ec4153407d6fe37aa96ea3efb8f6f0b1a982758c559935378660dae2d6

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			h[4] = h[2];
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 33 of bug id Chart13
### Patch Diff Hash-SHA-256:

5b8f6d4f0b67cd66c7134cbafb25f527e9ae6e0898eca1d3f6633b439a0848ba

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -254,7 +254,7 @@
 	protected org.jfree.chart.util.Size2D arrangeFF(org.jfree.chart.block.BlockContainer container, java.awt.Graphics2D g2, org.jfree.chart.block.RectangleConstraint constraint) {
 		double[] w = new double[5];
 		double[] h = new double[5];
-		w[0] = constraint.getWidth();
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c1 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, constraint.getHeight()), org.jfree.chart.block.LengthConstraintType.RANGE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.topBlock.arrange(g2, c1);
```


---
## Patch 34 of bug id Chart13
### Patch Diff Hash-SHA-256:

89969bbc27b8a094280731b5a4bc30df000728a1956445ebf6722341d8dc9e54

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -273,10 +273,8 @@
 			w[2] = size.width;
 		}
 		h[3] = h[2];
-		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
-			w[3] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.centerBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.centerBlock.setBounds(new java.awt.geom.Rectangle2D.Double(w[2], h[0], w[4], h[4]));
 		}
 		h[4] = h[2];
 		w[4] = ((constraint.getWidth()) - (w[3])) - (w[2]);
```


---
## Patch 35 of bug id Chart13
### Patch Diff Hash-SHA-256:

5c1958b68fbcab8f7463c2f0d47127805e737d06f301d8e645260bba71bdefe4

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			w[0] = constraint.getWidth();
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 36 of bug id Chart13
### Patch Diff Hash-SHA-256:

af93e5a9cfa029d5944896b619a0576d9d880c4f1ba9fb6197fcea7249d6aa34

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -273,10 +273,8 @@
 			w[2] = size.width;
 		}
 		h[3] = h[2];
-		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
-			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
-			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
-			w[3] = size.width;
+		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.topBlock.setBounds(new java.awt.geom.Rectangle2D.Double(0.0, 0.0, w[0], h[0]));
 		}
 		h[4] = h[2];
 		w[4] = ((constraint.getWidth()) - (w[3])) - (w[2]);
```


---
## Patch 37 of bug id Chart13
### Patch Diff Hash-SHA-256:

133881153cf3a24a20de9b58234c0fa167b59209c9088a1a5bd3782bb59faa03

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 38 of bug id Chart13
### Patch Diff Hash-SHA-256:

4854efac1bf953411322d39a6624ec8059a77154606e8d345a7ea5e4938130a2

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.centerBlock = null;
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 39 of bug id Chart13
### Patch Diff Hash-SHA-256:

92c4fb1c8a59f650a7ce3c100e24a221c3ee8e7ef557e0174d8a93e4c45459ca

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -181,6 +181,7 @@
 			h[3] = size.height;
 		}
 		h[2] = java.lang.Math.max(h[2], h[3]);
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.centerBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(((width - (w[2])) - (w[3])), null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
```


---
## Patch 40 of bug id Chart13
### Patch Diff Hash-SHA-256:

d8e1c7f3178c92ad8d2fcf6bc62aeae78a5ae97c24708e4ace52b69831b26ff4

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -269,6 +269,7 @@
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
+			org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
 			w[2] = size.width;
 		}
```


---
## Patch 41 of bug id Chart13
### Patch Diff Hash-SHA-256:

8ef66c3625df5aaf459dcce627d0f3bd539ce65aab73d261ef372c2364c52fd7

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -254,6 +254,7 @@
 	protected org.jfree.chart.util.Size2D arrangeFF(org.jfree.chart.block.BlockContainer container, java.awt.Graphics2D g2, org.jfree.chart.block.RectangleConstraint constraint) {
 		double[] w = new double[5];
 		double[] h = new double[5];
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		w[0] = constraint.getWidth();
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c1 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, constraint.getHeight()), org.jfree.chart.block.LengthConstraintType.RANGE);
```


---
## Patch 42 of bug id Chart13
### Patch Diff Hash-SHA-256:

ec75e7bb423254cb5d8a3ed46563e6f8139087f7783a1eab744c32842cfb7ce8

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			h[2] = java.lang.Math.max(h[2], h[3]);
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 43 of bug id Chart13
### Patch Diff Hash-SHA-256:

8fb7778e4d637e7efc0a1a628e3c57f38b9d488ffe359e3e8cb20d0b31653b6b

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.bottomBlock = null;
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 44 of bug id Chart13
### Patch Diff Hash-SHA-256:

c4092b915b3bc40dc14f491bb3219f7458ace686bcd6e079cb8ad98f46081982

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -189,7 +189,7 @@
 			h[4] = size.height;
 		}
 		double height = ((h[0]) + (h[1])) + (java.lang.Math.max(h[2], java.lang.Math.max(h[3], h[4])));
-		return arrange(container, g2, new org.jfree.chart.block.RectangleConstraint(width, height));
+		return new org.jfree.chart.util.Size2D(width, height);
 	}
 
 	protected org.jfree.chart.util.Size2D arrangeRR(org.jfree.chart.block.BlockContainer container, org.jfree.data.Range widthRange, org.jfree.data.Range heightRange, java.awt.Graphics2D g2) {
```


---
## Patch 45 of bug id Chart13
### Patch Diff Hash-SHA-256:

ec40f54313207d8f46380e7d61aa7e299f72522917337d2407ffe8c396c16389

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -177,6 +177,7 @@
 			double maxW = java.lang.Math.max((width - (w[2])), 0.0);
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(java.lang.Math.min(w[2], maxW), maxW), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c3);
+			org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 			w[3] = size.width;
 			h[3] = size.height;
 		}
```


---
## Patch 46 of bug id Chart13
### Patch Diff Hash-SHA-256:

923a38e6387a3db5db8ca89f568f2389e3b45614539154e5dd11a6935e479d94

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -266,7 +266,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.bottomBlock.arrange(g2, c2);
 			h[1] = size.height;
 		}
-		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
```


---
## Patch 47 of bug id Chart13
### Patch Diff Hash-SHA-256:

0808823c0ed39163fa104f94bc275ed0446ba288f50dd1e45dea81311f0ccc8e

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 48 of bug id Chart13
### Patch Diff Hash-SHA-256:

12e43b1dae8714e7281c69b06293525488d6a34e194144abb7fe4efa1f75a9f9

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			w[4] = ((constraint.getWidth()) - (w[3])) - (w[2]);
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 49 of bug id Chart13
### Patch Diff Hash-SHA-256:

2c9f97cfe12c7567802b2ebe5c09912cb5f7525f08b5ba6af7a5b74febea412d

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -253,6 +253,7 @@
 
 	protected org.jfree.chart.util.Size2D arrangeFF(org.jfree.chart.block.BlockContainer container, java.awt.Graphics2D g2, org.jfree.chart.block.RectangleConstraint constraint) {
 		double[] w = new double[5];
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		double[] h = new double[5];
 		w[0] = constraint.getWidth();
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
```


---
## Patch 50 of bug id Chart13
### Patch Diff Hash-SHA-256:

678af7908870c72d9735dc413b8577279c9a4551aeb01bd5517d9e528c80d97a

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -63,7 +63,8 @@
 			if (w == (org.jfree.chart.block.LengthConstraintType.FIXED)) {
 				if (h == (org.jfree.chart.block.LengthConstraintType.NONE)) {
 					contentSize = arrangeFN(container, g2, constraint.getWidth());
-				}else
+				}else {
+					org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 					if (h == (org.jfree.chart.block.LengthConstraintType.FIXED)) {
 						contentSize = arrangeFF(container, g2, constraint);
 					}else
@@ -71,7 +72,7 @@
 							contentSize = arrangeFR(container, g2, constraint);
 						}
 					
-				
+				}
 			}else
 				if (w == (org.jfree.chart.block.LengthConstraintType.RANGE)) {
 					if (h == (org.jfree.chart.block.LengthConstraintType.NONE)) {
```


---
## Patch 51 of bug id Chart13
### Patch Diff Hash-SHA-256:

1061bfed02819837397a3a576ed0e9e2be78256ea03dd8f330dcdcedd631d367

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -261,6 +261,7 @@
 			h[0] = size.height;
 		}
 		w[1] = w[0];
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.bottomBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c2 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, ((constraint.getHeight()) - (h[0]))), org.jfree.chart.block.LengthConstraintType.RANGE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.bottomBlock.arrange(g2, c2);
```


---
## Patch 52 of bug id Chart13
### Patch Diff Hash-SHA-256:

0f8cb52831e21b330d766dcd314bf1121d3f4d56cf4ec290682cc1e4e2478624

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,7 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
-			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.topBlock = null;
 		}
 		h[3] = h[2];
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 53 of bug id Chart13
### Patch Diff Hash-SHA-256:

ade43ef53e06d16bb031b30b656c9371955d7823c2818d684c27370dbce37837

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -174,6 +174,7 @@
 			h[2] = size.height;
 		}
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 			double maxW = java.lang.Math.max((width - (w[2])), 0.0);
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(java.lang.Math.min(w[2], maxW), maxW), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c3);
```


---
## Patch 54 of bug id Chart13
### Patch Diff Hash-SHA-256:

d58e89d4e4f46f4e52dc5978c1056b65a4d13ec1c37eb132569981ae6e577857

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -171,6 +171,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c2);
 			w[2] = size.width;
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 			h[2] = size.height;
 		}
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
```


---
## Patch 55 of bug id Chart13
### Patch Diff Hash-SHA-256:

a1b6c74bc76d0859f09dd3b4388c8a168c7faa456b22bb0ffeea01e2b2793e8d

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -272,7 +272,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
 			w[2] = size.width;
 		}
-		h[3] = h[2];
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
```


---
## Patch 56 of bug id Chart13
### Patch Diff Hash-SHA-256:

3d2ac1fef0cd5792f0e790cb14a31e017558bed8737ed226c133eacdd44743cd

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -179,6 +179,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c3);
 			w[3] = size.width;
 			h[3] = size.height;
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		}
 		h[2] = java.lang.Math.max(h[2], h[3]);
 		h[3] = h[2];
```


---
## Patch 57 of bug id Chart13
### Patch Diff Hash-SHA-256:

ede56b7afb53b31765e28ae44df7d3ee9acaa86fdc4f9d52cb7437c34dd8e546

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -253,6 +253,7 @@
 
 	protected org.jfree.chart.util.Size2D arrangeFF(org.jfree.chart.block.BlockContainer container, java.awt.Graphics2D g2, org.jfree.chart.block.RectangleConstraint constraint) {
 		double[] w = new double[5];
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		double[] h = new double[5];
 		w[0] = constraint.getWidth();
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
```


---
## Patch 58 of bug id Chart13
### Patch Diff Hash-SHA-256:

4e1abd8a0650d21e39069448704f7b6e26ed41f386ed54249b6962bc4d0e9500

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -188,6 +188,7 @@
 			w[4] = size.width;
 			h[4] = size.height;
 		}
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		double height = ((h[0]) + (h[1])) + (java.lang.Math.max(h[2], java.lang.Math.max(h[3], h[4])));
 		return arrange(container, g2, new org.jfree.chart.block.RectangleConstraint(width, height));
 	}
```


---
## Patch 59 of bug id Chart13
### Patch Diff Hash-SHA-256:

bdc5ead9a8fb1ae7eccf5ccb0d51fdcef9d228987396615579799ba95cfff9d7

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -170,6 +170,7 @@
 		org.jfree.chart.block.RectangleConstraint c2 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, width), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c2);
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 			w[2] = size.width;
 			h[2] = size.height;
 		}
```


---
## Patch 60 of bug id Chart13
### Patch Diff Hash-SHA-256:

2cb1bc59474bf590cb9bd43ced205ca5f96692e09b502788440d350126ea489e

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -254,6 +254,7 @@
 	protected org.jfree.chart.util.Size2D arrangeFF(org.jfree.chart.block.BlockContainer container, java.awt.Graphics2D g2, org.jfree.chart.block.RectangleConstraint constraint) {
 		double[] w = new double[5];
 		double[] h = new double[5];
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		w[0] = constraint.getWidth();
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c1 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, constraint.getHeight()), org.jfree.chart.block.LengthConstraintType.RANGE);
```


---
## Patch 61 of bug id Chart13
### Patch Diff Hash-SHA-256:

c509af06fe7a4a52dd76609a111f23b0f6623c0a9008567ce1b8480158d5d71b

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -267,6 +267,7 @@
 			h[1] = size.height;
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
```


---
## Patch 62 of bug id Chart13
### Patch Diff Hash-SHA-256:

b66310f9765e4566284a2538b85fdfcab9566c80367cc0409950205d2b264f8d

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -270,6 +270,7 @@
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
+			org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 			w[2] = size.width;
 		}
 		h[3] = h[2];
```


---
## Patch 63 of bug id Chart13
### Patch Diff Hash-SHA-256:

b3c5ef0182eeec8b93058b4b44f83697b93b53da5d5741af9f98e3a627acd065

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -188,6 +188,7 @@
 			w[4] = size.width;
 			h[4] = size.height;
 		}
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		double height = ((h[0]) + (h[1])) + (java.lang.Math.max(h[2], java.lang.Math.max(h[3], h[4])));
 		return arrange(container, g2, new org.jfree.chart.block.RectangleConstraint(width, height));
 	}
```


---
## Patch 64 of bug id Chart13
### Patch Diff Hash-SHA-256:

61e1eb34a8e6dd1ac2ae13d725a1d38e8741c78ab580e241f405f57e95c624e0

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -267,6 +267,7 @@
 			h[1] = size.height;
 		}
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.leftBlock.arrange(g2, c3);
```


---
## Patch 65 of bug id Chart13
### Patch Diff Hash-SHA-256:

624f4fdf2a9c2802114798d6788122a550d096f98ebc8e6bf137651636ae9490

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -175,6 +175,7 @@
 		}
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
 			double maxW = java.lang.Math.max((width - (w[2])), 0.0);
+			org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(java.lang.Math.min(w[2], maxW), maxW), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c3);
 			w[3] = size.width;
```


---
## Patch 66 of bug id Chart13
### Patch Diff Hash-SHA-256:

8b69631c301713f818670569b8952bda498cde80ff370bb3e79d005a8a8a61d0

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -255,6 +255,7 @@
 		double[] w = new double[5];
 		double[] h = new double[5];
 		w[0] = constraint.getWidth();
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.topBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c1 = new org.jfree.chart.block.RectangleConstraint(w[0], null, org.jfree.chart.block.LengthConstraintType.FIXED, 0.0, new org.jfree.data.Range(0.0, constraint.getHeight()), org.jfree.chart.block.LengthConstraintType.RANGE);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.topBlock.arrange(g2, c1);
```


---
## Patch 67 of bug id Chart13
### Patch Diff Hash-SHA-256:

1d4c6baa96fdfead448e3e08286d204e3fc9e65b043357f78f9eef301cc5790d

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -189,6 +189,7 @@
 			h[4] = size.height;
 		}
 		double height = ((h[0]) + (h[1])) + (java.lang.Math.max(h[2], java.lang.Math.max(h[3], h[4])));
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		return arrange(container, g2, new org.jfree.chart.block.RectangleConstraint(width, height));
 	}
```


---
## Patch 68 of bug id Chart13
### Patch Diff Hash-SHA-256:

4b385040ebbb08631fadd3ec180c0de185ad2b3101eb48f462bb41b146924c7f

### Patch Diff:
```
--- /original/org/jfree/chart/block/AbstractBlock.java	
+++ /fixed/org/jfree/chart/block/AbstractBlock.java	
@@ -196,7 +196,7 @@
 	protected double calculateTotalHeight(double contentHeight) {
 		double result = contentHeight;
 		result = org.jfree.chart.block.AbstractBlock.this.padding.extendHeight(result);
-		result = org.jfree.chart.block.AbstractBlock.this.frame.getInsets().extendHeight(result);
+		org.jfree.chart.block.AbstractBlock.this.width = 0.0;
 		result = org.jfree.chart.block.AbstractBlock.this.margin.extendHeight(result);
 		return result;
 	}
```


---
## Patch 69 of bug id Chart13
### Patch Diff Hash-SHA-256:

c34dc4d4d4b154c151bd5247e098987c6a1c6f953162c0b6cd2fcdc0f2c89a2e

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -273,6 +273,7 @@
 			w[2] = size.width;
 		}
 		h[3] = h[2];
+		org.jfree.chart.block.BorderArrangement.this.rightBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c4 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, ((constraint.getWidth()) - (w[2]))), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.rightBlock.arrange(g2, c4);
```


---
## Patch 70 of bug id Chart13
### Patch Diff Hash-SHA-256:

b62afdd42e5900009cf4e08b87af78e998911a2b1ddf4eef4b23eb14717e1dc5

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -266,6 +266,7 @@
 			org.jfree.chart.util.Size2D size = org.jfree.chart.block.BorderArrangement.this.bottomBlock.arrange(g2, c2);
 			h[1] = size.height;
 		}
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		h[2] = ((constraint.getHeight()) - (h[1])) - (h[0]);
 		if ((org.jfree.chart.block.BorderArrangement.this.leftBlock) != null) {
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(0.0, constraint.getWidth()), org.jfree.chart.block.LengthConstraintType.RANGE, h[2], null, org.jfree.chart.block.LengthConstraintType.FIXED);
```


---
## Patch 71 of bug id Chart13
### Patch Diff Hash-SHA-256:

fe8f105ce566934686d0465a46633732e61cc936a10cb96392cd3c24e78e0fcb

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -173,6 +173,7 @@
 			w[2] = size.width;
 			h[2] = size.height;
 		}
+		org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 		if ((org.jfree.chart.block.BorderArrangement.this.rightBlock) != null) {
 			double maxW = java.lang.Math.max((width - (w[2])), 0.0);
 			org.jfree.chart.block.RectangleConstraint c3 = new org.jfree.chart.block.RectangleConstraint(0.0, new org.jfree.data.Range(java.lang.Math.min(w[2], maxW), maxW), org.jfree.chart.block.LengthConstraintType.RANGE, 0.0, null, org.jfree.chart.block.LengthConstraintType.NONE);
```


---
## Patch 72 of bug id Chart13
### Patch Diff Hash-SHA-256:

c2ccd207349f2ae8d15580d431b680d0bc7c5e704a8a6d60482598122bceed21

### Patch Diff:
```
--- /original/org/jfree/chart/block/BorderArrangement.java	
+++ /fixed/org/jfree/chart/block/BorderArrangement.java	
@@ -65,6 +65,7 @@
 					contentSize = arrangeFN(container, g2, constraint.getWidth());
 				}else
 					if (h == (org.jfree.chart.block.LengthConstraintType.FIXED)) {
+						org.jfree.chart.block.BorderArrangement.this.leftBlock = null;
 						contentSize = arrangeFF(container, g2, constraint);
 					}else
 						if (h == (org.jfree.chart.block.LengthConstraintType.RANGE)) {
```


---
## Patch 1 of bug id Chart5
### Patch Diff Hash-SHA-256:

d494826fa5d8e1367df1fab3f427b26f0aa6d9c4f24136ed2a7bfda4ec98261e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -203,7 +203,7 @@
 			existing.setY(y);
 		}else {
 			if (org.jfree.data.xy.XYSeries.this.autoSort) {
-				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
+				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
```


---
## Patch 2 of bug id Chart5
### Patch Diff Hash-SHA-256:

271a0010140f7073948bd51b10f6ae9426b778c0a85928657cf5144b4aaff024

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -203,7 +203,7 @@
 			existing.setY(y);
 		}else {
 			if (org.jfree.data.xy.XYSeries.this.autoSort) {
-				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
+				add(x, y, true);
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
```


---
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