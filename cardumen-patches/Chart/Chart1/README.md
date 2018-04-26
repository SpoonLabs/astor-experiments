
# Patches of Chart1 from Defects4J 
Total patches 780
## Patch 1 of bug id Chart1
### Patch Diff Hash-SHA-256:

57bedac08fd49994d4524f2d34944b800347fdad8e8057d161715f371af65c7e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart1
### Patch Diff Hash-SHA-256:

26c7d0453707db14eeb3de4c2a6e8a1522399aa64291691d3f635704c5073609

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.baseItemLabelGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart1
### Patch Diff Hash-SHA-256:

c1df6deecc17e58cba6dfd78f5ce4685d7f30d84ab24ff3dd14dd31dae751df6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.legendItemToolTipGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart1
### Patch Diff Hash-SHA-256:

1084d5ead11cf6847221eed88c1f50ec7f2914b06a0888efe2f5975cb9888488

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart1
### Patch Diff Hash-SHA-256:

2c580f1aedd34ed4146e6ca156e7c49abcbe8841aa6e0b1fbe0be253e6e758c3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (plot == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart1
### Patch Diff Hash-SHA-256:

974c0c3b06e82ef6f1b50590368d509534195d40c958f128df61313fa1b58d15

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((plot) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart1
### Patch Diff Hash-SHA-256:

c3f37784d9f08639d0aa04f4aac7b84b2a41aee03e21b1a9dcb90568bde734cf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.baseToolTipGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart1
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart1
### Patch Diff Hash-SHA-256:

eed4cbd50aee307fd0783e10e81a4a2dca7a1ad60a9a0840a5172b4cf0e7c5a0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart1
### Patch Diff Hash-SHA-256:

9a09f20425b827198624538d6bee1e3f6c2b859c15d9c09222791c8452048715

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.ZERO) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart1
### Patch Diff Hash-SHA-256:

b9a3f0640f3284d1e0d8b57c59b766df325748855786b5bd22bff72e6359d0d1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.legendItemURLGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart1
### Patch Diff Hash-SHA-256:

6ab0b5501c0dece2e4868e0b61fd20d31419ccd669e91f12fa4f213817447d79

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart1
### Patch Diff Hash-SHA-256:

528bc173adec395f6b35ec3191dd2c68c98562dbd81a6920fbf8e8776d494756

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart1
### Patch Diff Hash-SHA-256:

a5d11f14841b9729d0aecd2a7b09521d6fa27e168618231107898459ac202679

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.baseURLGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart1
### Patch Diff Hash-SHA-256:

764ec46eef5a0d34e17e3f43020afa78753c4df21e3b383177ce2d779a11acc0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.legendItemURLGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart1
### Patch Diff Hash-SHA-256:

eb295e1f10b03d9a69bbd6cf69467daad3c6c7d7486ea279074368bc6b4ee7d4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.baseToolTipGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart1
### Patch Diff Hash-SHA-256:

26dc4d3223c54684274cf1b0e4fd653602edc6fc9cb659e2ee5f1146594b6dda

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart1
### Patch Diff Hash-SHA-256:

c7418b2842ca7da22b4b20b0595c9a24ca0f06ef4aac3f3d2e91460f12b674ba

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart1
### Patch Diff Hash-SHA-256:

900895614e9b3dab46540a18971deb270c88a7b8c236fe485c7ab83c7daaba2e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.baseItemLabelGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Chart1
### Patch Diff Hash-SHA-256:

693d8a7365e8d83af0197ea2a74815ae6e145982cbacced52b039354552b30d5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof java.awt.GradientPaint) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Chart1
### Patch Diff Hash-SHA-256:

30c5af7e3e17207cb536f5ef80e8dad45bcc2d0e664afae8808affcfc8c67bed

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Chart1
### Patch Diff Hash-SHA-256:

87b9ea0f92fe8102845526fc0fb4bf3abf2216ec04b03695829436450cba59cb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((!(isSeriesVisible(index))) || (!(isSeriesVisibleInLegend(index)))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Chart1
### Patch Diff Hash-SHA-256:

769fe890933e0a3d1a3db3f92640a9b656ce34186bbcb905d23d15fbb82672fb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((!(isSeriesVisible(columnCount))) || (!(isSeriesVisibleInLegend(columnCount)))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Chart1
### Patch Diff Hash-SHA-256:

94c723c2b6995c6a788ae321c80a2b96da7f55ae1b322a5ae0ef927564ef64a2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Chart1
### Patch Diff Hash-SHA-256:

cb7879c8c9a587431b9cdb7ce4c249b2d4f2c516983d0424e954a239a1cc67fe

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Chart1
### Patch Diff Hash-SHA-256:

3cdedbfe4c021fb66d2198c8ee3a938580adf9ed3b1b50f40464c4d2c404a2c3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Chart1
### Patch Diff Hash-SHA-256:

02463ee11bb6188fb0be0fc058339b0733b75bb587cfb8578c483fe6ecea3bda

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Chart1
### Patch Diff Hash-SHA-256:

124d6c8daa37ed19833fd871502e36a95391e354ffdf2150927cd61b68a68c1c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Chart1
### Patch Diff Hash-SHA-256:

48a20e4213ef68fd38b4196e55598c4f7e2933e965a7e1bf7f71d7595a145504

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Chart1
### Patch Diff Hash-SHA-256:

c4bb00e727d4564a6c90c8521c177cb4bb9bbbb2ce3e16e4277cf86ab9d49790

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Chart1
### Patch Diff Hash-SHA-256:

27c32e5be7051c69ecaabe5cd4bb4cb618a9e851d7630dcd64ade8620f6c7640

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Chart1
### Patch Diff Hash-SHA-256:

7ba27f973b478cbb33b4a41dad1333686bf29988ec699e18ff4006173feeea4c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.legendItemToolTipGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Chart1
### Patch Diff Hash-SHA-256:

2c3da92ed06d6ebc70d417b3270df52522a8c5f261966b5c3f5ef91694bec344

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Chart1
### Patch Diff Hash-SHA-256:

7b7a07d579ce398e06bac927a0922c9d95adedb2682e1da6475853008641c30d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Chart1
### Patch Diff Hash-SHA-256:

e40a0b7874840055e2be005fcf31abc7dd2593d254e148ae0b86b781d5313487

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Chart1
### Patch Diff Hash-SHA-256:

957747303c8616042569f95428c3fb2be8fc572d0b7f75bd511ad59d660960c8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((!(isSeriesVisible(rowCount))) || (!(isSeriesVisibleInLegend(rowCount)))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Chart1
### Patch Diff Hash-SHA-256:

a72f6d16dc10011b087a7a0c3f41783148bcfd0bfa91d433e14ab5332a2e4780

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Chart1
### Patch Diff Hash-SHA-256:

bce49b0f9a2732d22e5f178d7e77d6eecbdf780a8e23b973ff6f67ebb22bad5a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.baseURLGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Chart1
### Patch Diff Hash-SHA-256:

45f33594e34995b50eab49a16f1c01487364f78409f2c9c3d1d5b8f085c1014c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Chart1
### Patch Diff Hash-SHA-256:

a872e27afdcbc8cf15b5324b30a3d49792475df6d85ca950d042b84b82206ad4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Chart1
### Patch Diff Hash-SHA-256:

2f7208c9985e7cbf9f770ee1b10f1cfb58d3a06afd2f2fae8e421b05a166e948

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Chart1
### Patch Diff Hash-SHA-256:

215bba8ac8db16de6aedd6dcd76538d4c5c0fccf69c7ebfdf73f214d75beb1ea

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof java.awt.GradientPaint) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Chart1
### Patch Diff Hash-SHA-256:

6ea07eea97c446a22837303bb36103efca313d148a1289c55c3d8a4cbbdfaacd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Chart1
### Patch Diff Hash-SHA-256:

42d9061de56086a901af7537fb9f12fe6b245d0f683d6f26a76aa075ffbeed7e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Chart1
### Patch Diff Hash-SHA-256:

502173d5244b730fb9f97066ac2e58ef70071657f88125519b3eb0ab27af75b8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Chart1
### Patch Diff Hash-SHA-256:

d55eedd53fbe6ffe9aa4ff32378561ce76cbb4f45fd58e1265b633423b6e51d0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Chart1
### Patch Diff Hash-SHA-256:

58bb4ab8f283c2be0a9b9409729dfdd43e40e20443034f93d60a157e7b93f3eb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Chart1
### Patch Diff Hash-SHA-256:

51fd7068a78f962afd0b11a6f1d0b099062dd0e49e7d4f2c720855568e5a1ddf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof java.awt.GradientPaint) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Chart1
### Patch Diff Hash-SHA-256:

fbfa1c7d1920140c285e7af2b89a3d012563e102fde29962b7d55d07bad06465

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Chart1
### Patch Diff Hash-SHA-256:

aea72f685ccbfe6edd8d3fd6ad4588153022981a5c996e4f2f187e0d380b2d87

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Chart1
### Patch Diff Hash-SHA-256:

b7c18792e0a7276cee3604ac4c0a6420fb85f6fd9c1f11622ed173573848a9bc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Chart1
### Patch Diff Hash-SHA-256:

34de3b4850fb7712de77c8219c01b0c866f18407f041744a15e0b7ae0fab5067

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Chart1
### Patch Diff Hash-SHA-256:

a021dee55985954bd12617862ad0fb06ad432253fcc9c9db4c26c6deec8e0d70

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Chart1
### Patch Diff Hash-SHA-256:

5075dd45276d1aac4281afb27f8ff7cf165e6df82994c3bb579462d4705a9569

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Chart1
### Patch Diff Hash-SHA-256:

d695834d85b8e65d682225172b8250376454f10973c5f572d492284557f76b43

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Chart1
### Patch Diff Hash-SHA-256:

efc295cd4178f02f66af6f220949b172593e50fb73f03a1fb114808ee648c662

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Chart1
### Patch Diff Hash-SHA-256:

dafa21c4b1c1481324bb1b805bc1e4d1a290097aedb67207a4f9abaf2c29567a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Chart1
### Patch Diff Hash-SHA-256:

5e89a2016b070fdaec289c04435fc6d345e081fcec10cee5300aca403e6ba541

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Chart1
### Patch Diff Hash-SHA-256:

52508920bb531861aabd3c81af6701833052a8c0b9db8171f78a08786f5644d9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Chart1
### Patch Diff Hash-SHA-256:

6bb4dd0366ef26c62c69aa2b51214cff1d50e2214fd0f4b1c495c0d5dd8c6b1a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Chart1
### Patch Diff Hash-SHA-256:

a2943fc05827685f7f9e128924c0e5c97022ee274369e1e7ec649a447c752998

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Chart1
### Patch Diff Hash-SHA-256:

4876ec72e049ec1ee7362ca557335b4a8f60f5d91ae881876624085ddf198bf3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Chart1
### Patch Diff Hash-SHA-256:

c64606a08900f684794d3536b9f7004e022600ec6821dc6af3b470a0c7639359

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Chart1
### Patch Diff Hash-SHA-256:

20b48fb02a37b977e6d7e183763d71dc3112a3a432f7775fd0c45137d9e8581b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Chart1
### Patch Diff Hash-SHA-256:

f280989d7b3b6ecb8187f8433223e5f709b73c952d77b80405fb1ede434e2c76

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Chart1
### Patch Diff Hash-SHA-256:

0e94141780a4ebbef39ef9d8de02c38cead9609fe9dcccf4b17da15b05b0288a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Chart1
### Patch Diff Hash-SHA-256:

f3e930d95274b4cd565501d60994742b8f202f661ac7e5315e7f28dcb7d34c36

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Chart1
### Patch Diff Hash-SHA-256:

c8b2f0382be84979285cb4751201175319adcd6e055ff77d4a5947090a84380e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Chart1
### Patch Diff Hash-SHA-256:

62b5a2c8b9b039cabe0b1f7ddd30c659105e36954a2b9f0c11457875717d8ade

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Chart1
### Patch Diff Hash-SHA-256:

87c4f1ded16a1d43f6e0c0780fa0729a5189c522b6da826cdcc031a8759484b9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Chart1
### Patch Diff Hash-SHA-256:

7b3e72edbe1343eeb75476c2cd4a318f18fd7dc99d9c5f05f4d4f9405dda72d2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Chart1
### Patch Diff Hash-SHA-256:

69e391d8173e27ee4b4e601077fe8d199c6a4f740460279ff2b58134de0b1ef4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Chart1
### Patch Diff Hash-SHA-256:

4b3c7df531b2c72286a4bb27ef01cb7d6795c3b8fa87c04b7e53b78e486b11d7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Chart1
### Patch Diff Hash-SHA-256:

bec74de85d970b495c6193affd2a43cddd31c938032c0d5acb9687bd253ed31d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) == (org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Chart1
### Patch Diff Hash-SHA-256:

1a8c87a7baa9465fdec73f1bc9f25d3eb0261cefbd727705e58686e43710beef

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (plot.isDomainPannable()) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Chart1
### Patch Diff Hash-SHA-256:

139a89730985cb7e75427772581eec83f498c1aab63b20ebafadc9d570365db3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.renderer.xy.XYLineAndShapeRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Chart1
### Patch Diff Hash-SHA-256:

92e77bb2591d28059c860ad5bbc3a6fb052ff12154dbfd8a4b3aef8f36fc1cc8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) <= ((rowCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Chart1
### Patch Diff Hash-SHA-256:

a02048cc9d656855f3e4173b805a9b1ade5a930a011b7d23b6ba2136a9df2653

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.axis.NumberTickUnit) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Chart1
### Patch Diff Hash-SHA-256:

429d5e7a351eb91ea70f5c8b52a096088fd18681657490fb4d9981d870ed8097

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Chart1
### Patch Diff Hash-SHA-256:

97e295b732693da920726a9c565c00ae73424ae40032935722c6bcfb76246edf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Chart1
### Patch Diff Hash-SHA-256:

bf9fea799c87d734b236e875090d8b7c7ad434e8fe221e5e810b1da55958e1e4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Chart1
### Patch Diff Hash-SHA-256:

84342c20090aba4b101d3da5821138048dcd308b731355c1b4093bce82d710e9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(legendItemURLGenerator)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Chart1
### Patch Diff Hash-SHA-256:

f51285a7a0a9c66a837af36b38e73191f9bbf5b7acfb2421dc79196e76443a59

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (backgroundAnnotations.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Chart1
### Patch Diff Hash-SHA-256:

752b3d198eb0616cb452f4997f2462220e2bdd72db703518fa69efd4ac906ca9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Chart1
### Patch Diff Hash-SHA-256:

0b37d9b550771017cdb26416f6d33e4708bd25f669557b77621229306fc4d04a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.data.time.TimeSeriesDataItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Chart1
### Patch Diff Hash-SHA-256:

cf852b4918dffc1931a83d461408d58db24b0312add88b470884efe282602cac

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.xy.XYBarDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Chart1
### Patch Diff Hash-SHA-256:

b3b62ae32d5a519aaf5413df7868ff895f10a4a46b31e5da9a49626c1c0b4cfc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.renderer.AbstractRenderer.ZERO.equals(org.jfree.chart.renderer.AbstractRenderer.ZERO))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Chart1
### Patch Diff Hash-SHA-256:

6d8526219c897c1313e9998d4fe2a665abf6bb5623a0be8727e9f462005f2596

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.data.time.TimeTableXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Chart1
### Patch Diff Hash-SHA-256:

653e07512bc849912c423b4aead46a5bf3fdb4a091edf17acbcddef9345edbfb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.renderer.GrayPaintScale) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Chart1
### Patch Diff Hash-SHA-256:

f8ce341ec277d13d3516ed4e5256b5bb472680a067a6baf737e46fe349ce12af

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.RangeInfo) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Chart1
### Patch Diff Hash-SHA-256:

50c4314100d9d153a76a156af973376ace438d0f77a20de1d9bbe16d23342cf2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof java.awt.Color) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Chart1
### Patch Diff Hash-SHA-256:

2f6ccbbf0e1d2140e955bc3131f549e1598f90443617ec86de96f34ab85d77ec

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (null == (org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Chart1
### Patch Diff Hash-SHA-256:

badbdda04a45b142fdcc1fa8d8141fdf6f8f554f6143a491ad8ebca1e26f7052

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(dataset)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Chart1
### Patch Diff Hash-SHA-256:

14ae91e9cc76d666018fe15a1412c813b02f9a740110052106fd7467b5549061

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < (backgroundAnnotations.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Chart1
### Patch Diff Hash-SHA-256:

4fc9482bd5e32167979cde6ce4c66d4333fd6c24a2f877cc44a72c863ecad72f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.KeyedObjects2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Chart1
### Patch Diff Hash-SHA-256:

85e25e2191bb3afe6413c5236ed489bd85c286c5cd904a1e9d67dcaeae97ffdc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.data.xy.DefaultXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Chart1
### Patch Diff Hash-SHA-256:

bfce561ebc0102a244ca42717a45e2c807478612f951fbb4d1cf2fb42a0020c9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.renderer.category.GroupedStackedBarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Chart1
### Patch Diff Hash-SHA-256:

7e9026314cd1913e5f1e7579f608c614fd27a1c1f9ce27ec52a6674d24e400b0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.plot.PiePlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Chart1
### Patch Diff Hash-SHA-256:

982ef90fb3b0b1743e3bd4095227f29fd191d493ab8f2b3dbd9cbd0f12111bdb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) == ((rowCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Chart1
### Patch Diff Hash-SHA-256:

5133349c6d9597c91da1414359cfc989d2e72ce64df5f02c5c3d11a68ae1362a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.axis.SubCategoryAxis) && (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Chart1
### Patch Diff Hash-SHA-256:

333559fb4c4b10c03ae0ec4feecef0468365dab9aff009d753d341a7f542502e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.plot.Marker) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Chart1
### Patch Diff Hash-SHA-256:

9d6e6ac9d3d3d8bba7740df56c9d53b9602cd971074c0872e561f5c5df3f6501

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.labels.StandardXYItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Chart1
### Patch Diff Hash-SHA-256:

9f8ed399f0ac3bfda01831d0d19fc3d1ec916a7550799b8ccdb4f847e821794b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.data.time.Second) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Chart1
### Patch Diff Hash-SHA-256:

b01dcfc7caa14f222e2a7d7e887aa42ee5667674539fe774ef8c5c2ea3746659

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.data.statistics.DefaultStatisticalCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Chart1
### Patch Diff Hash-SHA-256:

598047ac7f7029fd70ba021626bcae0d9975babb66ca9295bea9a0a396d06bc4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.plot.PolarPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Chart1
### Patch Diff Hash-SHA-256:

7b1d3f64ef19d29be56b91744dabfec78c06d6e61a9dd9f3e9500dbc3c9e6594

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.LegendItemCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Chart1
### Patch Diff Hash-SHA-256:

f1eebddc3b203b1ee142d67a656bacb9a0041e4f8d6a9e9e00f3b32f479d69a5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.axis.MarkerAxisBand) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Chart1
### Patch Diff Hash-SHA-256:

9bd6c56d1acbfc7b6efd30f66912e8e7213cedd263ebe50e043ed6730acf5386

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.plot.dial.ArcDialFrame) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Chart1
### Patch Diff Hash-SHA-256:

cfa2f4abf43e13bc88af3cc012f9cedb830f262d77a6d6cef4a70afe610c4db4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((getLegendItemURLGenerator()) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Chart1
### Patch Diff Hash-SHA-256:

548246899b7908bbe36ca92913b1003b707e1681f1bd930eb8302d405d58bae6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.labels.CustomXYToolTipGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Chart1
### Patch Diff Hash-SHA-256:

ed529a6dc6a0e049c4f53d5a07d9e069cec1793b116a0f168665d5c3d8b53168

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.renderer.xy.XYBubbleRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Chart1
### Patch Diff Hash-SHA-256:

a32a4708da0aa8fe9f609b59d81be2c614cd16589826446da5b74d8a0e121f1f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.labels.StandardXYToolTipGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Chart1
### Patch Diff Hash-SHA-256:

63929d9477ae9a8a3f458d437971faf1d7d0d27857b9c2e0501c072f1e9bef5c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.data.time.ohlc.OHLCSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Chart1
### Patch Diff Hash-SHA-256:

147bcb312c4d575d56598f0fdea781eee6c1e3e7702a66da69c974e8683dfbf7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (false) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Chart1
### Patch Diff Hash-SHA-256:

0010f959ad0f2928b1138caff83d99b52ac492728e2426e82addd4b280b27595

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.axis.SegmentedTimeline) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Chart1
### Patch Diff Hash-SHA-256:

ec83dbef45cb6418184cabd07de0f8e35bd2609a484d7c10851c3cb2ddb5198a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof java.util.Date) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Chart1
### Patch Diff Hash-SHA-256:

34d08f48dc0148414dfe24a055f00ce1b6ce5d5db97fb548ef525342ea164d54

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.labels.AbstractPieItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Chart1
### Patch Diff Hash-SHA-256:

1d208393cc042a1029a6184ee6a39a861d34216dd162fc4b1440193227bda1a6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.axis.CategoryAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Chart1
### Patch Diff Hash-SHA-256:

7d0fffff58b2ef85d472c14e5e95f9a8c4ba256bcf17d675f57a457cbf52934e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((urlGeneratorList) instanceof org.jfree.data.general.KeyedValueDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Chart1
### Patch Diff Hash-SHA-256:

0045075ff513773f7bde931ad5a0e37742767185ee941f3182bcdb9114cef82c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) > 2) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Chart1
### Patch Diff Hash-SHA-256:

74f523f35ae4f7cbe7ec93aa30636018297af950588989551ad509fb97af787d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Chart1
### Patch Diff Hash-SHA-256:

da42fdee46869e2ce999781882b729a6759048e98244b170d5c1f0c2c57bf2ef

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (foregroundAnnotations.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Chart1
### Patch Diff Hash-SHA-256:

d89a27d845c759b6a30fe5ac4ea73cf3700452243d564b441fa1eba63d550110

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE)) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.needle.WindNeedle)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Chart1
### Patch Diff Hash-SHA-256:

b45976c0246a70ced2dcf95c5407f2f56c9680afb7327d410079e74e946378d2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Chart1
### Patch Diff Hash-SHA-256:

f520211ff755dd21890e780d73aa618c661d79c87f317461bc373bb551180d9e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.statistics.DefaultStatisticalCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Chart1
### Patch Diff Hash-SHA-256:

bd94d43de88954b2ac6759aee739284c17bab557587e1d1fec995a84bd05d3e5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.util.RectangleInsets) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Chart1
### Patch Diff Hash-SHA-256:

a0cd004fa0bc58ca0062cc1eda2f4fa2c679ab190c4cffb019485a066de9bdd5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.axis.DateTickUnit) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Chart1
### Patch Diff Hash-SHA-256:

a8d1b821b80d74e6b818037cd3f3cf16f461d3b2308b996b88ecd5ceb2c8dab5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.block.LineBorder) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Chart1
### Patch Diff Hash-SHA-256:

ace3a9db28e2781f1c4b156d9f33f0a03f90e64e84c2f9d34f9ac73d2c60544b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == 2) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Chart1
### Patch Diff Hash-SHA-256:

cd429c1ee2eef90a7e2010145569992699fdd6145d2a6ee0df8231ea104d4b48

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) == 1) && ((org.jfree.chart.renderer.AbstractRenderer.ZERO) != null)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Chart1
### Patch Diff Hash-SHA-256:

210cce2a0ca400e4f5329d3b93a38ef94de274a0153f872d99f58a04caf67576

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) < 0) || ((columnCount) > 2)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Chart1
### Patch Diff Hash-SHA-256:

9872a1f8d418b2d2d6ef8621f4832dc0d5ca6fe94ff9451aa30d75725726fb00

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.plot.MeterPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Chart1
### Patch Diff Hash-SHA-256:

8d5d433d69d90c85c9d1bc55254703fb66da0e0e99b3d66a019fb82228f6ff47

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) >= (columnCount)) && ((rowCount) < (columnCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Chart1
### Patch Diff Hash-SHA-256:

f8a2b651e7fa94bbfb94cb0fbd8ede1dbb2a209154b687498fa4d5f4b4d783ed

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.entity.JFreeChartEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Chart1
### Patch Diff Hash-SHA-256:

57cc8b092640f7d2386b95625d1717862adc71d74e086591110d878aa92885b0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.plot.PieLabelRecord) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Chart1
### Patch Diff Hash-SHA-256:

a3e912d4b02351930fb20561ce1043697dd7dbd615335e28240bb3e402990eac

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.entity.ChartEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Chart1
### Patch Diff Hash-SHA-256:

7086a8227dac16bc9cb8caa9d5e667a413d4094bee44b109a07adb2319b2c55e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.util.ShapeList) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Chart1
### Patch Diff Hash-SHA-256:

a70e5c752da97b8af2669ac62b73716ab37cc682c9bec4a49879fd249b78f5b5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.entity.JFreeChartEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Chart1
### Patch Diff Hash-SHA-256:

e19170165069002f80be7120f3a675f142d9a22fcda76309ecd9b4f96cf89829

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.data.xy.XYDataItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Chart1
### Patch Diff Hash-SHA-256:

9521defba811057d79626706c7e0c45368b9ed785c50720ae54c25ee84250733

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index > (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Chart1
### Patch Diff Hash-SHA-256:

eb6d571a961a16881a401e44b24243ff2c03505fc481042c20521c99dda5743a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) > 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Chart1
### Patch Diff Hash-SHA-256:

6a92834d1852aa35059514093671d6c3983958883d0c7dd0391d12b8baa6edb0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((itemLabelGeneratorList) instanceof org.jfree.chart.block.EntityBlockParams) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Chart1
### Patch Diff Hash-SHA-256:

b12117303174629ca5944b949f4848ac7448b849736f32b8bb4bd1b59c5fe9cb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < ((rowCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Chart1
### Patch Diff Hash-SHA-256:

d121846f6a584a78743b1ea88383edeab76ee23eaa5c5f938b85a61ece5f3ded

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Chart1
### Patch Diff Hash-SHA-256:

09070ac04841578e61cb43062884dfd988af3a4242e1a5a4a86cd9c358f8bb72

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) <= (index - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Chart1
### Patch Diff Hash-SHA-256:

badf34a94b0acbaaf9e76fb34ea3c335c851323175aaa82b992e6a16094d2f1c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.needle.LineNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Chart1
### Patch Diff Hash-SHA-256:

b3aa62cbd85036488a38063da0d2a45c4f1fc1c525fe3339c80dcbe513ea416e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.needle.MeterNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Chart1
### Patch Diff Hash-SHA-256:

47fe9fb5223d760ce22f9641910f440705800d4ec852f5c07dae22d948215442

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Chart1
### Patch Diff Hash-SHA-256:

65cd50be401fe62ce8f6b35d77c033b0dc09ee388accf554fe5aaa5f4307a822

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.axis.SubCategoryAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Chart1
### Patch Diff Hash-SHA-256:

e8874f99f17ccd13ff7b168493dc3bf78a12b8c9e8a323c23b95f0ebd44eb3ff

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.entity.XYItemEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Chart1
### Patch Diff Hash-SHA-256:

250943c43f7869bc2ed0c0c69e98ce3e3188b9ec644279d57a82039676411866

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.Year) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Chart1
### Patch Diff Hash-SHA-256:

f4b00dce227d8eb1341c1fc49c706ca5b13cffdb961620247e23a92c17fe6b01

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.data.time.Hour) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Chart1
### Patch Diff Hash-SHA-256:

1821a0935a265589fa613d879332448f5982d0852725e918e450ca702bdbb042

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.labels.StandardCrosshairLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Chart1
### Patch Diff Hash-SHA-256:

4ae8e1b2bced8210939fba20779eca7568f76bb675830b2d5c72c90e9ab33c74

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.plot.CompassPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Chart1
### Patch Diff Hash-SHA-256:

7ae4550259c8aa661a444f57d572580a60df426d5444383b7f7203504b15ff1f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (isItemLabelVisible(index, rowCount, false)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Chart1
### Patch Diff Hash-SHA-256:

d5c41f2ab772534bf4898987239bb9c061736816c26ea99e97ce7865619186c7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.data.time.TimeSeriesDataItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Chart1
### Patch Diff Hash-SHA-256:

11ee8d75dafe6f380865c15ec8ee2417f9d1838cc9c447949eb4a29ff2a6a9c2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index > 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Chart1
### Patch Diff Hash-SHA-256:

e853360b86a3929730ea1249de82c9a626b42a5df3a0baaaa5749725e68fce57

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(baseToolTipGenerator)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Chart1
### Patch Diff Hash-SHA-256:

b69846db3fe4579c534726060be8dee592e9e664c54f74e05c00d32d6268a968

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.data.function.NormalDistributionFunction2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Chart1
### Patch Diff Hash-SHA-256:

028d577988d98ff93d9d86de4f4c2ec5315b9c7b8db85c71df89f0f3ea3eb6d1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.axis.DateTick) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Chart1
### Patch Diff Hash-SHA-256:

824c1195ec46b157a863cbed92a5f49ce925fd584c3e7947ca4a17500bbf323d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == ((getColumnCount()) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Chart1
### Patch Diff Hash-SHA-256:

d615a590011c51db125e261a1b1fe5e408a6744264fabd8bcca3b219838a4a38

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((baseItemLabelGenerator) != null) && (isItemLabelVisible(columnCount, columnCount, false))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Chart1
### Patch Diff Hash-SHA-256:

2cb7269be0f33c7ec501154d16798899d37889e839d277ac23865898ba78031d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (backgroundAnnotations.contains(plot)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Chart1
### Patch Diff Hash-SHA-256:

d6cac574e901e8174d767da66d9aabdd35e98d9685a8692615e70d60b6e10b65

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.axis.LogAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Chart1
### Patch Diff Hash-SHA-256:

c26f3385f808aba3b5ca3bd4f88b47280ff97f6d014f364ed0280ae99af676c9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.time.Hour) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Chart1
### Patch Diff Hash-SHA-256:

f48353343af959feecf3364fd2aa3f53d7093edd8fb93ace841c7f47c29ee346

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.plot.XYPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Chart1
### Patch Diff Hash-SHA-256:

49441d27dbe3ff4f0f9d8b2dc5c62450913371a70b5ff58d70eff5065cc8315b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index % 2) == 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Chart1
### Patch Diff Hash-SHA-256:

a7855c1da56a382fab52f85ea15ab5064bacb49d3d899375df44d7063757e3ba

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.data.xy.XYInterval) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Chart1
### Patch Diff Hash-SHA-256:

7736affe9967db88598a6a12b8c7ce1ed866c86c7f9cfc11ccb3c24931d714fc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.category.IntervalCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Chart1
### Patch Diff Hash-SHA-256:

416e2c1e30ae8c4107b8ea4ecf31ee76a6ffdaafe66e2d364d86d1ae2af5ca6a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < (getRowCount())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Chart1
### Patch Diff Hash-SHA-256:

3f690e15d3d999eaa4483b3100f14997e963ff750a1e2e3baee0b97f6f6c2488

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Chart1
### Patch Diff Hash-SHA-256:

bb17f2cf2ad14ddf8c4e5859dc03661c23e8894264656b8fe31507197d0824fd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) == 0) && ((rowCount) > 0)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Chart1
### Patch Diff Hash-SHA-256:

90568b01330f472960ad3f0553f3310a068bdcaaf93625aebc51c5c73373bac2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.renderer.xy.StandardXYBarPainter) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Chart1
### Patch Diff Hash-SHA-256:

833c6a16534291634e6fb5310a5b867e93164a028243ff88b6529076d9c17f7d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.labels.SymbolicXYItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Chart1
### Patch Diff Hash-SHA-256:

8daa6b6166ff23515e39e18ea34b6118b7752e9030bdeeece270dd613dc24a06

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.util.PaintUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Chart1
### Patch Diff Hash-SHA-256:

80b396eeaeb6e5afffef2a878d884a455d19e487b8c7e27045004c88d76b7095

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.data.time.SerialDate) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Chart1
### Patch Diff Hash-SHA-256:

99669eebd696a6542e26e31092b72cc3044b55a3b3df06d4713f6c973c602255

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.statistics.MultiValueCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Chart1
### Patch Diff Hash-SHA-256:

5888158916a602830a97e73ce36b8938e0414583b3023c876b35491037dfd10a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.renderer.category.BarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Chart1
### Patch Diff Hash-SHA-256:

d1d60ab16cf153c010f929bc7eab2943121bbbe8d15c2f1acb5d0bfe249dc94d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Chart1
### Patch Diff Hash-SHA-256:

406a339f76c1d0d628397a9d0f4fbfe13b3308c66e30d53033dff0dbe4bc0491

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.statistics.BoxAndWhiskerCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Chart1
### Patch Diff Hash-SHA-256:

3c1e89bdf81a1fab86afd82482ba4af957000156cb07d2baaf30b0bd818a83b5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.entity.XYAnnotationEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Chart1
### Patch Diff Hash-SHA-256:

ac64dc0e6e6a667e4304d61b5e75e5fcd0c5ba1d3a31932a1a808d1c8996599e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Chart1
### Patch Diff Hash-SHA-256:

7637b6d945209efc1b7d20e9277af66e5a921fb67a6e701d4223a99123820499

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Chart1
### Patch Diff Hash-SHA-256:

6bdf53ef401fde666b83d6e60b8cb9982bfb4fb16fe4b6f29e30b7fc4d3e53aa

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.renderer.xy.XYAreaRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Chart1
### Patch Diff Hash-SHA-256:

d47c02c7d22cd41711af2d3ca599dc315123cae56c73148a240fe630407ba8c4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.data.statistics.DefaultBoxAndWhiskerCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Chart1
### Patch Diff Hash-SHA-256:

d8213bf03c230b2b972df27c763bfea5fa49f76223ef60337f333f7a255a3b27

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (backgroundAnnotations.contains(org.jfree.chart.renderer.AbstractRenderer.ZERO)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Chart1
### Patch Diff Hash-SHA-256:

f918d51f9e0b19ece517c70e153fa38cfa1172d25d950552322c953c4b384b8c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Chart1
### Patch Diff Hash-SHA-256:

21b45ad11a4b44824a4debc00042ad59cc74d6b757098fb959443a7141f45366

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) == (backgroundAnnotations)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Chart1
### Patch Diff Hash-SHA-256:

2ffdbe08e822ed5878cc672f6397e0bfd18d9dc7d585629b040eb03a15fe702b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index > (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Chart1
### Patch Diff Hash-SHA-256:

5242bc5b4a10ee86e72cb61607c7f175702d654db96ed9edfd6ca4fa988ce062

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.renderer.category.BarRenderer3D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Chart1
### Patch Diff Hash-SHA-256:

bb73587bd885ddc74a0be241d8d0d55e456b4dec4e944dc013e48eb7e426351f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.axis.SegmentedTimeline.Segment) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Chart1
### Patch Diff Hash-SHA-256:

5bff3192f54ab2043708bc2421f95334bda436dc3b22a684b178765ffc687b42

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) > 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Chart1
### Patch Diff Hash-SHA-256:

6a1cda82f9b5be0b585924d1b18efc29ea68f6f5a1ffea1d557b830fb88dbea0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.data.xy.DefaultWindDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Chart1
### Patch Diff Hash-SHA-256:

679165aeab269484859e0c0260eab023f8b9ed76978695b70c46f26c68982835

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.renderer.category.StackedBarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Chart1
### Patch Diff Hash-SHA-256:

7c7859dfa156f5fe6a970cdb30be6460bd51f202c097e64deb6ac1fd38bb74a3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof java.awt.GradientPaint) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof java.awt.GradientPaint)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Chart1
### Patch Diff Hash-SHA-256:

01c38f6f5149e273e0960f9e854d46d44325a4379e474a499c6b24992c906d3e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.data.statistics.DefaultStatisticalCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Chart1
### Patch Diff Hash-SHA-256:

e5c83535b39471839cc202f827af66e07c20677945d2febeaf96859412266396

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.time.Day) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Chart1
### Patch Diff Hash-SHA-256:

d466a7306aeac3fdc5c9c8cae9828253ddca6fec4a379da0bc93eaf9b1ffa2cf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > 2) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Chart1
### Patch Diff Hash-SHA-256:

262c44a2386aa095b89282141efe5ebb40584ebe6ebc4c1e58aab87262dc2515

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.util.StrokeList) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Chart1
### Patch Diff Hash-SHA-256:

f90abde1b3f2e0515864d0b57b5f6a2b9af0020cb89ac6dc6787293b67def131

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index > index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Chart1
### Patch Diff Hash-SHA-256:

b2b3be5f21959a87832cc35c02b5cf1c6a5ec752c58fe18d505f35745e4ed4f0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index | (columnCount)) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Chart1
### Patch Diff Hash-SHA-256:

7699ac0410af3df766f147ca5390cc15fffc243b7cad2e39018728dc450bf2fb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.Polygon) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Chart1
### Patch Diff Hash-SHA-256:

bfe1dc36eccbf69f56c1d4f5066b0206ffc89311305764df24d6a4c2437e9108

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.data.time.Week) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Chart1
### Patch Diff Hash-SHA-256:

88e7b24bdee046ad932363931c5267aab1ea53807cb7fc72ad29389f4c09140e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index == (-1)) && ((columnCount) < index)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Chart1
### Patch Diff Hash-SHA-256:

4a214135684aa3de8f39609f89b5b6c010f616bc4533b95524f1585808819081

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.ZERO.doubleValue()) > (org.jfree.chart.renderer.AbstractRenderer.ZERO.doubleValue())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Chart1
### Patch Diff Hash-SHA-256:

452b3e808100f90e5b68a7e48002df4aa02177af3377962a3a07df52c91b51e8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Chart1
### Patch Diff Hash-SHA-256:

b0506613e57f76b2af20a03f48d0180783d416463536fcd14cfac18d91c4bc30

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.DefaultKeyedValue) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Chart1
### Patch Diff Hash-SHA-256:

4287e94ca0b80e71b3f244f8be815316f873f18dc2b8dfba9651525da5a0d361

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(foregroundAnnotations)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Chart1
### Patch Diff Hash-SHA-256:

d14c8dd226228bcb01e47ed5217087e2c904d5300b67fd2336f6ac3b471828c4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) > (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Chart1
### Patch Diff Hash-SHA-256:

08269fe7d7b4783d180bcc2287f9915dd275e14f6db454b5e4b20100a4f95e86

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.data.xy.MatrixSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Chart1
### Patch Diff Hash-SHA-256:

44ac1e4ea183ad4d18d12fa4f41a607eb72f2961bd72d8ca02633a97c8af6570

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.LegendItemCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Chart1
### Patch Diff Hash-SHA-256:

061a6418fbf3311a19e57a558084f2115f763a452f5bacd045812908dec4069c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.renderer.category.LevelRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Chart1
### Patch Diff Hash-SHA-256:

0b26e37d7906ba5740ec76a3bc9fd8b8467a603f32797965794f345f18912f30

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.data.time.TimeSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Chart1
### Patch Diff Hash-SHA-256:

53fd93bf149cfbf8979f90fcd5b67ad20d9f30b11250bb06d5c4346a92e370b2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (plot.isRangePannable()) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Chart1
### Patch Diff Hash-SHA-256:

c8bdffc00ac2add9dbf1395017dd2928483faaaf1a356984b319e9386ba8f3be

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (-1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Chart1
### Patch Diff Hash-SHA-256:

7f673fd4d0283d1e3cb44e9fcbd50894eb94b1e00bf9cfece8188f3200d1395b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.labels.HighLowItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Chart1
### Patch Diff Hash-SHA-256:

4fbf839637054bd68793b57d06847b62b2a3f77d621f1673044f4a74a9d2ed9d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.plot.dial.DialCap) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Chart1
### Patch Diff Hash-SHA-256:

5454ab734199617312af6e03fdca16ace2052f8e65a81b6aa3f7204d08a29deb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((foregroundAnnotations) != null) && ((foregroundAnnotations.size()) > 0)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Chart1
### Patch Diff Hash-SHA-256:

b68699de1866180d0007725604750673dc3c8e0c83ae34751a0437defa7ac5c7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.data.gantt.SlidingGanttCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Chart1
### Patch Diff Hash-SHA-256:

e02d9ffcba0dd9d3f7954fd4578e12d85caab3bf1d790307b598a2b33545c088

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.axis.QuarterDateFormat) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Chart1
### Patch Diff Hash-SHA-256:

40602d5cc23a450c5ba07229393ddf4599ff56c96326c30dabf139cee9b33b52

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.block.AbstractBlock) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Chart1
### Patch Diff Hash-SHA-256:

79744cc0351e81da1ac488862fed0cf821743013cfa181885a25b8aeaad2e50a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.entity.XYAnnotationEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Chart1
### Patch Diff Hash-SHA-256:

127f79b50874c4addeb3e664b2f05e98eceda5667e090cd2acbd097c546e2bbf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.labels.AbstractXYItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Chart1
### Patch Diff Hash-SHA-256:

fa0c2bdf0722bca8903ac7c1c4c762efb19c52ae2aa455fe8230e9998d1f1874

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.gantt.GanttCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Chart1
### Patch Diff Hash-SHA-256:

a967445c3f93c797294fd42cb621b4df14a0fa4bf551a5da2c829c3decfe816c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.util.LogFormat) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Chart1
### Patch Diff Hash-SHA-256:

488e7e233e4acfc169cf12596c685020ba50c8cc6df9d5e8bd7427d5f0553108

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.labels.StandardCategoryToolTipGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Chart1
### Patch Diff Hash-SHA-256:

c421300ea03422fa11d4f1182145c2efb3a2886d4f13218e3ca71b54c0f20f1e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.block.EntityBlockResult) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Chart1
### Patch Diff Hash-SHA-256:

68e2f771a828a40c5d45c81b8a0e1a12fbae97b80cfd54dbbbbc3e679a338bdc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(getItemVisible(rowCount, columnCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Chart1
### Patch Diff Hash-SHA-256:

12c62551ce7b536c0877715d4fc6a228ca57fca9dad77fea8b200f25532f389e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT.isItalic()) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Chart1
### Patch Diff Hash-SHA-256:

92bc09c7db8223b6d2d1f50548e66f63b91def950d28e23b4019b078b27caa59

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.plot.PlotRenderingInfo) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Chart1
### Patch Diff Hash-SHA-256:

6c113b8ab3ea768602e1f866ac16cf5a9b09e5e79a5c598b54f0f15f94b52696

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) > (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Chart1
### Patch Diff Hash-SHA-256:

537aecbb3096e064d9d477c69d0ec60c1b56ac07ec36f1b6eab397404f41e14e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Chart1
### Patch Diff Hash-SHA-256:

a82364eb22d57531ef4482c1653a52b2bd58ef74ea7e23569cb93f473dfd1065

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.axis.Tick) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Chart1
### Patch Diff Hash-SHA-256:

db49fb74d3faa97b09f42caca69f1a8286abf7ded379a3f13ed12c7c21ed25fb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.plot.MeterInterval) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Chart1
### Patch Diff Hash-SHA-256:

0e9540a4531001a242a5ca85f29f16f0f6d96eebea22bd0ce763a507523a1615

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.labels.CustomXYToolTipGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Chart1
### Patch Diff Hash-SHA-256:

f5926906d8608c0615ff90848e19629e31f39a797bca64f8d146faffcf9e09f9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.time.TimePeriodValues) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Chart1
### Patch Diff Hash-SHA-256:

b5f35128758d1c559f86052d98ceca53a1e597e7df023cc3d18e980a9944797c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.axis.PeriodAxisLabelInfo) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Chart1
### Patch Diff Hash-SHA-256:

7ba602c1233a434402b34780709e8321f1ee0e474f692efb453712208c524db2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.data.time.ohlc.OHLC) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Chart1
### Patch Diff Hash-SHA-256:

de9eee9735d53448fd938e5098fe28e791b1b1839d9c71c40b4e6836b8a8ac84

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.xy.XIntervalSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Chart1
### Patch Diff Hash-SHA-256:

09fb3474a728f7305af5145dfa7cce3a73333a0d79f744db4a1ea246a90baf52

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (foregroundAnnotations.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Chart1
### Patch Diff Hash-SHA-256:

d15de26a99c9b49274218cd05d456fbaae194c96e06722d1d47888d5d57fb876

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.renderer.xy.XYSplineRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Chart1
### Patch Diff Hash-SHA-256:

82c922bbbf3bd2397f0a004ea9e714e6fc6d35979f96eee6276f841a5d2acf75

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.plot.ValueMarker) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Chart1
### Patch Diff Hash-SHA-256:

07dfb581f3f728009d029fa65c1dd9a3c637bebca8d62f470c4373e473078622

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.renderer.category.StatisticalLineAndShapeRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Chart1
### Patch Diff Hash-SHA-256:

f0eccb252b51eddb9d58b3d6600e7d134e138365c6602f879043e16b5bad330e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == (-1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Chart1
### Patch Diff Hash-SHA-256:

f77a2bd3f042f9d1bf21b158c7c375b04652adece611be0d1013064dd581259d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) == (-1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Chart1
### Patch Diff Hash-SHA-256:

809482fa2387e1f1198f3df277d21d3352240d44459c482663de4b326fd7d96d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.renderer.xy.XYAreaRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Chart1
### Patch Diff Hash-SHA-256:

5c3a479b7fecc509b16a690bd2e73adbee1ff63ca77b51a4ce19945d609472f9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) != null) && ((legendItemURLGenerator) != null)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Chart1
### Patch Diff Hash-SHA-256:

6caab4b7b22e3a1e9a95b1b25c6f774981db8e24bfd7e9205511f2960001464a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index > 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Chart1
### Patch Diff Hash-SHA-256:

323307a94c438f6ad84feb0e4755a693b007b989e80e206f3f0ba73de35110d3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (getRowCount())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Chart1
### Patch Diff Hash-SHA-256:

851ccb55a8b3cbb8c34193f49965633553ba5652f931d399b9ab9323dda28c89

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Chart1
### Patch Diff Hash-SHA-256:

7d517c7e502b03ba89284e0d3f49bd9f301ef72f75c9c9674faf3f44aa519046

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.category.CategoryRangeInfo) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Chart1
### Patch Diff Hash-SHA-256:

1cb0dca202b21cf3cae749df7e12da2b277c60fd6e06a505fea8d84a09bf028d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.DefaultKeyedValue) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Chart1
### Patch Diff Hash-SHA-256:

e1a712ae78124badd6910bcdb2f51c4b5e6795f9adca3f5fa7790612e3a81f1c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(result)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Chart1
### Patch Diff Hash-SHA-256:

502164ec7343c587f67b0d03c6e57dac2ed258e53e7e6bfb00dfcd3a30332c39

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.data.gantt.SlidingGanttCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Chart1
### Patch Diff Hash-SHA-256:

5d8dbcbd7f83b3a19a310a7a4344cced6b0ef8dc9fed8625508c4e7d4962fc02

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.plot.PieLabelRecord) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Chart1
### Patch Diff Hash-SHA-256:

b7aedd881c84cf36cff63dda0de5559c51b152cad37a374e5b7ed70ded01b2e7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.xy.XIntervalSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Chart1
### Patch Diff Hash-SHA-256:

7c42811c2e36c09c41db6f9920bc36bbb55cfec31b2d2c6f88827200137b2847

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.ZERO) == null) && ((org.jfree.chart.renderer.AbstractRenderer.ZERO) == null)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Chart1
### Patch Diff Hash-SHA-256:

aae46251e4e09435741b23e8e5e3b8dab5b673adb023d27113e7026e1b28fb6f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.renderer.xy.XYBubbleRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Chart1
### Patch Diff Hash-SHA-256:

fab41a7a462b70d1dbbf47255f84107b0a3b525f419f064d0422eeea25cec733

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.xy.XYSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Chart1
### Patch Diff Hash-SHA-256:

1ee0cab430924da9edf8339d286d94913c27f67344faf9176e71c0d02941c0a3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Chart1
### Patch Diff Hash-SHA-256:

673d459b2360cf547e466eca2d37f10e5c07809ff1f59d7e1e818f458d688c6a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) == 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Chart1
### Patch Diff Hash-SHA-256:

ad699fc7ed9be77a90a706074f36ec2a52a557cdbdbd60b0cff647da18b94cee

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.statistics.HistogramType) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Chart1
### Patch Diff Hash-SHA-256:

7789d80eea0154c0b2c45312f1b24774078bec8dae044b2b550c12e168cb857c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.KeyedObjects) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Chart1
### Patch Diff Hash-SHA-256:

0c9c68272d7cced710766f466f70f7af0917e344566ac4981db2a8988febfa1f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.ZERO.doubleValue()) < (org.jfree.chart.renderer.AbstractRenderer.ZERO.doubleValue())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Chart1
### Patch Diff Hash-SHA-256:

e667688c2d0ca892a8a341c71a34c54f7e0935c38891178ca1a2acc93f844b5b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Chart1
### Patch Diff Hash-SHA-256:

89a0f2108b06ee5b621f321b490bc3a80764042f3feeb987abd5882a03de1aed

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) > index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Chart1
### Patch Diff Hash-SHA-256:

76d79d8b677f781240cc7d6e5632621f440d359ee58dcae16728746ab06973c9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.renderer.xy.XYErrorRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Chart1
### Patch Diff Hash-SHA-256:

e0400cea6b1e9e751ce2429e63ed8b6cc34f74b0a1a5949982ce68f77955d607

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.plot.MeterInterval) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Chart1
### Patch Diff Hash-SHA-256:

fc8e396dc3ba44e076d52a1e454e196198843a1d38a7f72d8a0924a5c9d88834

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == 2) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Chart1
### Patch Diff Hash-SHA-256:

7753ff208bd11f04d3333d803d28599ad9d8eac64510966aeb3da0861dc2e6a5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.gantt.SlidingGanttCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Chart1
### Patch Diff Hash-SHA-256:

954bc96371e722e765d4790fe7fd6454775cfcc0b5a6b96304362a24626e125b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.text.TextLine) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Chart1
### Patch Diff Hash-SHA-256:

b5796fdcdd896d1d940fe389e0f8b0f5b1e9613669563c02f39585e6e8f9569b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.labels.BubbleXYItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Chart1
### Patch Diff Hash-SHA-256:

bc442b74aafc9229fb049c801fa275bcbbf8c4ca1229c6132257721220f1ef00

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((itemLabelGeneratorList) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Chart1
### Patch Diff Hash-SHA-256:

2715f77957abe80edf416294d4bc56e668eb9da6ae6c17875d36e1d41f5b57a8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.time.Second) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Chart1
### Patch Diff Hash-SHA-256:

60d275c5e33d812e9c6e59df65b50136ebb076550c838a8e0ef96a1a2aa351a8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(itemLabelGeneratorList)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Chart1
### Patch Diff Hash-SHA-256:

fc557212ae29919874c647e8904c01cc67203907804084fc5b7b4c54a82cb4d3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.xy.IntervalXYDelegate) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Chart1
### Patch Diff Hash-SHA-256:

6e7c2a8b1cf98db68f3645aad28c2442ce81412d72c2251bb5d1556883a1d01a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.renderer.category.GradientBarPainter) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Chart1
### Patch Diff Hash-SHA-256:

5f0246be3bdf95c3e7fdddc00e6f5e9a5efd27877dd1be0978747e53c51516cf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.data.time.SerialDate.isValidMonthCode(index)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Chart1
### Patch Diff Hash-SHA-256:

b8c24f6ff5d340c744e4d76e6b5566d6e02c8662950ec5332661e483a17f1595

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.needle.ShipNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Chart1
### Patch Diff Hash-SHA-256:

4a0385fb0e52dca7cb8abbfc316a7d5fb62da004f7419d58d13daff1ff5fc6de

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.renderer.category.WaterfallBarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Chart1
### Patch Diff Hash-SHA-256:

f24c99825c10364785d7e35de4d33cd2f1d69fb4f3680ef64d6066e84e22c9d0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.labels.StandardXYToolTipGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Chart1
### Patch Diff Hash-SHA-256:

c63617ac11faeab846bd0e5b4ed82d5d95d8e591266619b27a7c84e694036d22

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((itemLabelGeneratorList) instanceof org.jfree.data.category.CategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Chart1
### Patch Diff Hash-SHA-256:

a27e2603122c163981285eaab167f4f141560e43770efaaeefa08640f6ed7744

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.LegendItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Chart1
### Patch Diff Hash-SHA-256:

ad88085c7d8dc24b298320e09f0a269224808f04a95bc00f33e594445c753fc1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (0 < (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Chart1
### Patch Diff Hash-SHA-256:

5fc756a6462a406cfa1466701a9146ae5fe62e05c8ff6a07829bb5b462f3c8a2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.urls.CustomPieURLGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Chart1
### Patch Diff Hash-SHA-256:

51c853c17fe1f0ab2fe7ed990a2ccb4fc0e5946ea24159dd542ca7e93c1f3568

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.plot.RingPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Chart1
### Patch Diff Hash-SHA-256:

cf5b57358f7fe18c81a89b04f376daa4198ceb571a88078d0fc3d28788ec129a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.data.time.Month) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Chart1
### Patch Diff Hash-SHA-256:

11bf17e9e4fe7590564fa8505f19a5ecca5bd9d8edc66e71910e1c00416be8dc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.panel.CrosshairOverlay) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Chart1
### Patch Diff Hash-SHA-256:

204005a7a61e7f7bfa791bdddd0a6f7ff74cb81c11c02fae4d33800505350561

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) > (columnCount)) && ((columnCount) <= (columnCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Chart1
### Patch Diff Hash-SHA-256:

50553c628e1caf35ea2448020bbedd4ff183be94a5d70d4a43288b1b71965019

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.data.pie.PieDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Chart1
### Patch Diff Hash-SHA-256:

db80799db151b6f2fe77ca37a86574173a7199ec538844656be0b7238939191c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.axis.TickUnits) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Chart1
### Patch Diff Hash-SHA-256:

ba5782c7c355875b524c83e66ad963718d278d673bc6c8e4fc0257f5c756dc2b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.statistics.DefaultBoxAndWhiskerXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Chart1
### Patch Diff Hash-SHA-256:

c88835cc31ffa833eaf631a1fc2731bc3e243517349e0e3d8aed9ecb2ebac4e4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.needle.PinNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Chart1
### Patch Diff Hash-SHA-256:

42968407bd6ef06f386e9d38eb2f5968784e8a42f276ac0b79ffcb1816273caa

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.renderer.category.AreaRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Chart1
### Patch Diff Hash-SHA-256:

39921e2b97ed936a0bdbcdef1e6258e31f60f3c6a6fcc56701e2293d2f085de5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.category.SlidingCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Chart1
### Patch Diff Hash-SHA-256:

4fe78babfad211a70601f3d9ed91dba4ac4184ccaade8c608a94a8a9c35737ac

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) % 2) == 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Chart1
### Patch Diff Hash-SHA-256:

307176ccd29eda4f57cbc3d0c8f52fe29b73952e859e79749ad9eb8faf95e684

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((baseToolTipGenerator) instanceof org.jfree.chart.axis.CategoryTick) && (super.equals(baseToolTipGenerator))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Chart1
### Patch Diff Hash-SHA-256:

a30b2d4aa70486ce4759b9cf30ea38660d43510e35175e62421d2c183f7a765c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.title.ImageTitle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Chart1
### Patch Diff Hash-SHA-256:

8c35819cce06813798085b5f8a1b05f493c3fd7a7057f61105cf879117c3ba38

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.plot.DefaultDrawingSupplier) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Chart1
### Patch Diff Hash-SHA-256:

10382f78b3a6e4a37a3413da3b0969f3b2404759862c85a0e15d92509c896a5b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.block.BlockContainer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Chart1
### Patch Diff Hash-SHA-256:

2e7690f33f11ff0b14d2f915fc013607c8aef1aa78f2cdf9a3d078010e529b86

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.renderer.xy.XYDifferenceRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Chart1
### Patch Diff Hash-SHA-256:

68aeffe9762b2188c1b29bef56e54d251d3ff6651b1f119931533a6f75a60f87

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.time.TimePeriodValues) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Chart1
### Patch Diff Hash-SHA-256:

8ed05228af23285287fa95cb375d4fc5d61d7bf73feb2f6c64f4c9d1668d5d22

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.entity.ChartEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Chart1
### Patch Diff Hash-SHA-256:

392ad061377e00562386461b0d18efe1027bf923589db62d14ed20a3aaf61dd3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.data.xy.OHLCDataItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Chart1
### Patch Diff Hash-SHA-256:

9b88b7520300f280e3c29e366b9c82a8edff0c9cb1c88eeb80144cbe400364a9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.renderer.xy.XYAreaRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Chart1
### Patch Diff Hash-SHA-256:

3eee11e084c97dbffa7ef5ea5ef4e5267c38c2b314c7ec2643472086b27798a9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.entity.CategoryItemEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Chart1
### Patch Diff Hash-SHA-256:

ccdb5755e482190947c85a41dc44dfb7b348f2b037e0d31bf1ac7bdcfaa0060a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) >= 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Chart1
### Patch Diff Hash-SHA-256:

5949ea4060596bb3b960ce636abce4834e82944b95f1bee47c27aa13c03a945e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((plot.getRenderer()) instanceof org.jfree.chart.Effect3D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Chart1
### Patch Diff Hash-SHA-256:

af997e8276c52049d3c724154f252f4448637ccd7d7de932c503c5a9139225b6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.util.ShapeList) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Chart1
### Patch Diff Hash-SHA-256:

5596a9e0659f78e549ccb977546a01e26201a76ce5622bc35bfa7004f7487ab3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.plot.dial.DialCap) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Chart1
### Patch Diff Hash-SHA-256:

6c55d9682568ba1b7233922b0316c6843508bb1534c6fe25dfc2927f2b095eb3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.data.general.DatasetUtilities.isEmptyOrNull(dataset)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Chart1
### Patch Diff Hash-SHA-256:

0c187d26112676d8ac7def5cf7653380cd2b7880fbd1f4a8c2c6767209decdb2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.title.CompositeTitle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Chart1
### Patch Diff Hash-SHA-256:

29a10eb49a8afb50971333d09bc657233ac4afa2ccf8f6304793df916fd2865d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.data.time.Week) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Chart1
### Patch Diff Hash-SHA-256:

525392e263fcfa20efb0b68137f20ab6c256ed19a8c66b353155089ef4b2581c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.xy.DefaultOHLCDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Chart1
### Patch Diff Hash-SHA-256:

81f0503f1a374ef95aaef7990235da8750bb6161823828173322209cecdd1bac

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index < (columnCount)) && ((rowCount) < index)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Chart1
### Patch Diff Hash-SHA-256:

c7ef16c14e83a770813df17fe55e8e186b3869d9b57c7c65acbbc1692ab1e970

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(baseURLGenerator)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Chart1
### Patch Diff Hash-SHA-256:

e114978e902e951b0c14210a3bf4ee3b733d7708ff3976be9dcaec28d285a15c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < ((dataset.getColumnCount()) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Chart1
### Patch Diff Hash-SHA-256:

d34a983254e3f76a25d34bddfa739fce07ecd1c323c972ae7605000427ab30a2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.data.gantt.XYTaskDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Chart1
### Patch Diff Hash-SHA-256:

ee0808805c6fb779343bb87df5166ccc66f2ac22bd92b8a61fcd1e5d21eebe21

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.GeneralPath) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Chart1
### Patch Diff Hash-SHA-256:

7e56c5a3b5a237fcaf9c5f2efd35b32a17c0d8c9cef2746896df631b6a812053

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(toolTipGeneratorList)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Chart1
### Patch Diff Hash-SHA-256:

918060471ecd56429c5f4ade04d98364803aa4689fb3f94e4e0824d7b2a470fc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.entity.PieSectionEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Chart1
### Patch Diff Hash-SHA-256:

a436238a65d0b04ab98ac36a6d729bfd5a1e8db58ba724a5fe7fb8ae904a05a4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.util.RectangleInsets) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Chart1
### Patch Diff Hash-SHA-256:

d9d693f8b5f2ebe51605adb80a6348b2f7b33755d1d12342992f629583a572e7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.labels.StandardPieSectionLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Chart1
### Patch Diff Hash-SHA-256:

64d88525f5d57138a2c0c2b0c36698c3a2f91c8562be4522b38d12e34ba5a53f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.labels.StandardXYSeriesLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Chart1
### Patch Diff Hash-SHA-256:

fc3f2e8d2ba8526910212f51b43c275ad731fea69e60b51c8058614b85611492

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(getItemVisible(index, columnCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Chart1
### Patch Diff Hash-SHA-256:

b3d694db561c44a7abeb78bd9b1d296d084af396fd5014a3977306dec267e066

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.category.DefaultIntervalCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Chart1
### Patch Diff Hash-SHA-256:

eaa26f02f1861a1e6ecc8002b3bad937da81a6f9c36a2495c1eb8a7b1b9ea114

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (backgroundAnnotations.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Chart1
### Patch Diff Hash-SHA-256:

8e91788ad89b1a74555bdbfc3ecbffff9d719c4c8319f1f5661d8c711dd1ebe8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.data.statistics.DefaultBoxAndWhiskerCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Chart1
### Patch Diff Hash-SHA-256:

f05cc975c8d9087052a358e854a56c12d68f6605a1751e285415314c140a06b3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > 360) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Chart1
### Patch Diff Hash-SHA-256:

994ea749cecfab48e1d7c466fc3b67a7f654b82586fa7a87fef14bee78e3b975

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.data.gantt.XYTaskDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Chart1
### Patch Diff Hash-SHA-256:

41a08bbb537054e7c3b44808a327334eb714e88a9419a3e5b6ebb3b1b1a6a6f4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index | index) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Chart1
### Patch Diff Hash-SHA-256:

847f3c7b8f825a2ad93a4290aae592b846fa7db43c107dcf1508e7d76b08f660

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.renderer.xy.XYLine3DRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Chart1
### Patch Diff Hash-SHA-256:

9da0ab20f9d8ad8a7c0ca043304dfc22a2828670ab1283a417991cac5affdee1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) % 2) == 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Chart1
### Patch Diff Hash-SHA-256:

5ed0fa668e0717f5c8b804c89696f327544a6b64a577de91322ed24f1415d710

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.annotations.XYLineAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Chart1
### Patch Diff Hash-SHA-256:

8351a07cc8f02c018c57304c9b5a9743dce2768be55adba9b18d54416bb2d451

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(isSeriesVisible(columnCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Chart1
### Patch Diff Hash-SHA-256:

11dea04978955e2092b00854ffd381a4bf66184358f7b9d9a0a70dc186d9b7cc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.renderer.xy.StackedXYAreaRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Chart1
### Patch Diff Hash-SHA-256:

72e683ad954e31be56c67765e3cc63778145beaad7d1f92a9f83a6f904ad4853

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.block.LineBorder) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Chart1
### Patch Diff Hash-SHA-256:

aaf218a6ed1f8d24b7b00626978d6b36676ef55632070b0ddf16ea08cf3151fe

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (index - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Chart1
### Patch Diff Hash-SHA-256:

80c6b64d9aa1f3da3823d1b1572a11b94faadcc782044370a2e8e914e8454eae

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.plot.CompassPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Chart1
### Patch Diff Hash-SHA-256:

4858309696a8dd41355383d87d2220305f4e3d8b72c9cee0e94687603fcb4a55

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.data.time.TimeSeriesDataItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Chart1
### Patch Diff Hash-SHA-256:

26c89ef52c4448a76a9fd56ac15c40cfec3c3678adc9daca74b565baa54f09de

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT.equals(result)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Chart1
### Patch Diff Hash-SHA-256:

907c787f7e783e8f2d859122ab028b182a0ade0e2c75436c77f2c37c2cc9655f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.ZERO)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Chart1
### Patch Diff Hash-SHA-256:

b088d9db20291684a507d4ccc8fde26cec0445e141f68f6001f701582db2c2ea

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index != (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Chart1
### Patch Diff Hash-SHA-256:

f13f25d63f128cbef4f9895ebf27e1912414237034dd5e7a057b1e975ac89725

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Chart1
### Patch Diff Hash-SHA-256:

c4870a6df7cae13061dae179e9e601752766f436423babba2bb4847207c98952

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) == 1) && ((org.jfree.chart.renderer.AbstractRenderer.ZERO) != null)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Chart1
### Patch Diff Hash-SHA-256:

2ce560e6cb835a1c18f6828e46688e71157948562bf765cbe90233afaf63eb5d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.renderer.category.GradientBarPainter) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Chart1
### Patch Diff Hash-SHA-256:

bc658f7631c121df9a33221629aad0abe0c1deaa31f27e92e18a4a51b184d089

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.plot.dial.StandardDialRange) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Chart1
### Patch Diff Hash-SHA-256:

2964b6c5c4b2f1159ad8382220f3a99df7be8cff26f7e5248ff5451ea2f9eb11

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.needle.PlumNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Chart1
### Patch Diff Hash-SHA-256:

9ba239e74083aff414a181cde1125394721d720f4807789c4e4fbc3e2bdb2ffa

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) - (columnCount)) > 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Chart1
### Patch Diff Hash-SHA-256:

476981d8cb7c98ef7a8d630585babbf3f2d08af47c98e8be35126cea62321ba9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.plot.PieLabelRecord) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Chart1
### Patch Diff Hash-SHA-256:

7e980d0ef97f14e6dc0c988d7d1597d31209741b1eaf9ee1d2b4113fc5cb4806

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.plot.XYPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Chart1
### Patch Diff Hash-SHA-256:

8cc1679685afca5b0f1d5ca27c8d92cbeb74a9e1b7dd963c8417df5e2284b2c3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.entity.ChartEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Chart1
### Patch Diff Hash-SHA-256:

4fe5c9a700dc28740166b785b0bb37b8436c1ff4eb837f2295fe2563a80a1b6d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(getItemVisible(index, rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Chart1
### Patch Diff Hash-SHA-256:

c900896699d02017049c20500a53024e27438a8fac4614a9ef053f73f672cabc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.time.Minute) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Chart1
### Patch Diff Hash-SHA-256:

5eef94fe9818e9eff08f31538407888138c9d966a63d38cbbbfd4cd1b9aa6404

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.renderer.xy.XYAreaRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Chart1
### Patch Diff Hash-SHA-256:

a7b5b7a9f9efe895dad79a68912b4e7587b34d1363ed47085e44070488021c30

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.renderer.xy.AbstractXYItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Chart1
### Patch Diff Hash-SHA-256:

7117ae91fea276ee6eaed5d1d870bdb5f1ee178e1301d3bf9c4f03b8d451120e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.plot.ValueMarker) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Chart1
### Patch Diff Hash-SHA-256:

ec81aa795d79ee744a4b43e4d4c2260ae384aeb55d50f35ba2080b8bdf783195

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.renderer.xy.XYBubbleRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Chart1
### Patch Diff Hash-SHA-256:

07a100ec7d1304fbc1781df1abe489e0cbbc9264f251d4ac537309c8a6be3f4f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.Line2D) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.Line2D)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Chart1
### Patch Diff Hash-SHA-256:

1c4684c2d4a049989c5942f374bc502a6108df8382ba2917919b057be378fb2e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.data.KeyedObject) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Chart1
### Patch Diff Hash-SHA-256:

66d0f8f8adb9c2de4a556597e9bff3ed31fcc5b306c98067b18d4fb5daed0806

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.block.ColorBlock) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Chart1
### Patch Diff Hash-SHA-256:

bd8cc00ae5fdad09b2e0bad2c86dde9226d2aae40fc3cabfca7a5ab34376c61c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index >= index) && (index < index)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Chart1
### Patch Diff Hash-SHA-256:

62e8f5d4aa2182028bc43f4544aee3acf731cf7599e7306822fb059894413098

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Chart1
### Patch Diff Hash-SHA-256:

37fab13e9432b2c2c9c57619d07a4fa3d4fa84a7aa512f950b719dc0046ea918

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.time.TimePeriodValuesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Chart1
### Patch Diff Hash-SHA-256:

9e35f5afd6e1c2022e9babbff022ee96c30eb164a74f8c507607be8037db17c1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.annotations.XYBoxAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Chart1
### Patch Diff Hash-SHA-256:

6a0552aea3c77245e7be508236ef330021a2ad92a282ad647d92386efed40ec9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) >= 4) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Chart1
### Patch Diff Hash-SHA-256:

7ff626ed60ed6db2959bf49a05fb97a34588fbd7c345eaaa4d51c096587ee679

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.axis.DateTickUnitType) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Chart1
### Patch Diff Hash-SHA-256:

cf7712680e09c9323d39a847f417575d77245b49e6a875d33a0d89bee67e4e8b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.block.BorderArrangement) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Chart1
### Patch Diff Hash-SHA-256:

c21d5913839b7db0dc5cf4635cda01307a5d2b3814867883c68bbd3cb248a201

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < ((dataset.getColumnCount()) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Chart1
### Patch Diff Hash-SHA-256:

e8d32996fcb787e2de5022ea282068d5deece108a80fc5449f668bdbd3a3fe7a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.plot.ValueMarker) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Chart1
### Patch Diff Hash-SHA-256:

43382037e9ef8891d8f2db25a2c6a031f45f29f4f3740177dbd4315bb9e72930

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) >= 1900) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Chart1
### Patch Diff Hash-SHA-256:

fb7ebd9c24147601b6de38f60e6d710e2ad97b693f3a60cf6f2a66c80088f297

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.axis.PeriodAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Chart1
### Patch Diff Hash-SHA-256:

67633a475e1667eebe30bdd507051461e04be267f0c947116cdfb4f4199eacb4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Chart1
### Patch Diff Hash-SHA-256:

ecf6b5e30f4d85c6882a4e4aa1006721baf938b64c5a2dbad71e953f781edbe6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!((plot) instanceof org.jfree.chart.plot.Selectable)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Chart1
### Patch Diff Hash-SHA-256:

14f2120fa77a89ae75cdc1e4b991eb73eca9ba2ebe3fdec03d95d444a13032cb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.Arc2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Chart1
### Patch Diff Hash-SHA-256:

147d3fb00160d45a110182ac83dde75dd0d75f5152d0b4049cc11a78d2d02c94

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (0 < (columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Chart1
### Patch Diff Hash-SHA-256:

03bc705091cb40f1367dc9db5b87f459b24b22ccfe49b2a823083dec5871fae8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.data.function.PowerFunction2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Chart1
### Patch Diff Hash-SHA-256:

a44e014a4fbbeed2d7da6aee554f27033415762e55a8f71de77a91e14c414030

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof java.awt.Color) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Chart1
### Patch Diff Hash-SHA-256:

819d0208f112bc797ea3dda552fa710f29c1a46081a17cbd014915ef9b7b7fa1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.data.DefaultKeyedValue) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Chart1
### Patch Diff Hash-SHA-256:

328bb06f4c7b64b89dc281fd1dad5258ae95e3afc5a717aa6c22fb9e8f94e4f2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.plot.PiePlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Chart1
### Patch Diff Hash-SHA-256:

a32592166a0c0cc5bdc9779fec368adf1499f8b769e10b11328a814eb6b3c3f8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.urls.StandardPieURLGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Chart1
### Patch Diff Hash-SHA-256:

6e88d3629110ca3608f0f1d1bf7f5057b2d8073db7e787d6953aba851bbfa081

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.time.Week) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Chart1
### Patch Diff Hash-SHA-256:

c9637f2ef9103f3f57095242f194c3a47d25193023e206b13fcb1953da1bf744

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (foregroundAnnotations.contains(plot)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Chart1
### Patch Diff Hash-SHA-256:

bb7c767d3c6265decf1f229290c3a7fec0945275cabece46ede0224fd59cabb3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.labels.BoxAndWhiskerToolTipGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Chart1
### Patch Diff Hash-SHA-256:

07d5ebb951b75a856aef6d57810f50d7d6c2406110de4470af42c101946f2d51

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.block.AbstractBlock) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Chart1
### Patch Diff Hash-SHA-256:

397b9720691763d86b231e56b267d1282baab5773491f21fce9a0ba354ebd50b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.util.AbstractObjectList) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Chart1
### Patch Diff Hash-SHA-256:

27236d9d9bc10cb9e7b16dacb3b305ba0f3d7eb49c99a3f652e30aee21f7dec8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.renderer.xy.XYLineAndShapeRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Chart1
### Patch Diff Hash-SHA-256:

673a67f9cf2b96aa0aef26783933138a17811f10239d60b21080ad480dd435bc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.data.statistics.DefaultMultiValueCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Chart1
### Patch Diff Hash-SHA-256:

52dbb8364448ab426855c52d78cef0d529b4861bbcfac3dfaca8edf363168c2e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((baseItemLabelGenerator) != null) && (isItemLabelVisible(columnCount, rowCount, false))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Chart1
### Patch Diff Hash-SHA-256:

7e1e1a44adfdd6204e21d0980a79e7d16ed63df2ff1d988cf0343402daf52896

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.pie.PieDatasetChangeType) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Chart1
### Patch Diff Hash-SHA-256:

b733af78e0556d34dd008575ed79d8de78633fb67bdc3bb6629e380f083ddba1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.data.KeyedObjects2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Chart1
### Patch Diff Hash-SHA-256:

c18933e2c00492406c98e09270ca1084aa831bc206c7ed9ca362c640c761ae56

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.needle.ArrowNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Chart1
### Patch Diff Hash-SHA-256:

b529f91fd3ad48727fd29283be37756dc48c4d4ce337949e459245a4341e275f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.axis.AxisSpace) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Chart1
### Patch Diff Hash-SHA-256:

65dfe842c585b718040bcd33dab92fd0eee7cb9f4bbb298240522ccebfce0372

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.Arc2D) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.Arc2D)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Chart1
### Patch Diff Hash-SHA-256:

26ad722c47140f1f0080defb2c422a584ffc9321c3373ffe2860312399672756

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.labels.StandardXYZToolTipGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Chart1
### Patch Diff Hash-SHA-256:

d2e8d50b9384d797942bab893beb2cb38f3e5dd9aa48e13b814e3a276ebd3961

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < ((dataset.getRowCount()) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Chart1
### Patch Diff Hash-SHA-256:

1062031ce8d88a3d6d31c30b70afe5221936c0337cb834c8dc3e171732a9b669

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.axis.NumberAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Chart1
### Patch Diff Hash-SHA-256:

6d493dd6e700bff1f5f886235146fe08641b406cdf4fe88ed1324f9fda657d0c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.axis.CategoryLabelPosition) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Chart1
### Patch Diff Hash-SHA-256:

0746d2a05b3d63c037a77347ccebd0bc161da2a3c1c1cf721475e6ae20f5b756

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(dataset instanceof org.jfree.data.category.CategoryDataset)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Chart1
### Patch Diff Hash-SHA-256:

2313e150f4b75b4dfaaeea4b0c3409d542d51b7dce77d7ba9cdb6437587402b7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.renderer.category.BarRenderer3D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Chart1
### Patch Diff Hash-SHA-256:

f224fea35b61b6d4566452619e8a1de39d03b20e98060c23d2284cc41c4f157f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) == ((getColumnCount()) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Chart1
### Patch Diff Hash-SHA-256:

f9fb89c9342ab33bdb901231e98992fafdcd87c59d0b82b70757a71bff252951

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) == (org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Chart1
### Patch Diff Hash-SHA-256:

5aa83cd18dfe62fb6c368c802b44aa600cda86f5ed2c965a9ee967f27a2b987e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.renderer.category.StackedBarRenderer3D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Chart1
### Patch Diff Hash-SHA-256:

770b85c3cb7d79f9383b176b7d33c9eeeee1024a0e7a0135807d00a436dba1e1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Chart1
### Patch Diff Hash-SHA-256:

f8b62000aa03c90871a5f97fe5c20bdde95d389be9101c3eaf336d111dc6adc9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.labels.ItemLabelPosition) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Chart1
### Patch Diff Hash-SHA-256:

8ca85562946cbeec9aadb2adb78892bf05cf5a3c2e53c424abc7ae2fd53170fd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.annotations.XYLineAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Chart1
### Patch Diff Hash-SHA-256:

95b796913db23f6e8f66d708e851ee4a8d367e791da5d9831f4c36bdcda706a7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.annotations.XYShapeAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Chart1
### Patch Diff Hash-SHA-256:

80c7c1d3a072834f3040510988a8345d7041bc7baf40db68ed258ee422cfdc06

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.ComparableObjectItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Chart1
### Patch Diff Hash-SHA-256:

fbb446f4486dc067f3d2cfd1b37289aaa889d7cb50c6691e3f584e49093be861

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.urls.StandardCategoryURLGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Chart1
### Patch Diff Hash-SHA-256:

a1ed6e45807098c01da0e8bf9d40359d6ebc9e49c055305d8445a5273616f750

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) <= ((rowCount) - 2)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Chart1
### Patch Diff Hash-SHA-256:

c2c2fb8b80bdd34c3f194848c4e3de5c276d3454c9ee66dae31109bc078cc68e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((legendItemURLGenerator) instanceof org.jfree.chart.axis.CategoryTick) && (super.equals(legendItemURLGenerator))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Chart1
### Patch Diff Hash-SHA-256:

39a617defc329e771f8e11e1eec3ac20d7d82c23f0a690322a70c20476125209

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (java.lang.Double.isNaN(org.jfree.chart.renderer.AbstractRenderer.ZERO.doubleValue())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Chart1
### Patch Diff Hash-SHA-256:

7cd1de04b82713afa28bf732c735a13cf1354d5a9e5ba0c8309c9ee9eba926ae

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof java.io.Serializable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Chart1
### Patch Diff Hash-SHA-256:

d65587d4dd02821858de6f80f802ad3f4e4e3800f5a4bffc134d2955301c9b4e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.plot.FastScatterPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Chart1
### Patch Diff Hash-SHA-256:

719f367883d31ba161fcea5806bdcaa7302a12d138901201824b492d9da49ef1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.data.pie.PieDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Chart1
### Patch Diff Hash-SHA-256:

54aaf9c0b14aef49fc7f974325818e8a950c50cefe1d004af38632f339182d24

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((plot) instanceof org.jfree.chart.plot.CombinedRangeCategoryPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Chart1
### Patch Diff Hash-SHA-256:

1f710761c915bd2b84f9a781f2e5b3dd21b7009eb16a92bdaefa738f6dcbfde3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.data.gantt.XYTaskDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Chart1
### Patch Diff Hash-SHA-256:

0ff2f209daa5d2e493f2a4f837d2112065c49cf8f95bd5ec7fb911dd4960c923

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(baseItemLabelGenerator)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Chart1
### Patch Diff Hash-SHA-256:

77f726c7290612833231f3fc7a405b0a7ad132a4fb229236dc919d9080ec17f8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Chart1
### Patch Diff Hash-SHA-256:

11351d67a643ed2282c370bc1878f9e5b274a9aa3e45ac5164adc2b91600c0b7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof java.lang.Comparable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Chart1
### Patch Diff Hash-SHA-256:

712509f4aba20edcba8d340154c5ddb7c1479ea13e4ed79873dee9fd7b5cc859

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.renderer.category.BarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Chart1
### Patch Diff Hash-SHA-256:

b2e2ef3bf3e38364361ccb833e2ee8a887c8eb91630ffa9183d7194377935667

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.axis.NumberAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Chart1
### Patch Diff Hash-SHA-256:

965815668b84863da822a74e86c29c9d8b17a7a2919cf5f913d3300c75abfeeb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.plot.dial.DialBackground) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Chart1
### Patch Diff Hash-SHA-256:

28d55dbd5810d9da0896d00ccc02cbec727cf860a1d64ab937d3bbc3642afd24

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.urls.CustomXYURLGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Chart1
### Patch Diff Hash-SHA-256:

4a97903078a8270283321ec44bcb79c4d6ef90a6a106f88ac9c94770e3190ef2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.time.TimeSeriesDataItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Chart1
### Patch Diff Hash-SHA-256:

b59284171877a1180c6ceb74e37b1d71aa29c87ed621f66074d3f3f70ba0b9e6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.data.time.TimeTableXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Chart1
### Patch Diff Hash-SHA-256:

599e019533ad9ebede159dcc8f53b7c9a41eafdc485ceffcd08ff2fb095763de

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.statistics.HistogramType) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Chart1
### Patch Diff Hash-SHA-256:

2b65318ce2b41b2b2030fb222e4209776177f8a8acbf69ac0e0669eb5d631bb1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.plot.dial.DialCap) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Chart1
### Patch Diff Hash-SHA-256:

81c4ae13e2e22fc062f31c6a68f368605a1c1479c955ede4bfe2852528634d66

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.util.ObjectUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Chart1
### Patch Diff Hash-SHA-256:

be253cfbefb97fba9ad2ea85e8d3f958404c25a6608109bc12b73daa7b2c97af

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.renderer.xy.XYLine3DRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Chart1
### Patch Diff Hash-SHA-256:

8b401d6dd3257daa9bbf5939774590a9b79574b4d5030cccb0d04d96883fa9ae

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((super.equals(baseURLGenerator)) && ((baseURLGenerator) instanceof org.jfree.chart.needle.WindNeedle)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Chart1
### Patch Diff Hash-SHA-256:

a885a0cd44be7d7cddbe2a06aa1948c96d2372ea673cf63aa7d5ac2e54831616

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) == (index - 1)) && (index != 0)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Chart1
### Patch Diff Hash-SHA-256:

b1be6120e17eeba7f7e4c83748bb03dd44f9e370a35d53fb0f8ca77cc0d00553

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Chart1
### Patch Diff Hash-SHA-256:

3ab8a7b5d0921809c046e41624b5533d5a3514354efeb09db170dfb1f3b685c9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (isItemLabelVisible(rowCount, rowCount, false)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Chart1
### Patch Diff Hash-SHA-256:

ae58ff8ea701dce7311d4cf76b4f4892a7fa63a8ab6c3a830c4447980c313017

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.annotations.XYPolygonAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Chart1
### Patch Diff Hash-SHA-256:

9c77c27595db39260285a75d5701e18e25ec48e8312f68b8eb2770cd7670d9f3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.data.KeyedObject) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Chart1
### Patch Diff Hash-SHA-256:

73666d212adecd3ad3e5ff4ef877c3a80557a2d34cf070e24473dc89a7c013f1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.JFreeChart) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Chart1
### Patch Diff Hash-SHA-256:

24f5b855cc2927cacffbc994d45b065ff7e503fe0ce2f78ea6bbea2f1afec5b4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.axis.ValueTick) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Chart1
### Patch Diff Hash-SHA-256:

dec698d662a0ebb6119bf8b171f27e22dcd37cb51e027c35fec15d5075f624d5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.needle.WindNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Chart1
### Patch Diff Hash-SHA-256:

7dc615794629915bd550f3fa65c36d00322a52bb4b7d38e4bb963a0a88a250f4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.data.ComparableObjectItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Chart1
### Patch Diff Hash-SHA-256:

c5ae123acf8b5baf203b262f80cc342033cac55bbfe91285e9b5fccb2e1b1f53

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.data.time.TimeSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Chart1
### Patch Diff Hash-SHA-256:

1e6015dfc0c8d9052d0961a2ebb871eda694306752bab5bacb57140475fc6413

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.function.PowerFunction2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Chart1
### Patch Diff Hash-SHA-256:

d9111680a9bb8f70ec55f54061a3f8fd2edb38ec1c254a1f3225015102d6d393

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.axis.NumberAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Chart1
### Patch Diff Hash-SHA-256:

de030bfc4065730b67bfdea7e3f949cebd7ef31a6b6679c3dc28813d0169865e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.axis.SegmentedTimeline.Segment) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Chart1
### Patch Diff Hash-SHA-256:

1d43c5ed51e69223c71606ee89fb39dee9fa989dbe83ed0ab3f804095454b6de

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(isSeriesVisible(rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Chart1
### Patch Diff Hash-SHA-256:

a4ba792e28539808f6a743632e316d3b00d47b1969fb3365bdfc1774ea9aa56f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.data.xy.XIntervalSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Chart1
### Patch Diff Hash-SHA-256:

7db1f18c2ab0855b39594622c2560f776c7521cc462311aa286cd16e76ee9ae1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.annotations.XYTitleAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Chart1
### Patch Diff Hash-SHA-256:

814928e4b275abe16c978365522e144edff44f6aece871251fef178a67045338

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.xy.DefaultTableXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Chart1
### Patch Diff Hash-SHA-256:

8cc3decb865a8f0bdd0e50c34f148b618740f23df51e8d50e46dd0db60e92d1b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.data.time.TimePeriodValuesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Chart1
### Patch Diff Hash-SHA-256:

45123f77742a62aae208b2835480bf2b391613ce9a3fa16db07314f10bfbd386

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.needle.LineNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Chart1
### Patch Diff Hash-SHA-256:

55e7fec4e8a4c8fbae77422f95cdf8808146be15865a13406e91a24cb19a6537

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.block.BorderArrangement) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Chart1
### Patch Diff Hash-SHA-256:

d76c23a377becca46d300507e90475243426c9a09cfa05bb88729c7ca916823a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.data.xy.MatrixSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Chart1
### Patch Diff Hash-SHA-256:

600f0b85cb29cf2995a851ad604e9115f6d06b97adecf979764cd896a48b2353

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.axis.CategoryLabelPositions) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Chart1
### Patch Diff Hash-SHA-256:

1d6f1f16248bdf7faced6d91242ae56d14f42ca72fe6669c1d8857c06f72e1ed

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == ((columnCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 455 of bug id Chart1
### Patch Diff Hash-SHA-256:

abf4c356e8f581c736c6e2c345e51ca68b5932143a2ab947df77ae7b6ad19ef0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.Ellipse2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 456 of bug id Chart1
### Patch Diff Hash-SHA-256:

a8c915c8ca6ab90246f1572c8e4cd817e2a9110ad8dd02da9a5ffdbcbac8ca11

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index > index) && (index <= (rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 457 of bug id Chart1
### Patch Diff Hash-SHA-256:

c2b59695153050be39ab72271f3180c8e1119f83f96b8efeba49e7a8019974ce

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.axis.SymbolAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 458 of bug id Chart1
### Patch Diff Hash-SHA-256:

0968aae47f2b151793b4b01c3edd316fd81e1d8b93090b7cf395e4801de2ec8c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index > (columnCount)) && (index <= (columnCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 459 of bug id Chart1
### Patch Diff Hash-SHA-256:

693fbe44dc337282b1d366c1d4dd43edf0a24e9b5c2c19496107e2764bb49bfb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.plot.CombinedDomainCategoryPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 460 of bug id Chart1
### Patch Diff Hash-SHA-256:

96826039cbe7f3804a86c1dae0e9ae8de3d6f91a6321482ffe8f264d5f9056e4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.block.ColumnArrangement) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 461 of bug id Chart1
### Patch Diff Hash-SHA-256:

4238dbea4b3f03faab27dbb2fe6a5424a586a4c0e5f723d96d1f65f880ff896b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.labels.SymbolicXYItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 462 of bug id Chart1
### Patch Diff Hash-SHA-256:

93438868e111337b5c798eb7186d3fde4667117695c9e11a6fdefd11fd8d847c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (isSeriesItemLabelsVisible(columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 463 of bug id Chart1
### Patch Diff Hash-SHA-256:

e705f141e82c80108736f38d7cff1700a5639f140d33fd0b89fecfbdc9159881

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.xy.XYDataItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 464 of bug id Chart1
### Patch Diff Hash-SHA-256:

3d353c1b8623d5572f44571fedf035d4e49c31ee390688d8d5154d00676c3b81

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.data.xy.XYSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 465 of bug id Chart1
### Patch Diff Hash-SHA-256:

e9d738bbf3a8f5327d12874c6911767fd275742766b6e0e2f55aaf4eac77374c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.renderer.xy.StackedXYAreaRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 466 of bug id Chart1
### Patch Diff Hash-SHA-256:

b050dd8f50bbdd40415b30caca1e243a7ce79c1e14e4bffc72eaa6e133a070aa

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.axis.DateAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 467 of bug id Chart1
### Patch Diff Hash-SHA-256:

682d7995ea3684cffbc5fde81bbedb8dc87100de7d69d2d852971ab046e72de6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.xy.XYCoordinate) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 468 of bug id Chart1
### Patch Diff Hash-SHA-256:

5ee79dfc3d23c0e7c7ec84c48560ad97e63bdceed51508b873977770f6e3a299

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.labels.StandardXYSeriesLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 469 of bug id Chart1
### Patch Diff Hash-SHA-256:

3112d7b76d32b6779326587c475b0df3693d6625b068750583ce9225b39ac298

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.axis.SubCategoryAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 470 of bug id Chart1
### Patch Diff Hash-SHA-256:

b8e5a3af680d91a9591b69c274c132eef1472170e34a5bfe3e396b48b4d710ca

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(plot.canSelectByRegion())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 471 of bug id Chart1
### Patch Diff Hash-SHA-256:

d5073abdb13925737615197beea210f45d79b3360dac9e5f96934a6b16a1959e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.chart.entity.StandardEntityCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 472 of bug id Chart1
### Patch Diff Hash-SHA-256:

89a2816154185ae90bea824c9078e44ef642676d4220a3e48832b4ea3d435b12

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.Line2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 473 of bug id Chart1
### Patch Diff Hash-SHA-256:

355d9fbda4d3f3eeefc82c3ac4364b256a66703e632f8395b10b71e3303309ea

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.Polygon) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.Polygon)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 474 of bug id Chart1
### Patch Diff Hash-SHA-256:

785515d295eca93dba65187ea5800e061e4952bbaac7148a55a7081d230307cd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof java.lang.Number) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 475 of bug id Chart1
### Patch Diff Hash-SHA-256:

5b928a837f22edc76e0fc4797df5e9e1b255824e95d278292c224a35037659d5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!((0 == (columnCount)) && (0 == (rowCount)))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 476 of bug id Chart1
### Patch Diff Hash-SHA-256:

003fcceaf3e93a61f7b146ae55d533765f32c0f21aced25778601ead9f9b55f7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT) instanceof org.jfree.data.pie.PieDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 477 of bug id Chart1
### Patch Diff Hash-SHA-256:

1dddecd49fa69af8f53330d124c6e04241a7cfd8eea03115c8e3f2d8bb4f05c1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.labels.StandardPieSectionLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 478 of bug id Chart1
### Patch Diff Hash-SHA-256:

25a9d66a87fc389d9c6e624fb0dc5f9754f1357a3e043c62648499a77007301d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.plot.dial.StandardDialScale) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 479 of bug id Chart1
### Patch Diff Hash-SHA-256:

ac8484497439635446910b6870389939e99120a7c9e541dc19677c871d47435f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.axis.DateTickUnit) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 480 of bug id Chart1
### Patch Diff Hash-SHA-256:

e77db46d1cb1fe1c658f8fc89849d6d1a1786ab3c291e2be34cdcfcf901fc170

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.block.EntityBlockResult) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 481 of bug id Chart1
### Patch Diff Hash-SHA-256:

e26cbc6592933cb92f7a2afe153f12367812055b5976f03238155466036a8dc0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) < index) && ((columnCount) < (rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 482 of bug id Chart1
### Patch Diff Hash-SHA-256:

54e8526b81d688bdf419a50e22755d569470bc510ac51854f1c6c8a681560476

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!((plot) instanceof org.jfree.chart.plot.Pannable)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 483 of bug id Chart1
### Patch Diff Hash-SHA-256:

a66c6fa27bf7df497bd9313bdfb81110b55a06732d52bffe7bc789acf79d2f42

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE.equals(toolTipGeneratorList)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 484 of bug id Chart1
### Patch Diff Hash-SHA-256:

4642231df3f79ab66533d54eeb13702e06e907bd6fbad044c896ef5821070fb4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.plot.RingPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 485 of bug id Chart1
### Patch Diff Hash-SHA-256:

043615a96cf9cbcab1379beb3b2877fe362a7e8326cc64ef9adc0c3d85bb3f8b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.data.statistics.HistogramDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 486 of bug id Chart1
### Patch Diff Hash-SHA-256:

912f5f617010144d4ff93de5f1d0d54ad551a80d7744e64792580846219fc395

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.axis.CategoryAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 487 of bug id Chart1
### Patch Diff Hash-SHA-256:

2271515adce268b549d8140de55f2d87d7fc7fd1c89c86b2c91f38dcf5cf54d8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.data.time.TimePeriodValue) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 488 of bug id Chart1
### Patch Diff Hash-SHA-256:

6731105ee2c987f8f55042e675c0b9c0748fb22d98423b59d6f2b0071492d045

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.data.time.SerialDate) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 489 of bug id Chart1
### Patch Diff Hash-SHA-256:

56bbe60616caf2f89a8bf8db8d114e6941c5e6a5518d3e8f381f61f405c3b7c5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.dial.DialTextAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 490 of bug id Chart1
### Patch Diff Hash-SHA-256:

0df0a4c9fc507c59798b11c6742e6ebf478ae14c1f76135077385c400a396ac7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.renderer.category.StatisticalBarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 491 of bug id Chart1
### Patch Diff Hash-SHA-256:

f92eec1ec4832aefada8702a874fcbf83265e428c9bb3e91c41f205283b9adba

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.labels.AbstractPieItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 492 of bug id Chart1
### Patch Diff Hash-SHA-256:

6f055b4c287ab3690bdea495cd2d800dcaaa3587a4fb1f26ded46c4d305b6498

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT) instanceof org.jfree.data.KeyedValues) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 493 of bug id Chart1
### Patch Diff Hash-SHA-256:

b940c7ce9021c89322611ce840a9959db6a2a1b11fbf7e21de6414f01e759ed3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.renderer.DefaultPolarItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 494 of bug id Chart1
### Patch Diff Hash-SHA-256:

1184c5e468c18eb78f5809988892a3094870b8e692128dd6997a8c070a0706b1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(getItemVisible(rowCount, index))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 495 of bug id Chart1
### Patch Diff Hash-SHA-256:

6812a58ba951fc57a839751830c1e0d3790e6f0a3c4feb6ce86bd603e64f54e0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((plot.isDomainPannable()) || (plot.isRangePannable())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 496 of bug id Chart1
### Patch Diff Hash-SHA-256:

dd6aa4dc516da5e349e6e73cda53ce70eec832ea333a026fc97844a446039fb2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.plot.CombinedRangeXYPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 497 of bug id Chart1
### Patch Diff Hash-SHA-256:

76bf8a79acba12c2718482d50875d24d362272e42abce4670a959b3b7a4f8f67

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.block.EntityBlockParams) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 498 of bug id Chart1
### Patch Diff Hash-SHA-256:

3f1314cdba99c1581acf21ec851fa7c221643354dd38e8159c752f04e91f2d63

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.util.PaintUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 499 of bug id Chart1
### Patch Diff Hash-SHA-256:

ecf7e684160598e1cf4bc884fbbf4d1cb00657a24178217400d8b799bc65898e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index < 0) || (index > 2)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 500 of bug id Chart1
### Patch Diff Hash-SHA-256:

732433400200dc9f7da1f455b4146acb1aa74605a8cdf7495b479a1be96c539b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.category.SlidingCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 501 of bug id Chart1
### Patch Diff Hash-SHA-256:

3ab738b44979da5411bf438a1dac0466e450bb020febd40cc5464ccc9b075f24

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.xy.DefaultOHLCDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 502 of bug id Chart1
### Patch Diff Hash-SHA-256:

09704296bc37f17f37cc88bf351bfe7e766a0e7ab7b14c63c6b8c9d9d971fef7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.renderer.xy.YIntervalRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 503 of bug id Chart1
### Patch Diff Hash-SHA-256:

c454b976184156bfe2da56387383b00a873e780e7625b6b580a90c463c303fcb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.statistics.MeanAndStandardDeviation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 504 of bug id Chart1
### Patch Diff Hash-SHA-256:

5d0602730721cf1a13d07191775f89a18ca7b3c56cf5db66bafcedb1e2e5a6ee

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.needle.PointerNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 505 of bug id Chart1
### Patch Diff Hash-SHA-256:

55aa0044c45407b937c01b2ff793bb446b534c373f6cf5aac657b773172501cf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.time.Second) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 506 of bug id Chart1
### Patch Diff Hash-SHA-256:

5a6449cba1adee8af3f6f67484639dfbfe8e2771110204937f6facdfc614df0c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.util.PaintUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 507 of bug id Chart1
### Patch Diff Hash-SHA-256:

4883486de208af1cd9fd38bca33e271bb25d0b808a36d1e3cef306d8c452d110

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.util.DefaultShadowGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 508 of bug id Chart1
### Patch Diff Hash-SHA-256:

2637f168063565a4d4228e4dc89393d65f05a0ce47632a63f74fa40bd7fd5b9f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.axis.SubCategoryAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 509 of bug id Chart1
### Patch Diff Hash-SHA-256:

71b53b21447ba613ab2290b979536908fe6863feccc11adb0ad1deedb1ad6bbb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.renderer.category.MinMaxCategoryRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 510 of bug id Chart1
### Patch Diff Hash-SHA-256:

5d1797c8841c2f973e1a7fb02621e2a950970a548501c084f005c328c87d0fe3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.text.TextBox) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 511 of bug id Chart1
### Patch Diff Hash-SHA-256:

9c4e5b8a1b7809023b437956474d5bfd41f446cefef41253c348a94a06626ad8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (plot.isDomainZoomable()) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 512 of bug id Chart1
### Patch Diff Hash-SHA-256:

1662162dbd04782d3ca9946206fc4585aae96ee3de6f1f12af746cf506cf7b40

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.block.LabelBlock) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 513 of bug id Chart1
### Patch Diff Hash-SHA-256:

8a4e46f33bf42651197832eb1e1db35325b40adec61b9b2ef5dc4bcce39de500

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.KeyedObject) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 514 of bug id Chart1
### Patch Diff Hash-SHA-256:

9513bb6d29860a8604a552e978de51f7d0139b43de2a003aaecafbf47191d960

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.data.time.Day) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 515 of bug id Chart1
### Patch Diff Hash-SHA-256:

83c4929376a63b2f1cc0f411caa7a6411390b3dc3921a74afca68054918b1eb8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.labels.StandardCategoryItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 516 of bug id Chart1
### Patch Diff Hash-SHA-256:

53aabcee0e95d6e5765c5e75f65155b7eb2c79a7aa81bee7364bdf974b02341c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.gantt.Task) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 517 of bug id Chart1
### Patch Diff Hash-SHA-256:

078f6e8f08766847f7cab53efe18aaab6ea7bb1877b68a2ba2245581abc5be7f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.gantt.XYTaskDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 518 of bug id Chart1
### Patch Diff Hash-SHA-256:

3a3cd368fdac531f701397699895cef7c03245af461bb411832b8403738f3591

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.plot.ValueMarker) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 519 of bug id Chart1
### Patch Diff Hash-SHA-256:

1629039e9379e9a7c19564bfebe9a08f169203e4820c405fa70e1ce6dc4c6a43

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) % 4) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 520 of bug id Chart1
### Patch Diff Hash-SHA-256:

f5ec861bb9693611c5637f98b7d00774409eb1862d5517951d5fc03b82eefb48

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) < 0) || ((rowCount) > 255)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 521 of bug id Chart1
### Patch Diff Hash-SHA-256:

5dccf2c8ded739f03ca31154c95a0db5b712c65636be47e4bbea85c99249e948

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) < 0) || ((rowCount) > 3)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 522 of bug id Chart1
### Patch Diff Hash-SHA-256:

db265c208048e5f0d9d906147c6bc2ec15e99c3717816c3431aa88f65b0181ea

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((backgroundAnnotations) != null) && ((backgroundAnnotations.size()) > 0)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 523 of bug id Chart1
### Patch Diff Hash-SHA-256:

3725358c03320d2c23d22d4aa0bde980d046f691109c73821127fc4138e1290d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof org.jfree.chart.renderer.category.LevelRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 524 of bug id Chart1
### Patch Diff Hash-SHA-256:

e507e8f4eec84844b0d2cbeb29c284a96f88d4cad6c381c4e7f275d05901840b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.needle.WindNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 525 of bug id Chart1
### Patch Diff Hash-SHA-256:

29afda7e394cc3b66d5e98ec760e6bb3d60bac301d8a6feda29b19b241268f91

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.axis.DateTick) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 526 of bug id Chart1
### Patch Diff Hash-SHA-256:

12a7331439023e614fb7c9912c9643fb26c5b8f799d85550bc509b5ea9811d4c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.urls.CustomPieURLGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 527 of bug id Chart1
### Patch Diff Hash-SHA-256:

7c397caddc54f1d24da75743d8852ce9e6cbf3b1613c77eea05f453d4a26ef8b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.util.AbstractObjectList) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 528 of bug id Chart1
### Patch Diff Hash-SHA-256:

c6ca07ad386849ac1183299f3ad1072ea8ed69709ed44508d841b34c23310760

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.annotations.XYImageAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 529 of bug id Chart1
### Patch Diff Hash-SHA-256:

965434208138a5ddc1c951e9ed8cae837d094999346b8b7caedff8497f8d86f6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.data.category.DefaultIntervalCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 530 of bug id Chart1
### Patch Diff Hash-SHA-256:

ba8fe5087a40b4989e0064ec6ae9252dd20f3b3ab9961925c4114d60b04e62ee

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.renderer.xy.SamplingXYLineRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 531 of bug id Chart1
### Patch Diff Hash-SHA-256:

eb068d8a361936cc633a09c942e34284318457065d95800a3bec4b7d4f21eb5e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((toolTipGeneratorList) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 532 of bug id Chart1
### Patch Diff Hash-SHA-256:

6074e9770d86eab364c03f996a22244e06a8b4cd190b0d05c67375621ccbab0a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.axis.SymbolAxis) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 533 of bug id Chart1
### Patch Diff Hash-SHA-256:

b4077aa1931f87915cb5212f2348ff17ae6dc48c30bd9feaa4e4190ae87cb5c6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(legendItemToolTipGenerator)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 534 of bug id Chart1
### Patch Diff Hash-SHA-256:

b4513cfd3ca64b94cf87f6808c16f5766ae9f3130df1b36632dbb739640e2cb6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index & (rowCount)) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 535 of bug id Chart1
### Patch Diff Hash-SHA-256:

f98559f868b83f14750a754ab2749773bf344f4afacd2fe75e06c4c9c1c0d97a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.data.xy.YIntervalSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 536 of bug id Chart1
### Patch Diff Hash-SHA-256:

d4bf398c624f59c564d64d7fb9a0f9b729d470a0df538a8beaf4c1bf12cadf21

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.pie.PieDatasetChangeType) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 537 of bug id Chart1
### Patch Diff Hash-SHA-256:

911a39cb8504af967f9a3d6484026ad3b875466734f79b2c2a864c4aeb5c210b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.renderer.xy.XYLine3DRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 538 of bug id Chart1
### Patch Diff Hash-SHA-256:

dcf80bc54de36289dbdf2e4bcc6261099da486f35ea3a8a613c3fb08f0555baf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof java.awt.GradientPaint) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof java.awt.GradientPaint)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 539 of bug id Chart1
### Patch Diff Hash-SHA-256:

03b9b6f362a2d1cbe4994c8e10464c86ad69929fb6c699e75e0ab35d647fd214

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == ((rowCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 540 of bug id Chart1
### Patch Diff Hash-SHA-256:

1777727a63753a4917b993fc9b1864fb62f2444ac813ff4b40a75dc35ed021c4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) instanceof org.jfree.chart.labels.HighLowItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 541 of bug id Chart1
### Patch Diff Hash-SHA-256:

51bf51e7de32b213cc645550786a8b8b247f6a8d608a9f9ff028a303e0b5c5e4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.util.Size2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 542 of bug id Chart1
### Patch Diff Hash-SHA-256:

1546f349f725f0672c953af9f904df4e29b0201b48c73b36bb18a2b03abdcd5e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((urlGeneratorList) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 543 of bug id Chart1
### Patch Diff Hash-SHA-256:

efecee29da7e4822adf2550df6b0506db5296c5c3b1dcc5d939433fd064aed30

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.block.BlockContainer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 544 of bug id Chart1
### Patch Diff Hash-SHA-256:

04a1721e67be6bef4349caaabfecbee69c5988ab500e293ad5dd7f266de357ce

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.urls.CustomXYURLGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 545 of bug id Chart1
### Patch Diff Hash-SHA-256:

7607df8ba2bfbccd1dbccba8cc9afb04c0ba42d6622e2a9ad95c53b8c92de950

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.block.ColorBlock) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 546 of bug id Chart1
### Patch Diff Hash-SHA-256:

a4bd992d6b263f8c60a40515d44a742debd7f23ef034a47d1077f49d5a22832b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.util.RelativeDateFormat) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 547 of bug id Chart1
### Patch Diff Hash-SHA-256:

84543929a17a3f3d37705805421172f50642b64f54b5e8145284b43afbbaa5be

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.xy.MatrixSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 548 of bug id Chart1
### Patch Diff Hash-SHA-256:

0f00d918e8433a201dcc2af1ce25e06c7faa3deddc119aaae30265375468b8c2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index > 360) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 549 of bug id Chart1
### Patch Diff Hash-SHA-256:

001db594159276813e5bcb0a10a0148f478f1f9ba7ef83638e75ac48ccd4d7e1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 550 of bug id Chart1
### Patch Diff Hash-SHA-256:

5955e87994ed08ba85dd560df71e142e397dd03737e0d500b79d361458598ba1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.axis.StandardTickUnitSource) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 551 of bug id Chart1
### Patch Diff Hash-SHA-256:

55cc9b9ba0f78a5741242d0d0c695fca93ef88210ffc61a6500adae45fb7a331

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.urls.StandardXYURLGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 552 of bug id Chart1
### Patch Diff Hash-SHA-256:

77831385037c46da51a57472eef1b24fa0de9223c1194165a0a4f9956433eb71

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.plot.CompassPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 553 of bug id Chart1
### Patch Diff Hash-SHA-256:

15cb8c4281485b3691b559e566e392119fed39e06efab064ebd4f211e0296686

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.statistics.StatisticalCategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 554 of bug id Chart1
### Patch Diff Hash-SHA-256:

cb8fc73e08c3ab6a21eeb02929ccdc22f6f56f6d1d8c26c1874f10ea523a3ea1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.data.general.SeriesChangeType) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 555 of bug id Chart1
### Patch Diff Hash-SHA-256:

a65bdd6efd06769a112b6649aad70796e4e20328339f760183da79a42c04f640

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.annotations.XYPointerAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 556 of bug id Chart1
### Patch Diff Hash-SHA-256:

22ccb1eeabf045119bbe1c8692fed30be5e2e58688e40f8dc88332faa8062b37

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.statistics.HistogramDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 557 of bug id Chart1
### Patch Diff Hash-SHA-256:

eae5c2441e9f91b56f9d425625abed2cec08e7e589600e372f66243fc5ed34d4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.data.time.ohlc.OHLCSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 558 of bug id Chart1
### Patch Diff Hash-SHA-256:

93120b33be11bf9127818b14e15970c9f0d7811f20843bd34c84904161e1bb03

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (itemLabelGeneratorList.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 559 of bug id Chart1
### Patch Diff Hash-SHA-256:

222e293e21c0978e550aa9c22e2d8f8271daa9e0fb5b8aa984758d34a1aae61f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.renderer.xy.YIntervalRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 560 of bug id Chart1
### Patch Diff Hash-SHA-256:

2682a500b625186e960cb2a9631d65762b032c05ef5cd93f5a82a5d5c7a873d9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((getLegendItemToolTipGenerator()) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 561 of bug id Chart1
### Patch Diff Hash-SHA-256:

c7736afea218bd7b32eff6c394deeb9455bb839c80dd0b411fb7f7166d0b90c3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.plot.CompassPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 562 of bug id Chart1
### Patch Diff Hash-SHA-256:

b147fe117a9b9e89f2ee227624e6ca06acd669b69f477dabaee2fd0fa269ebda

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_PAINT) instanceof org.jfree.chart.renderer.xy.StackedXYBarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 563 of bug id Chart1
### Patch Diff Hash-SHA-256:

f4b500d7031876ba08bcc035b3ae5d5f4ec43a94fc69057c823e193901974b0d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.data.xy.XYSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 564 of bug id Chart1
### Patch Diff Hash-SHA-256:

fc95d95a0d5940a1ce07a2f26f4a2c14b495d9e73a14d4111d60ee4fb19d93d6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.KeyedValues) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 565 of bug id Chart1
### Patch Diff Hash-SHA-256:

9a59b6abfdb6223a5b887a92b39f5774b7c4d30cbf783936111879ed83d88875

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.chart.plot.dial.DialPointer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 566 of bug id Chart1
### Patch Diff Hash-SHA-256:

13b4051a1a498f40b315f2930d65a61396cf0def8524400381f1182a2deebbbe

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (foregroundAnnotations.contains(org.jfree.chart.renderer.AbstractRenderer.ZERO)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 567 of bug id Chart1
### Patch Diff Hash-SHA-256:

ca50f5a1a9288f4c273fac373266302f65cb06c1385a7d8947ace5920b60cc64

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.util.RelativeDateFormat) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 568 of bug id Chart1
### Patch Diff Hash-SHA-256:

6ac72989aa8e941680fa379184f36bc2ad59583b27b5c524f6de8abddc919b8a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.renderer.GrayPaintScale) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 569 of bug id Chart1
### Patch Diff Hash-SHA-256:

730e09597632bf042126d1860a8ec86a408d8fd7681060b02d2ed00711bcd7f2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.chart.plot.dial.StandardDialScale) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 570 of bug id Chart1
### Patch Diff Hash-SHA-256:

467c888c128fd267b33bb53db31928962f707a9198339a11aa67f8743cc88bf8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.chart.renderer.xy.AbstractXYItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 571 of bug id Chart1
### Patch Diff Hash-SHA-256:

76f004bf10deea28af61cbd6eb7485bcefe2a78d688c630396da6a6246979fce

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.data.ComparableObjectSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 572 of bug id Chart1
### Patch Diff Hash-SHA-256:

86421999b06880885e9ab35c328c73b913c28ef8c93f3e6a8fb7f129db9c603c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.data.gantt.XYTaskDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 573 of bug id Chart1
### Patch Diff Hash-SHA-256:

c0b0c79be7ac633dac3f723b5243cdc24305e5bbf506b503603484635e2eda74

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((baseItemLabelGenerator) != null) && (isItemLabelVisible(rowCount, rowCount, false))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 574 of bug id Chart1
### Patch Diff Hash-SHA-256:

3a8b14a0b6d62f1ecb2a8de32aed7e23ce58a3d95e4f8bdbf8c9706bd82f26fd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) > (rowCount)) && ((columnCount) < index)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 575 of bug id Chart1
### Patch Diff Hash-SHA-256:

206cfe79e0fcb5283b21aaa76e10d32dccd9108a4f3b76bf78af62db37922f8d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.xy.XYBarDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 576 of bug id Chart1
### Patch Diff Hash-SHA-256:

a830115ee955f272ae57f0c26f23ebce15178fe42a470f3f2b26860360a36022

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE) instanceof org.jfree.data.xy.CategoryTableXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 577 of bug id Chart1
### Patch Diff Hash-SHA-256:

d4c3a82cc138cf363b4cf418bb657e4cb0bf9297c8d38ab3cf5dd395070d9612

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.block.EntityBlockParams) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 578 of bug id Chart1
### Patch Diff Hash-SHA-256:

a0523b2119a908397d58c933bd300c6bf1bdb6853e0b575989e382d7db676264

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations) instanceof org.jfree.data.statistics.SimpleHistogramDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 579 of bug id Chart1
### Patch Diff Hash-SHA-256:

ace7f6c3406dafe63c80d7750dcc3fdba545771f0c05384b6d29d9e7235db954

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((baseToolTipGenerator) != null) && ((baseToolTipGenerator) instanceof java.io.Serializable)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 580 of bug id Chart1
### Patch Diff Hash-SHA-256:

573ea277c184f009ce7a38f93028278d9a662507a8bd369c36f5cd304cd9683f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.chart.renderer.category.StackedBarRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 581 of bug id Chart1
### Patch Diff Hash-SHA-256:

c7e8fcb196ba853c4810356ac4bb95a0706e5a12b85e9d43713e39283fef9a77

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE) instanceof org.jfree.chart.axis.TickUnit) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 582 of bug id Chart1
### Patch Diff Hash-SHA-256:

ed920efeaf38d76a56b9eedc6e36dcc5b18d280a42e455c339eb45549476293e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.LegendItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 583 of bug id Chart1
### Patch Diff Hash-SHA-256:

1748e5e23926ebf1b856d64cb9a1504f2d6477b02e265460e33b276f6d0d5008

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) instanceof org.jfree.data.ComparableObjectSeries) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 584 of bug id Chart1
### Patch Diff Hash-SHA-256:

b6f288a841cc9f671dfc31efa73c3623def950782ec2f28e7c313dcfb8c501f5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT) instanceof org.jfree.data.time.Millisecond) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 585 of bug id Chart1
### Patch Diff Hash-SHA-256:

eeecbef0afd6eec8c15bce813e6964d5ed1d42a6c2d771f105e36845231f86c5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.data.time.Millisecond) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 586 of bug id Chart1
### Patch Diff Hash-SHA-256:

9099cc5bee934905784fb94525cc8d163c2f63723190fbbe4749ba6f9ecdac12

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof org.jfree.chart.labels.AbstractCategoryItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 587 of bug id Chart1
### Patch Diff Hash-SHA-256:

c1e325b8bb39d1b43fd9af7d1f8230ea4521e377449482fb0f42d240e9f5aa5c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(isSeriesVisibleInLegend(rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 588 of bug id Chart1
### Patch Diff Hash-SHA-256:

765ad6da80a98b919e040e2865b4fbaf32f12c68f954f03b4f46ab074c145b9f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(plot)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 589 of bug id Chart1
### Patch Diff Hash-SHA-256:

797771fd54f07d2c73708e7c3befd4c2280e677aee51ca1f2fdc468a9194239b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations) instanceof org.jfree.data.time.TimeTableXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 590 of bug id Chart1
### Patch Diff Hash-SHA-256:

a0b0571980ab6a043a612ed8fd645afd2a811f4efcf58f9bb021b56aa6328b17

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.data.time.Day) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 591 of bug id Chart1
### Patch Diff Hash-SHA-256:

e2d0635e4bb8e1006a17e5ec13696f9b8aec9e578a0aa24428cec62fa0089a9a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (java.awt.geom.Rectangle2D.OUT_RIGHT)) == (java.awt.geom.Rectangle2D.OUT_RIGHT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 592 of bug id Chart1
### Patch Diff Hash-SHA-256:

60b4444903f258f38f18eb915cf86d08516f98a816ab599252235f86cbabcbec

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < ((rowCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 593 of bug id Chart1
### Patch Diff Hash-SHA-256:

1a3cb4615398e3cc6d1878e62a9628e73129a3ee14a2666a39fbc8bf0bfdd6d7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) != (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 594 of bug id Chart1
### Patch Diff Hash-SHA-256:

ddd9e08873c267b1cb03049449aad391733c3994451f3568fea921d1fba13560

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 595 of bug id Chart1
### Patch Diff Hash-SHA-256:

b2073b9d7b2c04aff4a01edf67658c8b76c0cdc8e662e0b45d5ff89a71e1f839

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (itemLabelGeneratorList.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 596 of bug id Chart1
### Patch Diff Hash-SHA-256:

419d84e72c4b1853126eff7367f09c5fa797e619aa419a0bec9e112eb9b7464e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (java.awt.RenderingHints.VALUE_ANTIALIAS_OFF.equals(result)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 597 of bug id Chart1
### Patch Diff Hash-SHA-256:

cc459b38f668f4ee6e62a907eaa5f7697144977a3f46e64c435c58b739afd5fe

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((org.jfree.chart.renderer.AbstractRenderer.ZERO.doubleValue()) < 0.0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 598 of bug id Chart1
### Patch Diff Hash-SHA-256:

a0bc692d5a4826345fc6ed81101cbb234d84c301f796d47f6051869db29bbdd6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations.size()) > 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 599 of bug id Chart1
### Patch Diff Hash-SHA-256:

38fd81817ee25c8a9cd577d45cbb5331bb2cca351ec79e12df2ab2fe84357af7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.IMAGES)) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 600 of bug id Chart1
### Patch Diff Hash-SHA-256:

c8420f1f05ddd69dbdd214388940505c989e97aabf0cbcc429a5998416782d58

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (backgroundAnnotations.addAll(backgroundAnnotations)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 601 of bug id Chart1
### Patch Diff Hash-SHA-256:

c13cacdab7611410ba4968577e43d4b362ebce3a56acad2a11e21050f7d2455f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.data.time.SerialDate.isValidWeekdayCode(rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 602 of bug id Chart1
### Patch Diff Hash-SHA-256:

951efdc2fa7d7842981d47340ca9cfa77fdb27ed1bd8669fe988d272bd696fd4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.dial.StandardDialRange) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 603 of bug id Chart1
### Patch Diff Hash-SHA-256:

9d62c11105131958e626ee85e61dd5c09e6b15a828ba5e61673713ec64c5116b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 604 of bug id Chart1
### Patch Diff Hash-SHA-256:

a1489b1addd9e5292bf6d075d6a2bfea2bdec232c86a952381c42a8d0b47794b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.util.ObjectUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 605 of bug id Chart1
### Patch Diff Hash-SHA-256:

7d3f9015472960684b977b2a2c62d41bda228205c3d8ccb99f0cce54566457da

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index >= 0) && (index < (rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 606 of bug id Chart1
### Patch Diff Hash-SHA-256:

1ea3b5ec289967aca865b43206da725ce48e04f74bc6961b251d499508932464

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.util.PaintUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 607 of bug id Chart1
### Patch Diff Hash-SHA-256:

95f09100e0c2df0637d9996e90eb24ec0112d911717e294ba2818ca6b10e3f7b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations.size()) > (rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 608 of bug id Chart1
### Patch Diff Hash-SHA-256:

cc2c1a59857afb54c8c0a5c2232d899a289ab042ae8510b021ab3dd468b323b7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.util.PaintUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 609 of bug id Chart1
### Patch Diff Hash-SHA-256:

a4d3bd1b0c76d932399289602f91b97650fea3d022c80aa87ed730cd3d17fd04

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (index - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 610 of bug id Chart1
### Patch Diff Hash-SHA-256:

9e3c5af1c0afba14eaccb3bbb9c008ed6b7d064f4fd2319e1115fc2cf156bd41

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < columnCount) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 611 of bug id Chart1
### Patch Diff Hash-SHA-256:

9a6fe7fd38be4935db6e4a83e20312b7d49d395094031956d52af82cb0141b64

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (java.awt.geom.Rectangle2D.OUT_TOP)) == (java.awt.geom.Rectangle2D.OUT_TOP)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 612 of bug id Chart1
### Patch Diff Hash-SHA-256:

fdb7501c22673b9bb905ca6a454f369b77d8ff623c6aa449ae60890212ca059e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > (org.jfree.data.time.Week.LAST_WEEK_IN_YEAR)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 613 of bug id Chart1
### Patch Diff Hash-SHA-256:

9328fbcbbb8ce4ee2799adcf9dd3f48ac11fe8992d10d86e7cbcdfe5e489a780

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (org.jfree.chart.util.Align.RIGHT)) == (org.jfree.chart.util.Align.RIGHT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 614 of bug id Chart1
### Patch Diff Hash-SHA-256:

036ad6d08cd5d11feacee290fc9cdf20ba107e2222b41520cf3af55074fd1cb1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((itemLabelGeneratorList.get(rowCount)) == dataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 615 of bug id Chart1
### Patch Diff Hash-SHA-256:

040c7e4a6cde115cab955a69ae7acb42be7c28e82a497ff7f21028c9f574f643

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index & (java.awt.geom.Rectangle2D.OUT_RIGHT)) == (java.awt.geom.Rectangle2D.OUT_RIGHT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 616 of bug id Chart1
### Patch Diff Hash-SHA-256:

e20035817bdf43ac3154ae1848cb8e405b045cafe2271e22fa76ed192c18ddc0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) >= 1) && ((rowCount) <= (org.jfree.data.time.SerialDate.lastDayOfMonth(rowCount, rowCount)))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 617 of bug id Chart1
### Patch Diff Hash-SHA-256:

1daf0f5c787122539aa4967dfd8115683e8f9aec189d6bdeb01aafc4ee8ce300

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.data.time.SerialDate.isValidMonthCode(rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 618 of bug id Chart1
### Patch Diff Hash-SHA-256:

7fea879db454a926e4017263f31e4f7b91a9bd3c1b8f017da3847cad7479720e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((plot.getOrientation()) == (org.jfree.chart.plot.PlotOrientation.HORIZONTAL)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 619 of bug id Chart1
### Patch Diff Hash-SHA-256:

38f02520bc168b2fc9c9c2fe530ab2c7008b1a1a509096947599bb7d272867ed

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (foregroundAnnotations.addAll(foregroundAnnotations)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 620 of bug id Chart1
### Patch Diff Hash-SHA-256:

61cc71026dc393ec8cd7cfc912610eef7f5918089859dc934394d1b3cd3e9da2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (urlGeneratorList.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 621 of bug id Chart1
### Patch Diff Hash-SHA-256:

9862552a12eeb382ff6e74a0101ef951b690297af771c5b0994b00a53531d12d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.data.KeyedValues) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 622 of bug id Chart1
### Patch Diff Hash-SHA-256:

05ed9f87eab2caf72ba97f65f4b2f5dfb0989ad7bca11cbdffbfc730deb7117a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index & (java.awt.geom.Rectangle2D.OUT_TOP)) == (java.awt.geom.Rectangle2D.OUT_TOP)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 623 of bug id Chart1
### Patch Diff Hash-SHA-256:

fd6e6469d21a07e4c78b839886bc42f86e9338c70f975ed86642841b548cd0c8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (java.awt.geom.PathIterator.SEG_CLOSE)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 624 of bug id Chart1
### Patch Diff Hash-SHA-256:

7a6059b40cc6b2fe3a3c5303af121967b03d37c0c6846246cf36f00494b442d2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.Second) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 625 of bug id Chart1
### Patch Diff Hash-SHA-256:

2f79e28fcc6d850cf6970a141cb18ce83f13c2138365fa722ae1d49832b6f113

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.RegularTimePeriod) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 626 of bug id Chart1
### Patch Diff Hash-SHA-256:

e8a41267cf1eadd15b42c7862a151dc0d352275ced28f5c8f70eb4dea619d5f5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT.isBold()) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 627 of bug id Chart1
### Patch Diff Hash-SHA-256:

fb4a84be162aff74917ee83425d1e18b6bcb7446b5fe1e781b46f26c9e85fc06

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.GeneralPath) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_SHAPE) instanceof java.awt.geom.GeneralPath)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 628 of bug id Chart1
### Patch Diff Hash-SHA-256:

8a245cf7dd286973dc73ace44246ebcc1895dcac469f6dbfc2f45d766ea37028

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof java.awt.GradientPaint) && ((org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT) instanceof java.awt.GradientPaint)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 629 of bug id Chart1
### Patch Diff Hash-SHA-256:

125da30c3679906d6f6d6cce1f2688e6d375c3ef66c4ddbf01b04ee228b324f6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.chart.renderer.xy.XYAreaRenderer.LINES)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 630 of bug id Chart1
### Patch Diff Hash-SHA-256:

cd6b982bd59a5e2a7f74ad3a9b2c37f68292e0fca01482e761d9cd1aff539002

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 631 of bug id Chart1
### Patch Diff Hash-SHA-256:

cf38f4360f5dc17dca0acc3e0888b7e2e3838ebede55b1be080536a0d95a4224

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.SpiderWebPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 632 of bug id Chart1
### Patch Diff Hash-SHA-256:

d5cafaf2da0cb1852f91e240f5c1a9670a896253946297091df682b240b2c42c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.SHAPES)) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 633 of bug id Chart1
### Patch Diff Hash-SHA-256:

39572cd1b31ab20e521d42197f4136fc648bd365f2ced15a5a5f3c4956629f88

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < (getRowCount())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 634 of bug id Chart1
### Patch Diff Hash-SHA-256:

92636d5fd0386e0ae31e5841c8db20c3564965372a6173e3c7a3364e4bfa8619

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (org.jfree.data.time.Year.MINIMUM_YEAR)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 635 of bug id Chart1
### Patch Diff Hash-SHA-256:

cd2b56ba5b75a793e5d8c1a0a3e1fcee66127f973959494c61646f7786289770

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index > 2) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 636 of bug id Chart1
### Patch Diff Hash-SHA-256:

be30738ec8f39f426a8e32073cef1f5123ebe0f430b3eceb1fd93dd6a75a4670

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.AREA_AND_SHAPES)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 637 of bug id Chart1
### Patch Diff Hash-SHA-256:

5d0290b1f1719b4ff4589338e26bbbac5180c7066a5fb4adc41915f7048d9507

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.data.time.SerialDate.INCLUDE_BOTH)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 638 of bug id Chart1
### Patch Diff Hash-SHA-256:

7d8219c2a4a0475eff1dd9f09afb38a33ade1f638a8281eff4c8b75585d13e3a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > (org.jfree.data.time.Quarter.LAST_QUARTER)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 639 of bug id Chart1
### Patch Diff Hash-SHA-256:

0b3653ae0f2e5262ca4e4b2e627ee518374ee7ff31b0a23b8941d2efdd4bb0a8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((foregroundAnnotations.size()) > 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 640 of bug id Chart1
### Patch Diff Hash-SHA-256:

94ae105c4c52d88999f61ed096dd2b7ab3149f82c78e10974711cb07ee6c8ffd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.general.SeriesChangeType) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 641 of bug id Chart1
### Patch Diff Hash-SHA-256:

cc3d1cd58c5088c2dbdf3800d4e61151e0978f78cc496742d92015806961ca2f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < rowCount) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 642 of bug id Chart1
### Patch Diff Hash-SHA-256:

b7c4b5a8ef7aa26fb44159e710d5a42022716b2c2cb044eb4c2c7cc16c1343e9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) >= 1900) && ((rowCount) <= 9999)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 643 of bug id Chart1
### Patch Diff Hash-SHA-256:

77c60a9d5e95f88ff322ce5b33aca2051d7c622106a37c60d3aff769c2eed448

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < rowCount) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 644 of bug id Chart1
### Patch Diff Hash-SHA-256:

62e8db0d147f2bc5fb9074ed03ec9d226c42ac10ccc3356a7740a722cfe01bb6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (rowCount)) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 645 of bug id Chart1
### Patch Diff Hash-SHA-256:

eaac79d63f5cfdfadfaacf791db5cdd0147cbff7408b3bb239565348e8fe7a4d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof java.lang.Number) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 646 of bug id Chart1
### Patch Diff Hash-SHA-256:

72e3167f995235a002892fd42a141047b852a52733e36a40ddbc78b73a90fe8e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (org.jfree.chart.util.Align.FIT_HORIZONTAL)) == (org.jfree.chart.util.Align.FIT_HORIZONTAL)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 647 of bug id Chart1
### Patch Diff Hash-SHA-256:

d83cd40d80eb92a063164080d28e5bc1247ee346a50e88bfc65c19e8d5e86cc9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < columnCount) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 648 of bug id Chart1
### Patch Diff Hash-SHA-256:

70c1ba67068fe72731f24a6e51a4d8350cc38adafd592e09beb9f1911f636439

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.IntervalMarker) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 649 of bug id Chart1
### Patch Diff Hash-SHA-256:

ac3cba9920a76bc72dcb775b04aad3fcefc654c5486cb651968b5a528ee8f1f6

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) < (org.jfree.data.time.Week.FIRST_WEEK_IN_YEAR)) && ((rowCount) > (org.jfree.data.time.Week.LAST_WEEK_IN_YEAR))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 650 of bug id Chart1
### Patch Diff Hash-SHA-256:

a909d4292f71f68e1b062eb26ad8b37fa19557c1e6084c613327ed9c8eae74e5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.dial.ArcDialFrame) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 651 of bug id Chart1
### Patch Diff Hash-SHA-256:

4cbb8b7dfb7d8eb584b957aa057a682d5386f31d97e33711aad284c1d8631c6b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.plot.CategoryPlot.DEFAULT_DOMAIN_GRIDLINES_VISIBLE) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 652 of bug id Chart1
### Patch Diff Hash-SHA-256:

7535530bae7d99dd622ba73e129b78d159655615ea8a00483b4d04faabfc3970

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == ((rowCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 653 of bug id Chart1
### Patch Diff Hash-SHA-256:

f574efd120033af598335a81c80604522ce9059a99da01f2872c0278d766dd2b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.data.time.SerialDate.isValidWeekdayCode(index)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 654 of bug id Chart1
### Patch Diff Hash-SHA-256:

74eee8694d8489c6e324b08521ba3b5b335f39b28b5af10d5435626dfb7e6a6f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.renderer.LookupPaintScale) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 655 of bug id Chart1
### Patch Diff Hash-SHA-256:

20f2f7abc7275637d863c08ae488eb85f2d03d464c335a08ed6c7bc156eefd01

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.PlotRenderingInfo) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 656 of bug id Chart1
### Patch Diff Hash-SHA-256:

c56b2ce11c33d5ca4c105469d20afd2f9e80615650a832bfd4bb220ff40e6e59

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemLabelGenerator) == null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 657 of bug id Chart1
### Patch Diff Hash-SHA-256:

e3c28f9b2f573d8cb7d2a28f95d8445b0979ac663479541e8395dbf930ddf4e5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) & (java.awt.geom.Rectangle2D.OUT_RIGHT)) == (java.awt.geom.Rectangle2D.OUT_RIGHT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 658 of bug id Chart1
### Patch Diff Hash-SHA-256:

ccb5efd51af8c08bb79838c8a2afb25ab4a34a3e16fed2cafcef0d7f58d753fc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == (org.jfree.chart.renderer.xy.XYAreaRenderer.LINES)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 659 of bug id Chart1
### Patch Diff Hash-SHA-256:

983d4e9198fd71534b40ac0f088123772e354ec1a512a6c5e80b298bb7d8267a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.title.CompositeTitle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 660 of bug id Chart1
### Patch Diff Hash-SHA-256:

0ef37e5d28a8dd063e7ab6b4a2706b3cf2b49b843bdee5a84c4ee2d961642c88

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index != index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 661 of bug id Chart1
### Patch Diff Hash-SHA-256:

36e14f11d0d12aea1ca5d46b367278e2ba2f37f5fd139c9c3cb51cbc74918bd1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(plot instanceof org.jfree.chart.plot.Pannable)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 662 of bug id Chart1
### Patch Diff Hash-SHA-256:

d03a6593672a5dca55cad78482617b83913a5fd08a7382f3fbecb882dbb94009

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.xy.CategoryTableXYDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 663 of bug id Chart1
### Patch Diff Hash-SHA-256:

8d5ba4b4a95be2ceeadd89ddfe6be30b50813e7ec42a10f43ff329931bc374a9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.data.time.SerialDate.INCLUDE_FIRST)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 664 of bug id Chart1
### Patch Diff Hash-SHA-256:

9de07cbab3a35e6c8363ec606be3c0d00d4f4281dc59e39c199be96f7a8a6f99

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.entity.LegendItemEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 665 of bug id Chart1
### Patch Diff Hash-SHA-256:

ed102fac9779d51c1496b504b92710272b85dcba53ba852a3c8131288e4a9ddb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.renderer.xy.AbstractXYItemRenderer) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 666 of bug id Chart1
### Patch Diff Hash-SHA-256:

467d5cb2eb1a687f521e97f212ff78534c4414dcebb60d865a8302b8f14fcf37

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.data.time.SerialDate.isValidWeekdayCode(columnCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 667 of bug id Chart1
### Patch Diff Hash-SHA-256:

cab0fce0b613a11a7f93db8a7d3e9ea990847f1dcc2e7e3a9092296338f51c26

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.IMAGES)) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 668 of bug id Chart1
### Patch Diff Hash-SHA-256:

34d3f29a50a07a7a4e60d5a4cc1b5801d62cb7cda945b8d7f463188c8cbb0ad3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) <= ((rowCount) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 669 of bug id Chart1
### Patch Diff Hash-SHA-256:

e51fcc1d0dfafbdf61468dab7fd871f084f5eeafabf1225c163327f58e471201

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.SHAPES)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 670 of bug id Chart1
### Patch Diff Hash-SHA-256:

31df82812da3ef5136f03a698200e2e79b2f50a3efe944ac0f5338503405d84a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.util.ObjectUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.ZERO, org.jfree.chart.renderer.AbstractRenderer.ZERO))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 671 of bug id Chart1
### Patch Diff Hash-SHA-256:

e98f22305cb1a302042bf23e2c44e72c736b341e641132bb2bdda3a5ad614968

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_PAINT))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 672 of bug id Chart1
### Patch Diff Hash-SHA-256:

22974b4b2ba95c6adcd1d8aa96c275136c35a66298705e0a1dd31d9fc0936c8c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) >= (org.jfree.data.time.MonthConstants.JANUARY)) && ((rowCount) <= (org.jfree.data.time.MonthConstants.DECEMBER))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 673 of bug id Chart1
### Patch Diff Hash-SHA-256:

ff1cff890e9f71625b4c876b98647f59aa53b374da4a8d70d7ad472abda4b602

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(getItemVisible(rowCount, rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 674 of bug id Chart1
### Patch Diff Hash-SHA-256:

b4a618508b6b0491aad4dba86122165e1ccf6f293dd9ee5059c652d2a239d714

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_PAINT))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 675 of bug id Chart1
### Patch Diff Hash-SHA-256:

e215234af6a077a6955be40f897ca22065f34d55b49041d7de9e51ad813972d3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 676 of bug id Chart1
### Patch Diff Hash-SHA-256:

9d22404bc5f8f55e138870d9d062561f0243bc526f48eed38993b0b9ed0f659b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (java.awt.geom.Rectangle2D.OUT_BOTTOM)) == (java.awt.geom.Rectangle2D.OUT_BOTTOM)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 677 of bug id Chart1
### Patch Diff Hash-SHA-256:

2c1402aa2de07bbf59d3d1529beb9402825a9899e1c3e2b30e1a816bae36efdf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) >= (dataset.getColumnCount())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 678 of bug id Chart1
### Patch Diff Hash-SHA-256:

fbd22989482dcde3e01d0d3849e1b5eb7f03be7e2d1b5970feda606fb240e096

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.PiePlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 679 of bug id Chart1
### Patch Diff Hash-SHA-256:

f580dd8b85b87041b714b454d9271694e33dfedad6c5119ca21f39f0ff9499c9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (org.jfree.chart.util.Align.BOTTOM)) == (org.jfree.chart.util.Align.BOTTOM)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 680 of bug id Chart1
### Patch Diff Hash-SHA-256:

5658c578a83e3081fe013cbcd1ed30d3452c8f2e2935b11b8de1aba4ca238f13

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.data.time.TimePeriod) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 681 of bug id Chart1
### Patch Diff Hash-SHA-256:

b936b44d64348137e1856d6363e21d0a0ad76eba843d12594327e03bc550bbe0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < rowCount) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 682 of bug id Chart1
### Patch Diff Hash-SHA-256:

008173d5922716af2ac65be04ee0e57d06f8c249e556111d16aaba4360b16e96

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index == (index - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 683 of bug id Chart1
### Patch Diff Hash-SHA-256:

e094f05d3fc6551e7a39aafe08d3643f7ba37e4ed487ced1beb8c2c4e26f26e2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) != (org.jfree.chart.plot.CompassPlot.NO_LABELS)) && ((rowCount) != (org.jfree.chart.plot.CompassPlot.VALUE_LABELS))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 684 of bug id Chart1
### Patch Diff Hash-SHA-256:

fc7e69dbf764e7654d97a372e29e0020918c9529d08689bb1b6d9b3dac264792

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.data.general.ValueDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 685 of bug id Chart1
### Patch Diff Hash-SHA-256:

0419463ac3c271b5456f130eb215d0550a508093b6d2e485c8dacd0a80795975

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(itemLabelGeneratorList.equals(itemLabelGeneratorList))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 686 of bug id Chart1
### Patch Diff Hash-SHA-256:

a72ee0f2665c037ac4395a3e3024e19447e84ee7064985c2afbdfc2cca8d43cb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (org.jfree.chart.util.Align.TOP)) == (org.jfree.chart.util.Align.TOP)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 687 of bug id Chart1
### Patch Diff Hash-SHA-256:

5cd95f814f2db68e1761b5b7dfc53f406cc12060a032db756b5fdf5801f1a6d3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (urlGeneratorList.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 688 of bug id Chart1
### Patch Diff Hash-SHA-256:

2106e2ee4dd83ea638905406fc1a03941249661160b0f15db790f6e772509d4b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index >= 1) && (index <= (org.jfree.data.time.SerialDate.lastDayOfMonth(index, index)))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 689 of bug id Chart1
### Patch Diff Hash-SHA-256:

cf3b9af69fabbbf98ea53709646eaefc14b7841074b4ab4e85770319eefa1634

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > 255) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 690 of bug id Chart1
### Patch Diff Hash-SHA-256:

3032d1ef25b74ffee1bd49f16d334c59e390a466caebaa9134e902109bc23182

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index & (org.jfree.chart.util.Align.TOP)) == (org.jfree.chart.util.Align.TOP)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 691 of bug id Chart1
### Patch Diff Hash-SHA-256:

8ce4e9e2d7b15a3be9d144b0d71c0380026410d2966179dc3a70a62858095b25

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.statistics.BoxAndWhiskerItem) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 692 of bug id Chart1
### Patch Diff Hash-SHA-256:

c324705e5a9a39cf5e66cf087a84b3b49cac38ea6243ba9c61ce37d66d6acf79

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) & (java.awt.geom.Rectangle2D.OUT_TOP)) == (java.awt.geom.Rectangle2D.OUT_TOP)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 693 of bug id Chart1
### Patch Diff Hash-SHA-256:

feac48a21533c3e8b6f3136661ed8763de2d74edc17f4f82ecdc58270ded3365

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) >= (org.jfree.data.time.SerialDate.SERIAL_LOWER_BOUND)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 694 of bug id Chart1
### Patch Diff Hash-SHA-256:

d6034e70742dde9ecd4b58b44e59b824b61339ebcb4fcc2b6ed0df5e1779c573

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(urlGeneratorList)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 695 of bug id Chart1
### Patch Diff Hash-SHA-256:

87d770205a21c0521f9c0ae9505edbdb2ff40c19fc706d7b5137899b5a3a853f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.axis.ValueAxis.DEFAULT_INVERTED) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 696 of bug id Chart1
### Patch Diff Hash-SHA-256:

bb72c2329fd4f2a486bfa5924f05f8e10b29c6a4e78bb00d7c718477af5b3106

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.chart.renderer.xy.XYAreaRenderer.SHAPES_AND_LINES)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 697 of bug id Chart1
### Patch Diff Hash-SHA-256:

8d3c1e5e4b8cc172389ce3aa3dfa1613ed081b282b730635708c063390d63685

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) > (rowCount)) && ((rowCount) <= (rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 698 of bug id Chart1
### Patch Diff Hash-SHA-256:

491b50f31b62d0f5ca4797a903772901b412e309ead04667fb4398c34da2427a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.renderer.AbstractRenderer.ZERO.isNaN()) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 699 of bug id Chart1
### Patch Diff Hash-SHA-256:

c4382af02677fc0972a6878c2695c22470a8236a9feee447357ed8e718ce75f1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.renderer.category.StackedBarRenderer3D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 700 of bug id Chart1
### Patch Diff Hash-SHA-256:

40334428be5da1e9469f4b98538d7b47cb2e5c7f72669423a3e7a3a7fc078257

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index & (java.awt.geom.Rectangle2D.OUT_BOTTOM)) == (java.awt.geom.Rectangle2D.OUT_BOTTOM)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 701 of bug id Chart1
### Patch Diff Hash-SHA-256:

aa7ec719a3fbf1beb403049c47060b546d66f876508e79cb7d5f398dcb3b5bf8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < (itemLabelGeneratorList.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 702 of bug id Chart1
### Patch Diff Hash-SHA-256:

019bdb082bacfd9a4533750a84a2e03cc14d986843c716e6446eff46322c1ec9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index >= (org.jfree.data.time.MonthConstants.JANUARY)) && (index <= (org.jfree.data.time.MonthConstants.DECEMBER))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 703 of bug id Chart1
### Patch Diff Hash-SHA-256:

acc11088b7a6c5dec9c9c63b80d1ecfec5d50cd2cb162121d016e308c77f8aab

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.plot.CombinedRangeCategoryPlot) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 704 of bug id Chart1
### Patch Diff Hash-SHA-256:

03d4c60b52e0b2e8166fb04848d587922517673f1b2d97bca1da72e6f196b21c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.AREA)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 705 of bug id Chart1
### Patch Diff Hash-SHA-256:

66812bb15ebfbd32ff6a88aef2f4ebb1bcac72ec75c5d45316e83cffab1e34c8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((columnCount) & (java.awt.geom.Rectangle2D.OUT_BOTTOM)) == (java.awt.geom.Rectangle2D.OUT_BOTTOM)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 706 of bug id Chart1
### Patch Diff Hash-SHA-256:

141607861b58866c824a322b2bbbf323d9bd81a261f2f10f0f9e4af25766e268

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (org.jfree.chart.plot.CategoryPlot.DEFAULT_CROSSHAIR_VISIBLE) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 707 of bug id Chart1
### Patch Diff Hash-SHA-256:

2a5505edebcd75430bd5f7aaf8b1667c2760c819fb6ccbf6d870403ca92f0de9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(dataset instanceof org.jfree.data.KeyedValues2D)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 708 of bug id Chart1
### Patch Diff Hash-SHA-256:

dc32103ac3a34bbc58a5fde1810dd6063dea1baa4945cecb9b008c69d2a1a890

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.title.ImageTitle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 709 of bug id Chart1
### Patch Diff Hash-SHA-256:

f876c1112fe74f642ed8b23262cd8797156a58e11f3f565bcfd53e367cb2e73a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(legendItemLabelGenerator)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 710 of bug id Chart1
### Patch Diff Hash-SHA-256:

255cd743d62243ba88903fafff85ceb3e1df3f0d2d655d7e714f1583db0603cf

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) == 2) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 711 of bug id Chart1
### Patch Diff Hash-SHA-256:

b9500f006fe3162dc906add174ceb7f8b66d56e236d088d08b30f9b5c6275754

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.chart.renderer.xy.XYAreaRenderer.AREA_AND_SHAPES)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 712 of bug id Chart1
### Patch Diff Hash-SHA-256:

2149376776d84c2aaef8ce632678ebda252bed18495c2328ff7e61b0e1adaf26

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < (foregroundAnnotations.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 713 of bug id Chart1
### Patch Diff Hash-SHA-256:

6f4db16ae0676fef4bc0f623fbc6cece09d57cf670240f9933fa30830da4a9f4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (backgroundAnnotations.remove(org.jfree.chart.renderer.AbstractRenderer.ZERO)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 714 of bug id Chart1
### Patch Diff Hash-SHA-256:

05df16d561962632e6e238c93440acd23495bc3281a4c2c412bb46c69d1a91f2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.ohlc.OHLCSeriesCollection) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 715 of bug id Chart1
### Patch Diff Hash-SHA-256:

62f12b239f955563ddf90ac1c79b4b70dd884767f36d68d5da67e74ade4a44c8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.data.category.CategoryDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 716 of bug id Chart1
### Patch Diff Hash-SHA-256:

5a371526001c3b48c0b8b1dd99a5a7408eedc3ffb7717708c6d86894c6507762

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) < (org.jfree.data.time.Year.MINIMUM_YEAR)) || ((rowCount) > (org.jfree.data.time.Year.MAXIMUM_YEAR))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 717 of bug id Chart1
### Patch Diff Hash-SHA-256:

b30591a3536464d4c6444b0e7f91608d63691f5013d393ed1c32e4144f169418

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.axis.CategoryLabelPositions) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 718 of bug id Chart1
### Patch Diff Hash-SHA-256:

5d7c71ed49631579d438361426aecbe78051e8227a6f8f3841d956929a264290

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(backgroundAnnotations.equals(backgroundAnnotations))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 719 of bug id Chart1
### Patch Diff Hash-SHA-256:

1520f62b5324d0639243f75a4ca4bc346379547f60fb9899380250dacdc4a9e7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) > 360) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 720 of bug id Chart1
### Patch Diff Hash-SHA-256:

a4f8f82bfbde65b42b0d5201773a6366883538741da8627e2bd103bbf2c14947

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) == 0) && ((rowCount) > 0)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 721 of bug id Chart1
### Patch Diff Hash-SHA-256:

c166f1cfd912561b16018356578b0343c1557c854b1b5e4df4212f0c485a91a1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) != (org.jfree.data.time.Millisecond.FIRST_MILLISECOND_IN_SECOND)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 722 of bug id Chart1
### Patch Diff Hash-SHA-256:

535f7dfde518e4379f9ab8f6e6a7b4e3a6ec68c94dd78d254deca0ba0d2027f3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (isSeriesItemLabelsVisible(rowCount)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 723 of bug id Chart1
### Patch Diff Hash-SHA-256:

86790f446ef0ba498c62ce9ed390330edd55d45cb7fa7231a1d7179f05283834

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.util.ObjectUtilities.equal(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT, org.jfree.chart.renderer.AbstractRenderer.DEFAULT_VALUE_LABEL_FONT))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 724 of bug id Chart1
### Patch Diff Hash-SHA-256:

5d86b007f63abc352876107ad61246cab7269d5295384fe5a5b41aec406ce58c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(plot instanceof org.jfree.chart.plot.Selectable)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 725 of bug id Chart1
### Patch Diff Hash-SHA-256:

824b88beda37e082c774cb3c2a11cbe42de520c6b47760b89123c1a6bd55d0cb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) - (rowCount)) > 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 726 of bug id Chart1
### Patch Diff Hash-SHA-256:

8bafb194b39ff9a038233c6b36d541dea4e788738173df78acab667391d98ecc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof java.lang.Comparable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 727 of bug id Chart1
### Patch Diff Hash-SHA-256:

e03f64d61a16708a14d23dd1c0a4ff7dde447edd1bbeb528f3aa1ead5cd55c44

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (java.awt.RenderingHints.VALUE_ANTIALIAS_OFF.equals(dataset)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 728 of bug id Chart1
### Patch Diff Hash-SHA-256:

d9a52b9de6505b6af933084f913d90eb2c6f633d55ab1cb18aee1e50d4d372de

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.labels.BubbleXYItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 729 of bug id Chart1
### Patch Diff Hash-SHA-256:

107452f6752c9a63ef186bffe5bec8a252269104038e88d4cdca464ea97548ed

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) >= (org.jfree.data.time.SerialDate.SERIAL_LOWER_BOUND)) && ((rowCount) <= (org.jfree.data.time.SerialDate.SERIAL_UPPER_BOUND))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 730 of bug id Chart1
### Patch Diff Hash-SHA-256:

e92fc18537974b789f5bb4adac133d8dbbc8c905612969b31e7c62bdc88ac8b4

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.annotations.XYShapeAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 731 of bug id Chart1
### Patch Diff Hash-SHA-256:

866cbfd06bb3f66ff2f61d6954319dc0209d979021ea42a7e0f1b28fb2195f12

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.data.pie.PieDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 732 of bug id Chart1
### Patch Diff Hash-SHA-256:

7f994aa492ffc334ff55751d127eee21fbd5f05608c59e71a3768d3c83a52429

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((backgroundAnnotations.size()) > 1) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 733 of bug id Chart1
### Patch Diff Hash-SHA-256:

267873445af3f0efdd442d9f6507f124fe6bd3033e06348168f9a115edc9f6cc

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(result instanceof org.jfree.chart.LegendItemCollection)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 734 of bug id Chart1
### Patch Diff Hash-SHA-256:

9fe28336edb8c76521a7604a99de4c51cc9ee837b88798303fa0d691c309fd16

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < (result.getItemCount())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 735 of bug id Chart1
### Patch Diff Hash-SHA-256:

e9e66c08e059ccfe3f8f8d3909ae3475302e960a84073ef1152cdb00394bac2e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) == (-1)) && ((rowCount) < (rowCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 736 of bug id Chart1
### Patch Diff Hash-SHA-256:

fc5eb2b056a7ce667abb3681df208ebb9b2a3c6409d2b0e5c97a08e2ef35ff84

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > 12) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 737 of bug id Chart1
### Patch Diff Hash-SHA-256:

5d0f7ef49e22988f5453ae6845e209ac09c26cc2a2cb172de5a7c800262490f7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((itemLabelGeneratorList.size()) > index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 738 of bug id Chart1
### Patch Diff Hash-SHA-256:

dbaadec1baddac0ead906f58af892a3057953cfe24cbb9f815eabc21a16e2320

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(result.equals(result))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 739 of bug id Chart1
### Patch Diff Hash-SHA-256:

9863567f64ea69093920a609a373a7a94f15852730712b135714b6d6ae17c326

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.needle.ShipNeedle) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 740 of bug id Chart1
### Patch Diff Hash-SHA-256:

7d77aea02a3668275efe64647f67c066ce7d42e30cc1a6bb25da6701448bd6a8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.chart.block.EntityBlockResult) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 741 of bug id Chart1
### Patch Diff Hash-SHA-256:

f15cfdc78bebfff38385bf63806395d0fc39f4255f16c4cd5913abe9c40e716a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.data.general.KeyedValueDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 742 of bug id Chart1
### Patch Diff Hash-SHA-256:

084ca70b3115c42f6d14c83cf19c378a841459d7e8a93ecd1972e1a13381eb29

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.axis.NumberTickUnit) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 743 of bug id Chart1
### Patch Diff Hash-SHA-256:

692c89e63b6ce7ac9adc7f7fe7ea6b29045d27e39d035b903331b30dcacea449

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) < ((dataset.getRowCount()) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 744 of bug id Chart1
### Patch Diff Hash-SHA-256:

4448ac02ec9b11d337c35afd5007d1fdaf8af6195a24ea7185f81cbe2dea364f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.Month) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 745 of bug id Chart1
### Patch Diff Hash-SHA-256:

fd15fbd15ec01d176fe4a40f2e22b7d80e4f543b3b55ab07f481eb5ec0bdcaf8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.function.PolynomialFunction2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 746 of bug id Chart1
### Patch Diff Hash-SHA-256:

e3ca9ecea46174c3d7214a2025f44558b4573d7dc31c70087ca8510d2d7dc1b3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (java.awt.geom.Rectangle2D.OUT_LEFT)) == (java.awt.geom.Rectangle2D.OUT_LEFT)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 747 of bug id Chart1
### Patch Diff Hash-SHA-256:

bf24d39519c7234ab13a8860c6b91b894a5c5470f4bbe4a3ce4358a3684ab5b8

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) == (rowCount)) && ((rowCount) > 0)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 748 of bug id Chart1
### Patch Diff Hash-SHA-256:

0f964e891f37c1b3fc585cc353cb9d21959fd680726267cc634270baeba46e18

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((urlGeneratorList.size()) > index) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 749 of bug id Chart1
### Patch Diff Hash-SHA-256:

95b57cf56aa4272daf207255cc16e82c7496fa3185773661506f1dc4840731f9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) * (rowCount)) > 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 750 of bug id Chart1
### Patch Diff Hash-SHA-256:

c038e00b28ea7a5ae28d16732657f429670ff27e29241e0a25a507e4522c99df

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (index < ((dataset.getRowCount()) - 1)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 751 of bug id Chart1
### Patch Diff Hash-SHA-256:

ffee9c8f654d0632ef300ca62d753f6c7c61e11ddf470557a029bf2c02cd2257

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (result instanceof org.jfree.chart.block.EntityBlockParams) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 752 of bug id Chart1
### Patch Diff Hash-SHA-256:

dc97bdd4134703a4080dcf65c5999553862b01763af1c76b5955c02ee02dbd34

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.Minute) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 753 of bug id Chart1
### Patch Diff Hash-SHA-256:

671ea0140f82bc84fb560144b3c62a1fb2b41f307284c73de03a8b493c125de1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(org.jfree.chart.util.ObjectUtilities.equal(result, result))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 754 of bug id Chart1
### Patch Diff Hash-SHA-256:

5f5d5d5aa368b00fe5c382e685caf40476d44be06f3a9beec86a7cc8dad1c04c

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.function.PowerFunction2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 755 of bug id Chart1
### Patch Diff Hash-SHA-256:

9b130e5a6f05e9144cc19716fdbbfcea08042d857b99792966fb52f4a80c424b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.Quarter) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 756 of bug id Chart1
### Patch Diff Hash-SHA-256:

4b30c6a054f0315ed174c4e01cef9345bac7ba0b32e60d248a0b26f29ec0f1c0

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) == (org.jfree.data.time.SerialDate.INCLUDE_SECOND)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 757 of bug id Chart1
### Patch Diff Hash-SHA-256:

a34fb820779175173addf4d7acc71cebf650745acff448ec76f055e3667d21be

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) < 0) || ((rowCount) >= (dataset.getColumnCount()))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 758 of bug id Chart1
### Patch Diff Hash-SHA-256:

1d4433ca24017c1c2477c28592b30ef32592775da660f068167cfeaee8af38f7

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((index == index) && (index > 0)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 759 of bug id Chart1
### Patch Diff Hash-SHA-256:

970e3c49695d0c910bc6e52548a5ef570d0870308c38b4b74374b076cab2ea05

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.time.TimePeriodValues) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 760 of bug id Chart1
### Patch Diff Hash-SHA-256:

5b1e9cc2cb50b3d2846bc5b02b278d61cb2a3da3fdd9442d31829716bbbbd82f

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (getTreatLegendShapeAsLine()) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 761 of bug id Chart1
### Patch Diff Hash-SHA-256:

bcdc997678ccb9dff550b65e18282318acd59cbff93bf91fb3b517567f889a4e

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.annotations.XYTitleAnnotation) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 762 of bug id Chart1
### Patch Diff Hash-SHA-256:

10a276d71e359f8e2cca3d5fc4547b19b4add26b84ab9990b6f2897f283bd2e3

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((rowCount) > (backgroundAnnotations.size())) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 763 of bug id Chart1
### Patch Diff Hash-SHA-256:

07d74bcdb10598583248672283bba0f6a384d635111ab06a5ca3579e393716fd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (((rowCount) & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.LINES)) != 0) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 764 of bug id Chart1
### Patch Diff Hash-SHA-256:

1a036def3cf7b66ed0abf833f49c30a653628f4a24d9fcbadeaf058bd0f4d026

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.entity.AxisEntity) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 765 of bug id Chart1
### Patch Diff Hash-SHA-256:

dd0f6d314b96cd2c5d292f33a9ae4a6ba6042f94345a700e61c87d4111a91935

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.pie.PieDataset) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 766 of bug id Chart1
### Patch Diff Hash-SHA-256:

bb79ce451cbc57ef96f2a4c8cf9fc4e5b93ca7d86ecd7adc2fd34148ce7cd825

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((columnCount) < columnCount) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 767 of bug id Chart1
### Patch Diff Hash-SHA-256:

6458b24379ccc079da68f61d1327993d7a2837f7f4b59df8092ab5a8de141d5b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.data.KeyedObjects2D) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 768 of bug id Chart1
### Patch Diff Hash-SHA-256:

b1b3833b36a96b085d02642387d4df0792772f470ea3b87f0f53fffd38d304b1

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (dataset instanceof org.jfree.chart.labels.StandardCategoryItemLabelGenerator) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 769 of bug id Chart1
### Patch Diff Hash-SHA-256:

1e28a6e06588acaee4ac991def82e93265c3122639007d2d0823c2fa910eee20

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!((0 == (rowCount)) && (0 == (rowCount)))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 770 of bug id Chart1
### Patch Diff Hash-SHA-256:

12f4780c0c349324c6f8952f1bd74653074194f94880e0d1695b60c7d3895016

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(isSeriesVisibleInLegend(index))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 771 of bug id Chart1
### Patch Diff Hash-SHA-256:

6e2392ad71c42e01a8421e358de91cdd770f9b09646f5ec97c25d374d0b1ca38

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseURLGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 772 of bug id Chart1
### Patch Diff Hash-SHA-256:

d87ffcbe3c81eb0d7edb0a977786827013e1e8cb955f1d1820ca8561b09cf978

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemToolTipGenerator) != null) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 773 of bug id Chart1
### Patch Diff Hash-SHA-256:

6ab5267335ffc94b270384bada5d6490b4f2e19b3345116678bd8abe9b034c82

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(isSeriesVisibleInLegend(columnCount))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 774 of bug id Chart1
### Patch Diff Hash-SHA-256:

0deb3cd3de50fd2b82571d171666629a2e51a58ca313072d5f8085b4c718d7b5

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((legendItemURLGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 775 of bug id Chart1
### Patch Diff Hash-SHA-256:

c41bfe2c875847d479b09c9cbbdf0f1b4a60b24ea19a4f8941a4b064762bc56d

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseItemLabelGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 776 of bug id Chart1
### Patch Diff Hash-SHA-256:

8388eddd51425583f7b15d394a66f2fc8a75a2e56428e98b45ccb3a17ba998b9

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if ((baseToolTipGenerator) instanceof org.jfree.chart.util.PublicCloneable) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 777 of bug id Chart1
### Patch Diff Hash-SHA-256:

598ecbf2db1be22a5d8db620c6cb6597fa2f2e6e162924bc772fbc1344d32060

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (!(isSeriesVisible(index))) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 778 of bug id Chart1
### Patch Diff Hash-SHA-256:

2bcfc06cf605937a5199af42dcb26c83fe4d97693f4f1dbaf1374fcab08a553b

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(backgroundAnnotations)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 779 of bug id Chart1
### Patch Diff Hash-SHA-256:

d4797196950b3d60ef3974a189cf3e19c8ee5f7abb49b87743095f97e9ae9a73

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_STROKE)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 780 of bug id Chart1
### Patch Diff Hash-SHA-256:

0df8c11c64815e12da2bc3c7e08ce8f5df7f2db4d8ea558a3b055185a37127e2

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
+++ /fixed/org/jfree/chart/renderer/category/AbstractCategoryItemRenderer.java	
@@ -766,7 +766,7 @@
 		}
 		int index = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getIndexOf(org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this);
 		org.jfree.data.category.CategoryDataset dataset = org.jfree.chart.renderer.category.AbstractCategoryItemRenderer.this.plot.getDataset(index);
-		if (dataset != null) {
+		if (super.equals(org.jfree.chart.renderer.AbstractRenderer.DEFAULT_OUTLINE_STROKE)) {
 			return result;
 		}
 		int seriesCount = dataset.getRowCount();
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---