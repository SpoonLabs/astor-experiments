
# Patches of Chart26 from Defects4J 
Total patches 6
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