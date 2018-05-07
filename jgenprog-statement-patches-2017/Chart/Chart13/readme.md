
# Patches of Chart13 from Defects4J 
Total patches 72
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