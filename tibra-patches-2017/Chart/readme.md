
## Patch 1 of bug id Chart11
### Patch Diff Hash-SHA-256:

5e9cb8d57ac602d816c41e85bb41767d550f3faec04d2e80414531f780c241b4

### Patch Diff:
```
--- /original/org/jfree/chart/util/ShapeUtilities.java	
+++ /fixed/org/jfree/chart/util/ShapeUtilities.java	
@@ -123,6 +123,7 @@
 			return false;
 		}
 		java.awt.geom.PathIterator iterator1 = p1.getPathIterator(null);
+		p1 = p2;
 		java.awt.geom.PathIterator iterator2 = p1.getPathIterator(null);
 		double[] d1 = new double[6];
 		double[] d2 = new double[6];
```


---
## Patch 1 of bug id Chart7
### Patch Diff Hash-SHA-256:

c2a5f319249ac64e04370be9ba9a6e860c19b15731dbb65edfd9f7569d623c42

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -74,6 +74,7 @@
 	}
 
 	public void add(org.jfree.data.time.TimePeriodValue item) {
+		this.minMiddleIndex = maxMiddleIndex;
 		if (item == null) {
 			throw new java.lang.IllegalArgumentException("Null item not allowed.");
 		}
```


---
## Patch 2 of bug id Chart7
### Patch Diff Hash-SHA-256:

9ed1c30226e01cc48b5323a7dbd6c4076f93a052912ae63b139a542ec35da6d1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return maxStartIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 3 of bug id Chart7
### Patch Diff Hash-SHA-256:

922e499ec90876da325fff4c8076cae19128a195c8f58a8e36f25d33f38a3c62

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -102,6 +102,12 @@
 		}else {
 			this.maxStartIndex = index;
 		}
+		if ((minMiddleIndex) > 0) {
+			(minMiddleIndex)++;
+			if (((minMiddleIndex) % (minMiddleIndex)) == 0) {
+				fireSeriesChanged();
+			}
+		}
 		if ((this.minMiddleIndex) >= 0) {
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
```


---
## Patch 4 of bug id Chart7
### Patch Diff Hash-SHA-256:

4e6e76902ab0ee7b500b923a0649f7da1c03b0c15cae8cfa3c13bc38dc042109

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return ((maxEndIndex) - (maxStartIndex)) + (maxStartIndex);
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 5 of bug id Chart7
### Patch Diff Hash-SHA-256:

8abd83ba10fbe71b4f063ca6274424ecd6f82dafe4f030d61cc1763731108f81

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return maxEndIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 6 of bug id Chart7
### Patch Diff Hash-SHA-256:

2a6f3fa5e0f851de2f747125c121d5789f0dca9032a4f72ae6f7cdc24024b8ba

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return this.maxStartIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 7 of bug id Chart7
### Patch Diff Hash-SHA-256:

6edc97935d1b4eb289ec472a2d552df1a0057fecb6d6a1423c2700ffe4f39137

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -155,6 +155,7 @@
 
 	public void add(org.jfree.data.time.TimePeriod period, double value) {
 		org.jfree.data.time.TimePeriodValue item = new org.jfree.data.time.TimePeriodValue(period, value);
+		minMiddleIndex -= maxMiddleIndex;
 		add(item);
 	}
```


---
## Patch 8 of bug id Chart7
### Patch Diff Hash-SHA-256:

b94dfcc8a2e7ed88ba4180e6ccfae321657e9a65600f4139901a3e35d214ac47

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -155,6 +155,7 @@
 
 	public void add(org.jfree.data.time.TimePeriod period, double value) {
 		org.jfree.data.time.TimePeriodValue item = new org.jfree.data.time.TimePeriodValue(period, value);
+		minMiddleIndex = maxEndIndex;
 		add(item);
 	}
```


---
## Patch 9 of bug id Chart7
### Patch Diff Hash-SHA-256:

be1489bf48d15e0527321e8066ac50ec79bdad1e4a97a5a3e29ec0efab31ac53

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -116,8 +116,8 @@
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
-				this.maxMiddleIndex = index;
+			if (org.jfree.data.time.SerialDate.isLeapYear(minStartIndex)) {
+				maxMiddleIndex = (maxMiddleIndex) + 1;
 			}
 		}else {
 			this.maxMiddleIndex = index;
```


---
## Patch 10 of bug id Chart7
### Patch Diff Hash-SHA-256:

c39454e3e4d3ac821155e912a4ace69801e87a756666b5252507c550b734bc14

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -78,6 +78,7 @@
 			throw new java.lang.IllegalArgumentException("Null item not allowed.");
 		}
 		this.data.add(item);
+		minMiddleIndex = maxMiddleIndex;
 		updateBounds(item.getPeriod(), ((this.data.size()) - 1));
 		fireSeriesChanged();
 	}
```


---
## Patch 11 of bug id Chart7
### Patch Diff Hash-SHA-256:

d9d3f52e3b1e0e3eb61914b9a2e2950c941faecff875bed7fd1cab3f885f60e5

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -255,7 +255,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return this.maxMiddleIndex;
+		return this.maxEndIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 12 of bug id Chart7
### Patch Diff Hash-SHA-256:

e7ce71609ddb26895fd8a4de6ebbc8cc21d95c8ac03c15d5a0be57e795fb095d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -126,6 +126,10 @@
 			long minEnd = getDataItem(this.minEndIndex).getPeriod().getEnd().getTime();
 			if (end < minEnd) {
 				this.minEndIndex = index;
+				if (index >= 0) {
+					this.data.remove(index);
+					fireSeriesChanged();
+				}
 			}
 		}else {
 			this.minEndIndex = index;
```


---
## Patch 13 of bug id Chart7
### Patch Diff Hash-SHA-256:

a9da9e04ea6a2a5f99d61ce70b82f855474ccf0be8779baa9d3a8474bd794604

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -126,6 +126,7 @@
 			long minEnd = getDataItem(this.minEndIndex).getPeriod().getEnd().getTime();
 			if (end < minEnd) {
 				this.minEndIndex = index;
+				this.data.remove(minMiddleIndex);
 			}
 		}else {
 			this.minEndIndex = index;
```


---
## Patch 14 of bug id Chart7
### Patch Diff Hash-SHA-256:

eeced183d6159445d376a03b3df838bee0fbff2e87663cb1d377b75b8025d445

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -96,6 +96,9 @@
 		}
 		if ((this.maxStartIndex) >= 0) {
 			long maxStart = getDataItem(this.maxStartIndex).getPeriod().getStart().getTime();
+			if ((minMiddleIndex) >= (maxMiddleIndex)) {
+				minMiddleIndex -= maxMiddleIndex;
+			}
 			if (start > maxStart) {
 				this.maxStartIndex = index;
 			}
```


---
## Patch 15 of bug id Chart7
### Patch Diff Hash-SHA-256:

cbf48ba363871bd69e6d0bc19662064ba0dba440e7b24f3d5b857be1dda078d2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -127,6 +127,7 @@
 			if (end < minEnd) {
 				this.minEndIndex = index;
 			}
+			maxMiddleIndex = maxStartIndex;
 		}else {
 			this.minEndIndex = index;
 		}
```


---
## Patch 16 of bug id Chart7
### Patch Diff Hash-SHA-256:

cdaaf4b954082818d448b4372abcec8d3c728309409033c62c9e62af06c68588

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -106,6 +106,7 @@
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long minMiddle = s + ((e - s) / 2);
+			minMiddleIndex = maxMiddleIndex;
 			if (middle < minMiddle) {
 				this.minMiddleIndex = index;
 			}
```


---
## Patch 17 of bug id Chart7
### Patch Diff Hash-SHA-256:

39100ac10c19d22b16ec1758f34ac43065846e6996127e40daa9335a76f5c666

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -116,8 +116,8 @@
 			long s = getDataItem(this.minMiddleIndex).getPeriod().getStart().getTime();
 			long e = getDataItem(this.minMiddleIndex).getPeriod().getEnd().getTime();
 			long maxMiddle = s + ((e - s) / 2);
-			if (middle > maxMiddle) {
-				this.maxMiddleIndex = index;
+			if (org.jfree.data.time.SerialDate.isLeapYear(maxMiddleIndex)) {
+				maxMiddleIndex = (maxMiddleIndex) + 1;
 			}
 		}else {
 			this.maxMiddleIndex = index;
```


---
## Patch 18 of bug id Chart7
### Patch Diff Hash-SHA-256:

f07c8c242e6a47197832e109b532e97a08f6df006142408aaedabe8539121353

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -96,6 +96,9 @@
 		}
 		if ((this.maxStartIndex) >= 0) {
 			long maxStart = getDataItem(this.maxStartIndex).getPeriod().getStart().getTime();
+			if ((minMiddleIndex) >= (maxStartIndex)) {
+				minMiddleIndex -= maxStartIndex;
+			}
 			if (start > maxStart) {
 				this.maxStartIndex = index;
 			}
```


---
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
## Patch 1 of bug id Chart24
### Patch Diff Hash-SHA-256:

d35594c95999f0a002f06a1a611881b72279c8d309e99763100f6bc73f157bbd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/GrayPaintScale.java	
+++ /fixed/org/jfree/chart/renderer/GrayPaintScale.java	
@@ -29,6 +29,7 @@
 	public java.awt.Paint getPaint(double value) {
 		double v = java.lang.Math.max(value, this.lowerBound);
 		v = java.lang.Math.min(v, this.upperBound);
+		value = v;
 		int g = ((int) (((value - (this.lowerBound)) / ((this.upperBound) - (this.lowerBound))) * 255.0));
 		return new java.awt.Color(g, g, g);
 	}
```


---
## Patch 1 of bug id Chart3
### Patch Diff Hash-SHA-256:

a86e529615cf8c94e1911e817b1ab2cc7196c425e0611466d6f582c9a834afe2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -194,6 +194,9 @@
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
+		if (((minY) <= (this.minY)) || ((minY) >= (this.maxY))) {
+			findBoundsByIteration();
+		}
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
```


---
## Patch 2 of bug id Chart3
### Patch Diff Hash-SHA-256:

0a2d0310d361b29c3150210fc622f4f7b8254a19e7bf61408a0a257cb0ed95f1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -194,6 +194,7 @@
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
 		java.lang.Class c = item.getPeriod().getClass();
+		findBoundsByIteration();
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
```


---
## Patch 3 of bug id Chart3
### Patch Diff Hash-SHA-256:

63b4f2eb2bb3306b95606e440fd131410f595aec91f661a79f377270647f1a07

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -236,7 +236,7 @@
 			}
 		}
 		if (added) {
-			updateBoundsForAddedItem(item);
+			findBoundsByIteration();
 			if ((getItemCount()) > (this.maximumItemCount)) {
 				org.jfree.data.time.TimeSeriesDataItem d = ((org.jfree.data.time.TimeSeriesDataItem) (this.data.remove(0)));
 				updateBoundsForRemovedItem(d);
```


---
## Patch 4 of bug id Chart3
### Patch Diff Hash-SHA-256:

ac9f236a0384acfd93b4b0ad8e57c6daada95e059b2c38f094a91ee50000052b

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,7 +243,7 @@
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
## Patch 5 of bug id Chart3
### Patch Diff Hash-SHA-256:

d3a25005c3783d2d57d8e785452782106ba8b9ce3630a24a04eefcd0dc7f12ea

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -212,6 +212,11 @@
 		int count = getItemCount();
 		if (count == 0) {
 			this.data.add(item);
+			if (!(java.lang.Double.isNaN(maxY))) {
+				if (((maxY) <= (this.minY)) || ((maxY) >= (this.maxY))) {
+					findBoundsByIteration();
+				}
+			}
 			added = true;
 		}else {
 			org.jfree.data.time.RegularTimePeriod last = getTimePeriod(((getItemCount()) - 1));
```


---
## Patch 6 of bug id Chart3
### Patch Diff Hash-SHA-256:

5aa009fd1e53a013c0c4d3ed55580e05250b3e7c7312dc0763787285831cc726

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,7 +243,7 @@
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
## Patch 7 of bug id Chart3
### Patch Diff Hash-SHA-256:

64bae89a6d30b96008bedf888165beb943e5f095e0e37fed98871ac5e45f7ee1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -197,17 +197,16 @@
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
-			if (!(this.timePeriodClass.equals(c))) {
-				java.lang.StringBuffer b = new java.lang.StringBuffer();
-				b.append("You are trying to add data where the time period class ");
-				b.append("is ");
-				b.append(item.getPeriod().getClass().getName());
-				b.append(", but the TimeSeries is expecting an instance of ");
-				b.append(this.timePeriodClass.getName());
-				b.append(".");
-				throw new org.jfree.data.general.SeriesException(b.toString());
+			if (notify) {
+				findBoundsByIteration();
+			}else
+				if ((item.getValue()) != null) {
+					double yy = item.getValue().doubleValue();
+					this.minY = minIgnoreNaN(this.minY, maxY);
+					this.maxY = minIgnoreNaN(this.maxY, maxY);
 			}
 
+
 		boolean added = false;
 		int count = getItemCount();
 		if (count == 0) {
```


---
## Patch 8 of bug id Chart3
### Patch Diff Hash-SHA-256:

91c60d1c6b790d908d55c8075d9b8fef8d7aec5335a2c63558992b658be5ecd1

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -189,6 +189,15 @@
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item, boolean notify) {
+		if (notify) {
+			findBoundsByIteration();
+		}else
+			if ((item.getValue()) != null) {
+				double yy = item.getValue().doubleValue();
+				this.minY = minIgnoreNaN(this.minY, maxY);
+				this.maxY = minIgnoreNaN(this.maxY, maxY);
+			}
+
 		if (item == null) {
 			throw new java.lang.IllegalArgumentException("Null 'item' argument.");
 		}
```


---
## Patch 9 of bug id Chart3
### Patch Diff Hash-SHA-256:

7637ccb43cd3e140a2d1f26bd9c073da94fb9aef98a565fb42c9fd594128a3c2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -218,6 +218,7 @@
 			if ((item.getPeriod().compareTo(last)) > 0) {
 				this.data.add(item);
 				added = true;
+				org.jfree.data.time.TimeSeriesDataItem oldItem = addOrUpdate(item.getPeriod(), item.getValue());
 			}else {
 				int index = java.util.Collections.binarySearch(this.data, item);
 				if (index < 0) {
```


---
## Patch 10 of bug id Chart3
### Patch Diff Hash-SHA-256:

13a66b047ec2e893ab13a165f47f13b74bfecebdee34e458530f2a5624b78100

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -246,6 +246,9 @@
 				fireSeriesChanged();
 			}
 		}
+		if (((minY) <= (this.minY)) || ((minY) >= (this.maxY))) {
+			findBoundsByIteration();
+		}
 	}
 
 	public void add(org.jfree.data.time.RegularTimePeriod period, double value) {
```


---
## Patch 11 of bug id Chart3
### Patch Diff Hash-SHA-256:

b72440dd82eab7bebe3d8b326bbf6bf30ca9bb895dd5b1a5ab26e222856e88fc

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -185,6 +185,7 @@
 	}
 
 	public void add(org.jfree.data.time.TimeSeriesDataItem item) {
+		updateBoundsForRemovedItem(item);
 		add(item, true);
 	}
```


---
## Patch 12 of bug id Chart3
### Patch Diff Hash-SHA-256:

2b9a1356d856904b5095b59b7438934956b903362f4261bc67f3dfa3e2e236ce

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -193,6 +193,7 @@
 			throw new java.lang.IllegalArgumentException("Null 'item' argument.");
 		}
 		item = ((org.jfree.data.time.TimeSeriesDataItem) (item.clone()));
+		updateBoundsForRemovedItem(item);
 		java.lang.Class c = item.getPeriod().getClass();
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
```


---
## Patch 13 of bug id Chart3
### Patch Diff Hash-SHA-256:

6887fb71803085588a687b9a15191c71588c7a82be7b93b98c21f985603b75a4

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -197,15 +197,10 @@
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
 		}else
-			if (!(this.timePeriodClass.equals(c))) {
-				java.lang.StringBuffer b = new java.lang.StringBuffer();
-				b.append("You are trying to add data where the time period class ");
-				b.append("is ");
-				b.append(item.getPeriod().getClass().getName());
-				b.append(", but the TimeSeries is expecting an instance of ");
-				b.append(this.timePeriodClass.getName());
-				b.append(".");
-				throw new org.jfree.data.general.SeriesException(b.toString());
+			if (!(java.lang.Double.isNaN(maxY))) {
+				if (((maxY) <= (this.minY)) || ((maxY) >= (this.maxY))) {
+					findBoundsByIteration();
+				}
 			}
 
 		boolean added = false;
```


---
## Patch 14 of bug id Chart3
### Patch Diff Hash-SHA-256:

cabd66b8f18c647dfbc54ca128ddf66c847a6019968dd9f179005a9fcc56e2c2

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -235,6 +235,7 @@
 				}
 			}
 		}
+		findBoundsByIteration();
 		if (added) {
 			updateBoundsForAddedItem(item);
 			if ((getItemCount()) > (this.maximumItemCount)) {
```


---
## Patch 15 of bug id Chart3
### Patch Diff Hash-SHA-256:

6e8216c69df728743e72cfe8ab3fb78133902682e7cc81ee0c60c521326f4acb

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -243,8 +243,14 @@
 			}
 			removeAgedItems(false);
 			if (notify) {
-				fireSeriesChanged();
+				findBoundsByIteration();
+			}else
+				if ((item.getValue()) != null) {
+					double yy = item.getValue().doubleValue();
+					this.minY = minIgnoreNaN(this.minY, maxY);
+					this.maxY = minIgnoreNaN(this.maxY, maxY);
 			}
+
 		}
 	}
```


---
## Patch 16 of bug id Chart3
### Patch Diff Hash-SHA-256:

ab609fe048b68b79804b97840c9c0ed7e2aafd0d4e9b100532a65e7dacc36755

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -96,6 +96,7 @@
 	}
 
 	public double getMinY() {
+		findBoundsByIteration();
 		return this.minY;
 	}
```


---
## Patch 17 of bug id Chart3
### Patch Diff Hash-SHA-256:

889554ceca93a14420e0c81b7307f3311f5a20334d368d16b4ef5cbc4c1e22e0

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -196,7 +196,10 @@
 		java.lang.Class c = item.getPeriod().getClass();
 		if ((this.timePeriodClass) == null) {
 			this.timePeriodClass = c;
-		}else
+		}else {
+			if (((maxY) <= (this.minY)) || ((maxY) >= (this.maxY))) {
+				findBoundsByIteration();
+			}
 			if (!(this.timePeriodClass.equals(c))) {
 				java.lang.StringBuffer b = new java.lang.StringBuffer();
 				b.append("You are trying to add data where the time period class ");
@@ -207,7 +210,7 @@
 				b.append(".");
 				throw new org.jfree.data.general.SeriesException(b.toString());
 			}
-
+		}
 		boolean added = false;
 		int count = getItemCount();
 		if (count == 0) {
```


---
## Patch 18 of bug id Chart3
### Patch Diff Hash-SHA-256:

1cea66c2f6f75d4b7c69ed34a15c4fe36e7c3f123ed3f30a8014561609f88975

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -209,6 +209,12 @@
 			}
 
 		boolean added = false;
+		if (notify) {
+			findBoundsByIteration();
+			if (notify) {
+				fireSeriesChanged();
+			}
+		}
 		int count = getItemCount();
 		if (count == 0) {
 			this.data.add(item);
```


---
## Patch 1 of bug id Chart12
### Patch Diff Hash-SHA-256:

2d5ed77fc02ea2823ae6d86309547a89688b82b9e816cd7488a320a308405c28

### Patch Diff:
```
--- /original/org/jfree/data/general/AbstractDataset.java	
+++ /fixed/org/jfree/data/general/AbstractDataset.java	
@@ -34,7 +34,7 @@
 
 	public boolean hasListener(java.util.EventListener listener) {
 		java.util.List list = java.util.Arrays.asList(this.listenerList.getListenerList());
-		return list.contains(listener);
+		return true;
 	}
 
 	protected void fireDatasetChanged() {
```


---
## Patch 1 of bug id Chart5
### Patch Diff Hash-SHA-256:

c1be83f474b57b502d7dd77b014168bce33c2dc5f980da61a8a26825a8036cef

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -210,6 +210,7 @@
 			}
 		}
 		fireSeriesChanged();
+		autoSort = false;
 		return overwritten;
 	}
```


---
## Patch 2 of bug id Chart5
### Patch Diff Hash-SHA-256:

b23cf92d5fe202738428eb5906edd4cfea66d34af2d08e7ea4935715180f81f0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -201,7 +201,7 @@
 			existing.setY(y);
 		}else {
 			if (this.autoSort) {
-				this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
+				this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
```


---
## Patch 3 of bug id Chart5
### Patch Diff Hash-SHA-256:

ab4c87de63e47b7435c35445c4d77c2f4d833842e50338ac2e05729d3ff017c9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -201,7 +201,7 @@
 			existing.setY(y);
 		}else {
 			if (this.autoSort) {
-				this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
+				add(x, y, true);
 			}else {
 				this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
```


---
## Patch 4 of bug id Chart5
### Patch Diff Hash-SHA-256:

b19874b5281caeb19ebb8451c6f3390321821eb0c8191020172edaf7cae88a12

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -209,6 +209,7 @@
 				this.data.remove(0);
 			}
 		}
+		autoSort = false;
 		fireSeriesChanged();
 		return overwritten;
 	}
```


---
## Patch 5 of bug id Chart5
### Patch Diff Hash-SHA-256:

01112d666ed4870e3319b57b9b81e8800c84dac23e4732831558cd9514f90ac1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -189,6 +189,7 @@
 		if (x == null) {
 			throw new java.lang.IllegalArgumentException("Null 'x' argument.");
 		}
+		autoSort = false;
 		org.jfree.data.xy.XYDataItem overwritten = null;
 		int index = indexOf(x);
 		if ((index >= 0) && (!(this.allowDuplicateXValues))) {
```


---
## Patch 6 of bug id Chart5
### Patch Diff Hash-SHA-256:

6998c2a0cf02bef50d055fe07cd4e7a8dbc93266f0132ff0483a2fb6fc4c7968

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -182,6 +182,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(double x, double y) {
+		x = y;
 		return addOrUpdate(new java.lang.Double(x), new java.lang.Double(y));
 	}
```


---
## Patch 7 of bug id Chart5
### Patch Diff Hash-SHA-256:

1632909c88e2583a69b8a54fa123a754cf966990b69c1a6d3b502cfdf2276045

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -182,6 +182,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(double x, double y) {
+		autoSort = false;
 		return addOrUpdate(new java.lang.Double(x), new java.lang.Double(y));
 	}
```


---
## Patch 8 of bug id Chart5
### Patch Diff Hash-SHA-256:

f032737c392ca6116698bfa5e29da00f70b683585cf0634c5444615eb6c7a22b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -205,6 +205,7 @@
 			}else {
 				this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
+			autoSort = false;
 			if ((getItemCount()) > (this.maximumItemCount)) {
 				this.data.remove(0);
 			}
```


---
## Patch 9 of bug id Chart5
### Patch Diff Hash-SHA-256:

cafba0a95cf7136dc94d7db54c61002650b892da6fdfa38f190621f4ef13fb91

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -190,6 +190,7 @@
 			throw new java.lang.IllegalArgumentException("Null 'x' argument.");
 		}
 		org.jfree.data.xy.XYDataItem overwritten = null;
+		autoSort = false;
 		int index = indexOf(x);
 		if ((index >= 0) && (!(this.allowDuplicateXValues))) {
 			org.jfree.data.xy.XYDataItem existing = ((org.jfree.data.xy.XYDataItem) (this.data.get(index)));
```


---
## Patch 10 of bug id Chart5
### Patch Diff Hash-SHA-256:

f586aba9c1c2d518e415ecb38aa21d901d904fba344a18c9cb745fdf8dae0f28

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -201,6 +201,7 @@
 			existing.setY(y);
 		}else {
 			if (this.autoSort) {
+				autoSort = false;
 				this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```


---
## Patch 11 of bug id Chart5
### Patch Diff Hash-SHA-256:

db5ebf6fb782ca789d7043df645cb197443305e9df27079e79c450ddeb39227f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -200,6 +200,7 @@
 			}
 			existing.setY(y);
 		}else {
+			autoSort = false;
 			if (this.autoSort) {
 				this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
```


---
## Patch 12 of bug id Chart5
### Patch Diff Hash-SHA-256:

86379601e8753f9285aed4b2b55bbf283616836e934589d6db2aa49ec19ba355

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -208,6 +208,7 @@
 			if ((getItemCount()) > (this.maximumItemCount)) {
 				this.data.remove(0);
 			}
+			autoSort = false;
 		}
 		fireSeriesChanged();
 		return overwritten;
```


---
## Patch 13 of bug id Chart5
### Patch Diff Hash-SHA-256:

dd384b859890a4eaef047cb8e98b4a7f09441ab7b9d38a7151a5c8421be205d1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -215,6 +215,7 @@
 
 	public int indexOf(java.lang.Number x) {
 		if (this.autoSort) {
+			autoSort = false;
 			return java.util.Collections.binarySearch(this.data, new org.jfree.data.xy.XYDataItem(x, null));
 		}else {
 			for (int i = 0; i < (this.data.size()); i++) {
```


---
## Patch 1 of bug id Chart9
### Patch Diff Hash-SHA-256:

11d2c7483032de4b34d40d2191be5cf2b94b515bbe5c076a7a7f451582d4d083

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -404,6 +404,13 @@
 		int endIndex = getIndex(end);
 		if (endIndex < 0) {
 			endIndex = -(endIndex + 1);
+			if (startIndex >= endIndex) {
+				startIndex -= endIndex;
+			}else
+				if (startIndex < 0) {
+					startIndex += endIndex;
+				}
+
 			endIndex = endIndex - 1;
 		}
 		if (endIndex < 0) {
```


---
## Patch 1 of bug id Chart17
### Patch Diff Hash-SHA-256:

28438de7e622fca9b351e019cac889cd01617769a3309ce6d16d9233dbfafd0a

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -363,6 +363,13 @@
 		if (start < 0) {
 			throw new java.lang.IllegalArgumentException("Requires start >= 0.");
 		}
+		if (end >= (maximumItemCount)) {
+			end -= maximumItemCount;
+		}else
+			if (end < 0) {
+				end += maximumItemCount;
+			}
+
 		if (end < start) {
 			throw new java.lang.IllegalArgumentException("Requires start <= end.");
 		}
```


---