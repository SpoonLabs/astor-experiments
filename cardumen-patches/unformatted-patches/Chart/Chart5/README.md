
# Patches of Chart5 from Defects4J 
Total patches 700
## Patch 1 of bug id Chart5
### Patch Diff Hash-SHA-256:

b38579ec36dca4816d0aaa6acdab8e10e7b4c1e0cb350967c3a9e4ebe1b29af7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((maximumItemCount) < 1) || ((index < 1) && ((maximumItemCount) < 5))) || ((maximumItemCount) < (4 - index))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart5
### Patch Diff Hash-SHA-256:

e51a568d605970c15ddba4383cc8efde02db992a2055d06d1c67f31704d2bf5c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (!(allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart5
### Patch Diff Hash-SHA-256:

3c38a9ac431ac590ce8e28c7c9288fd8dece8ad4d6dba7cb497b865bc775dd0e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index >= 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Chart5
### Patch Diff Hash-SHA-256:

67499d677d90473adcad57303aab9d77cf028d06612b3ba3686faa85a052d4c0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.CategoryLineAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Chart5
### Patch Diff Hash-SHA-256:

b9bdae62f97e05aa46ad2f40dd58e19f67a9626b0af52c939d1b755faf2c1267

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -207,7 +207,7 @@
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
-			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
+			if (autoSort = false) {
 				org.jfree.data.xy.XYSeries.this.data.remove(0);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Chart5
### Patch Diff Hash-SHA-256:

ec3f990604b4bf0627880999cb8298fa70e439f6061a279b06319f2e4f7991ca

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Chart5
### Patch Diff Hash-SHA-256:

bebc9e5bccb801352354090191d3b720baf4e9c5762a837612f46b43c043efd0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > 2) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Chart5
### Patch Diff Hash-SHA-256:

13c98bf4abefd531c89e7938e73c9540b59f70560758ce033efe4b1d257890b7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index < index) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Chart5
### Patch Diff Hash-SHA-256:

c783593101c0473fdaf2dbfd40ea33cb864eea102dfce3973f73654be5039357

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == 2) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Chart5
### Patch Diff Hash-SHA-256:

87913d9222aaf8347de9f19f11e9b2cb143a40794c7f90480c5d5d947ac60e04

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) == null) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Chart5
### Patch Diff Hash-SHA-256:

add0fb4903d11f30aa6ab41c71b5817ac3b9908ed938d9386c4ec6f13af7c4cc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < index) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Chart5
### Patch Diff Hash-SHA-256:

8c91abbbd683329caa99e84110cba5791288ca85b04806154a2bc0919441e94b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.CategoryPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Chart5
### Patch Diff Hash-SHA-256:

6f7a574976a87e14ee39756d0df6d37c092d624a7eff9bf448c5b1208dc89929

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((!(allowDuplicateXValues)) && (!(allowDuplicateXValues))) && (!(autoSort))) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Chart5
### Patch Diff Hash-SHA-256:

c2359bd0a47dcba5f2263e829f605a5c2ee44ede7f974499d2fa5525189f7068

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.data.KeyedValues) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Chart5
### Patch Diff Hash-SHA-256:

3d56df4cc1bb158ab58a3133d77b012a0613ed572d17bcbc64e75555faa02ff2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYBoxAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Chart5
### Patch Diff Hash-SHA-256:

a71b9bafe14333451d2c36a179c586c920cacc7cd3f42167b9d444171b489544

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Chart5
### Patch Diff Hash-SHA-256:

b76cd01fe2a2e900e468e9bbc563e5853fac32d1695b0682f3f3f848793d89b5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.general.PieDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Chart5
### Patch Diff Hash-SHA-256:

d848b26cf3b691b879000300534e2a974f9f66d7d686eba001fc711d2755fb01

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y == null) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Chart5
### Patch Diff Hash-SHA-256:

f632e0960704e53058c853202dd31fd1b9e18749212f262260723c25af0e3606

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == (-1)) && ((maximumItemCount) < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Chart5
### Patch Diff Hash-SHA-256:

78c4a8a958bcef7eb05ddfba11be4d2373a761a8e7c9709defa2fa97335c80fe

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.DefaultStatisticalCategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Chart5
### Patch Diff Hash-SHA-256:

daefd60fcdd355cad9ebb7035afe04e6f149d39ea057b29679407398f7734633

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (false) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Chart5
### Patch Diff Hash-SHA-256:

0333037ba2308a1ae334f1c20ccc1e7c7b68dc84b883e4608bcaf750fb5b216b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.OHLCDataItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Chart5
### Patch Diff Hash-SHA-256:

7e9331aa3be14401c5e598dd51a7ef66e4f0cf570731c467c92b684f28b32f20

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten != null) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Chart5
### Patch Diff Hash-SHA-256:

391388e8757fb0f92a60c0eaebc8942837b3614958a92dbb96fa1b93ad383a6d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.PublicCloneable) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Chart5
### Patch Diff Hash-SHA-256:

6e1f31a596edef3410560d465d65797f3602ad64aa73c83087dfaf742504a503

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x.equals(y)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Chart5
### Patch Diff Hash-SHA-256:

8992b87167b2c2d933e928aca48067bd9d137f672c0098370b94ef994a25ddbf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.MonthDateFormat) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Chart5
### Patch Diff Hash-SHA-256:

337dcc33d458c88796ddb955f74c5a8fd95b33eabcec693d215ce2c7923859d6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.LineNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Chart5
### Patch Diff Hash-SHA-256:

67c1f681fa95a8892d8553233f9cc66bb9f2ca12fb74e5f18b330223a7259af1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 3) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Chart5
### Patch Diff Hash-SHA-256:

d941244b1ffdb2cdea36400cd7c74e3ed207c3370999e9245c138d3e7e46c4cc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index * index) > 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Chart5
### Patch Diff Hash-SHA-256:

3c175477132447aec112a9ed5851da4db49b1fd816aa4055682d44631baf28b3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (!((0 == index) && (0 == index))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Chart5
### Patch Diff Hash-SHA-256:

7702e00c80ee8acc05fe04491de1e4f8fc3182ce0a31179b4165ce32f48e6337

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= (-4)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Chart5
### Patch Diff Hash-SHA-256:

19c6ab006f8d60a1cd0d49a0af5139e5003ea0c5c6439818b3a168a60ab1deae

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(autoSort)) && (!(allowDuplicateXValues))) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Chart5
### Patch Diff Hash-SHA-256:

6af98d3bdabea902e94860081f915f7a2e8f544c97b21cf6a21c0a858fce285c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.CategoryAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Chart5
### Patch Diff Hash-SHA-256:

db49d1a49c389ba6fe3bea4d10b46576f333eea3a68ab2507d1a0b0e3da71634

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) * index) > 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Chart5
### Patch Diff Hash-SHA-256:

7364d24977c286e82c9b4e1159bddeb80a404eb4c3eaee49ea6c6a4700b425b3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(allowDuplicateXValues)) && ((x.doubleValue()) < (x.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Chart5
### Patch Diff Hash-SHA-256:

1b9200dc0f3fff274455caa3d016e771b5077c84d357b1beef3d414524ac6705

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.KeyedObjects) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Chart5
### Patch Diff Hash-SHA-256:

636db6827cc6f19cdaad014d3d7c7c6d2c3ef3be1849740e5ccba3e4fff41a95

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.ValueMarker) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Chart5
### Patch Diff Hash-SHA-256:

5fec78a87fb758258e814e8ed7de949d656d59efca898f943a04cdad5fde5b09

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Day) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Chart5
### Patch Diff Hash-SHA-256:

debdebaed94044f0045832377890962b3724120ca737105e424cd05839070836

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.CategoryTick) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Chart5
### Patch Diff Hash-SHA-256:

3616f81c720a32144ea63e95b172dd70d48c96b2643ec6e735d984b7b35d46aa

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Chart5
### Patch Diff Hash-SHA-256:

7286e7e62997485f15f267746f85931637cee382378682a5b8dc9f9ea770aa1d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (super.equals(y)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Chart5
### Patch Diff Hash-SHA-256:

597d1ad528956acec0e1631e29129471aa92d095c05bbb426c3f89804f1b35e0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(autoSort)) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Chart5
### Patch Diff Hash-SHA-256:

507df41e8779de022a2833b1d7187306613a870527a9fda21d6fdd42fb4644c8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (-1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Chart5
### Patch Diff Hash-SHA-256:

40aa65a7c0fa37bffc3fb861ebdc3cd2e6f955e2dd5d59ef85a2a59ac69d3872

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -216,7 +216,7 @@
 	}
 
 	public int indexOf(java.lang.Number x) {
-		if (org.jfree.data.xy.XYSeries.this.autoSort) {
+		if (autoSort = false) {
 			return java.util.Collections.binarySearch(org.jfree.data.xy.XYSeries.this.data, new org.jfree.data.xy.XYDataItem(x, null));
 		}else {
 			for (int i = 0; i < (org.jfree.data.xy.XYSeries.this.data.size()); i++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Chart5
### Patch Diff Hash-SHA-256:

41d6831557d11ccf55033428b70aa83a70709e8c1baa2a0022b8e7055351ebf3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((getItemCount()) == 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Chart5
### Patch Diff Hash-SHA-256:

40290e341efe1b9847c8c9d05c4d2966278bef9f8cd584364361fe2658768323

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= (maximumItemCount)) && ((maximumItemCount) < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Chart5
### Patch Diff Hash-SHA-256:

d6107b9e1e37fdeea6a6999a0b8b9b229167f2f9af2cf1392fbfc5a15110fffb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.data.category.CategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Chart5
### Patch Diff Hash-SHA-256:

37d34e7db835f60e307bbc7b028a08c14eab8a38895587e6f4f53174e8c6df72

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.data.general.PieDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Chart5
### Patch Diff Hash-SHA-256:

41ef125b4b2ca5f1e6b06c9f306b846cd59ba5437a54a72eb9dc0c724ddd3a84

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(allowDuplicateXValues)) && ((x.doubleValue()) < (y.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Chart5
### Patch Diff Hash-SHA-256:

0d72043623972f25b3d2f1efcb9437b9ff124501794c06b5c7fdd4510876b328

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((0 == (maximumItemCount)) && (0 == (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Chart5
### Patch Diff Hash-SHA-256:

9ca6dbafaf84d6b343d52ccb836b027c25f104bd29a0670df2093e54d675d2d7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialPointer.Pointer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Chart5
### Patch Diff Hash-SHA-256:

1a9e44f77ae90784457b71def62531c7f116750aacf2cc931c16c42acd9963e7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Chart5
### Patch Diff Hash-SHA-256:

d0924fe2d01438ed02d5025125b28e7660e82ba725c6c1653e9712ca1d62edb3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == ((maximumItemCount) - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Chart5
### Patch Diff Hash-SHA-256:

3d7a5849745815a940cba1019ef465ece48b3bc48a1140a77ac6e6123ff10bd5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= index) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Chart5
### Patch Diff Hash-SHA-256:

df817806e1cde46b7d9a77e6c8379537d6dde2cccfdb0480d05c39fb05b4fb43

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.SegmentedTimeline) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Chart5
### Patch Diff Hash-SHA-256:

deedf149585e45be1e585eda25920dad6e71937c0411a9d27deffcb96443484f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) > (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Chart5
### Patch Diff Hash-SHA-256:

1143a50a1f27b71c3a5bc629ef21f6b10041de55ea2ef2c2445c1fdfa53fb843

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.title.ImageTitle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Chart5
### Patch Diff Hash-SHA-256:

4c488050d3b46694e01f93b2177bae986b0881373d8d4b3cd45f0716518a49a5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.MeterInterval) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Chart5
### Patch Diff Hash-SHA-256:

9d34f1709d4a5ab22b6422228192ea375f7f8ba14a950fe0a47a049b82752677

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == ((maximumItemCount) - 1)) && (index != 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Chart5
### Patch Diff Hash-SHA-256:

1723f5147651fc4c50f03ccc574e203065889e08e2baea52a990724b5df27ea9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (super.equals(overwritten)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Chart5
### Patch Diff Hash-SHA-256:

80547af4949a9e70f931194687e73a2240dae21c6a179e02299d95ef3df92bba

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 12) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Chart5
### Patch Diff Hash-SHA-256:

1b8e55104e12f0bd97f7513f6d9d7c718ef243973599ac5c061c0e500755d9f8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == (-1)) && (index < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Chart5
### Patch Diff Hash-SHA-256:

439572fd33e50ea7b118ddf34fbf2651cfae4a951b3af4cb76c7c45f55ca33ac

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == 0) && (index > 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Chart5
### Patch Diff Hash-SHA-256:

e6ffdcc5f31d02d2dd0a2e239d255b9257ace81342aa8a1e2f7ecab618a537e5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Chart5
### Patch Diff Hash-SHA-256:

b62cc9e1d971f9a2c484145ed9ab6eadaf029666783bc32896a6dad58072756c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((maximumItemCount) < 1) || (((maximumItemCount) < 1) && ((maximumItemCount) < 5))) || ((maximumItemCount) < (4 - (maximumItemCount)))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Chart5
### Patch Diff Hash-SHA-256:

7aebd27e0dcf647edd560458fa3414d64c496af8a6a9c0cd737fb63ae5d6978e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (!(y.equals(y))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Chart5
### Patch Diff Hash-SHA-256:

9af2c338836b0df29647dbc6eeee9fce53b5dd9f787636714f6984674d4345a7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= 0) && ((maximumItemCount) < 3)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Chart5
### Patch Diff Hash-SHA-256:

a7c354d3f334217d4cd768385314f98d4f245c9f06a7571f6fa95f4e1a0867ca

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.IntervalXYDelegate) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Chart5
### Patch Diff Hash-SHA-256:

9556d269a732f547e5a89b17565a6bf9cf37cfce210d6d2b4a49fffb067ef38b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 4) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Chart5
### Patch Diff Hash-SHA-256:

a284c7e124a83ccee6f2016aa9f0fa057eaeea1cc4c89e1aa7edcbb83464865e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.ExtendedCategoryAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Chart5
### Patch Diff Hash-SHA-256:

46dd2e342b5def6e8e925f09c4537e5c45548ebd8b04e082edc6a59ed1b703d8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Chart5
### Patch Diff Hash-SHA-256:

b1fec8840d5f2f42c794f7d2aaf076554efa2d3d555bf6da1ca4a45096e104f5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 10) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Chart5
### Patch Diff Hash-SHA-256:

b07a33f486c8abb86b9e79ad737d7960a15d5d17695ff4c71f6aa61512aa1c06

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.StackedBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Chart5
### Patch Diff Hash-SHA-256:

48fc4fa9431bc44d6baae4e1514824df2ade78544879fda5dd159252fd6d3084

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Chart5
### Patch Diff Hash-SHA-256:

e8674622e001d88c03638244890c83eacbe5ea48376adba64039c98cbe8b9697

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((allowDuplicateXValues) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Chart5
### Patch Diff Hash-SHA-256:

a12b49c7386387a15a35a45a6fc4132cf0c8364b40a0664884508b7bd2263386

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((x.doubleValue()) > (y.doubleValue())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Chart5
### Patch Diff Hash-SHA-256:

c8ed4d84dfa8f74f12979eecf326aa9e749c13d4d95164e08ef69622d17a503d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Chart5
### Patch Diff Hash-SHA-256:

4ebd61c7ca03fb4a2180ff90145f078cab0c422fe45dd77a75b3913641abd95f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (maximumItemCount)) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Chart5
### Patch Diff Hash-SHA-256:

e944bf2970a0d2d5a007083ab73efc3dfacff405ae517a0ea9bc896cfb564333

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (super.equals(data)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Chart5
### Patch Diff Hash-SHA-256:

bcb53b8f286878e98be41e615314891bab2d4c77e8183562bb3985d824e6c89e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((autoSort) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Chart5
### Patch Diff Hash-SHA-256:

fcaf0d7e2627ea1ed57d20511a687cad3736d8bd5ca29012fb38dec28de738ae

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.Vector) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Chart5
### Patch Diff Hash-SHA-256:

38d990cfa7958e09884dc9ce67eed31a008e9b3fb4a18d7ba4a43cf8aefd5da4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((super.equals(data)) && ((data) instanceof org.jfree.chart.needle.ShipNeedle)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Chart5
### Patch Diff Hash-SHA-256:

9217d46ebb1ff5d6fb7f59a8e3097e37407efe70f5fad0c96a72953f3a7729b4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Chart5
### Patch Diff Hash-SHA-256:

e08c5525ce7308dd5a688f8894f9de4c4fab215da671a2215966f9709de4d6c3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.SymbolicXYItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Chart5
### Patch Diff Hash-SHA-256:

9bac58fae55ab92e3ace51938bdd4ed5aeccd327977ec477e3a995d4d1f32a50

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Chart5
### Patch Diff Hash-SHA-256:

1c5bbf43807292c4ed64d18634ab081984248b594cbd5e37fe0aa8e24cc761d2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.FastScatterPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Chart5
### Patch Diff Hash-SHA-256:

78b7dd7d2611e9da9c594d48b185eeefd27c13075dc0a278b3dec4e53ca6d4d4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.BorderArrangement) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Chart5
### Patch Diff Hash-SHA-256:

1d79f11525adc6c10f76e6dea1f2697263ec70f2394fe619e6314b7c28497a9d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((super.equals(data)) && ((data) instanceof org.jfree.chart.needle.WindNeedle)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Chart5
### Patch Diff Hash-SHA-256:

4c9d65bbc82035f4a8008297556432bdec867ed5303606fd05296f8a90e1b530

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.StackedXYAreaRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Chart5
### Patch Diff Hash-SHA-256:

1bce995cd28e5abf330e56de15d4b28f3e8f677e2a9cd560cd351fc445f6b2d9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Chart5
### Patch Diff Hash-SHA-256:

f9ab76e592ca4e95a944e79e5a4812777ee1fb936e401b618b7993b85e69eb2f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.StandardDialScale) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Chart5
### Patch Diff Hash-SHA-256:

50bc63d9ab286c46d7c092cf924e8f996ed65e1e2ad1445be7318a8c25fcf76f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == 0) || ((maximumItemCount) == 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Chart5
### Patch Diff Hash-SHA-256:

25151ccd4dfd72b712e88cbc6dd38fb07b4797b84ab47ed0588d97cffada769c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 2) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Chart5
### Patch Diff Hash-SHA-256:

2109bb38c6277df12d58db10d837aa7745ea93f24edcaf2bb9384f4697d3b551

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data.size()) == 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Chart5
### Patch Diff Hash-SHA-256:

8c3782969de6cc8b75b6ae410f5f3248ba669d024ce5cefc04c59b35af7d2332

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.data.KeyedValues) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Chart5
### Patch Diff Hash-SHA-256:

dbf8a4e3a14d8020fb7fb387374ae47132e6dffdd83f854e13c2f8c825b9e536

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(autoSort)) && ((y.doubleValue()) < (x.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Chart5
### Patch Diff Hash-SHA-256:

b268d2018f590aa722259a323ba91817dbc4672c1f67fb74bf308b33a1401841

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == index) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Chart5
### Patch Diff Hash-SHA-256:

be8fb2c1b401a57510e9fa3ce4811913d692bbf2019e0f7aa8c459ba474e61f3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = false) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Chart5
### Patch Diff Hash-SHA-256:

2a486d7e7ddc56c71cd339236f4254746eff1d2eaef12e9d7607240cb0da8e42

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.DefaultOHLCDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Chart5
### Patch Diff Hash-SHA-256:

39330ce959c691d11ef40368aacc08c3e69137b923bf9c3a80dedb2543374044

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index >= 4) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Chart5
### Patch Diff Hash-SHA-256:

f297b34e43881f31adc687ca0cc33eddc830d346a4c87890b9ce816e3b3d7263

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.XYCoordinate) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Chart5
### Patch Diff Hash-SHA-256:

48f13227853339d3b7b385fc1bc896f6c97e6ce59b6b660d99c85007a75b07f9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Chart5
### Patch Diff Hash-SHA-256:

2c57b569aa661f55c12355b87b3284c1ef9cc5c64643a3fb1987b4291132bf33

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.XYPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Chart5
### Patch Diff Hash-SHA-256:

21ac761c1adbbbdd9877a39af65c5af2e430123d2d09c69bb2ce8f8b49434109

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) % 100) == 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Chart5
### Patch Diff Hash-SHA-256:

3f049777bccf65afc29de6d4330445d6d9870e8cd68fb97f54c76fa9ad95edee

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(autoSort)) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Chart5
### Patch Diff Hash-SHA-256:

03a80ac2f527be15b82f0f3b206f918698bacdf102144ffcb27878750a0f31c3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Chart5
### Patch Diff Hash-SHA-256:

957ff22315793066a277064311c5091736f5a57dcd6164204ab56742031253f6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index >= (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Chart5
### Patch Diff Hash-SHA-256:

0d5bbe60cddc05e3e8ea2dc041259a56358eb0ef0deebb1544e7b957fa65f996

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= (index - 2)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Chart5
### Patch Diff Hash-SHA-256:

2eb9fb13cbd461e9cf9da4e88537809f6fb4308f522c73c5b53cfaccb8018755

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (super.equals(x)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Chart5
### Patch Diff Hash-SHA-256:

7ff565d206a2ec2b1d143c03f3c2fca00c89ee6b8edb469b868872a837ac507f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.XYInterval) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Chart5
### Patch Diff Hash-SHA-256:

a64640977b5d5f9d773695ed6f253d6ed67fb6b195992150eaf06ab26e5e851d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (!(data.equals(data))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Chart5
### Patch Diff Hash-SHA-256:

d6ddf61e0d620ccfa8005ba1d1e3a15856d06c3fec87f4e9d0e3d82a0f13a22f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.data.xy.XYDataItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Chart5
### Patch Diff Hash-SHA-256:

d941df8872a3af8fb8466eaa07dba1005ff1fe67955ca526ce055f47edf7c87c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.AbstractXYAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Chart5
### Patch Diff Hash-SHA-256:

99af3a4fcd8c31885b6b19467c1f9c50532a1f54e956c086fea1539056b61943

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.SimpleHistogramBin) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Chart5
### Patch Diff Hash-SHA-256:

73070b7f4c9bbfe229c43abd4a493dfbc1bdc50d6312307c46da3a1b86882322

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.WindDataItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Chart5
### Patch Diff Hash-SHA-256:

da9faa867738f8663d5144737275135196cb984526b9b80ee9058646fa63fae8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (data.size())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Chart5
### Patch Diff Hash-SHA-256:

eed69dc096e1a3bba45f2a01c437bacd14535513bd205ce2b0ec4f4bee00ce74

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (data.contains(overwritten)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Chart5
### Patch Diff Hash-SHA-256:

b4888cd9d530589eae702e9fe30959e1a9a33b204381bd8832fa8b903bcbf7a8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index % 2) == 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Chart5
### Patch Diff Hash-SHA-256:

e996536cc9db0c662664ff13780b470b15a859a4d1fa8125f11fcbf30bcf344c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < 0) || (index > 3)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Chart5
### Patch Diff Hash-SHA-256:

2ff4c5ebc2efcd160e882846a339d1cd3ceaf84135cbd8b3bfdaa1d41c83dca7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((!(autoSort)) && (!(autoSort))) && (!(allowDuplicateXValues))) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Chart5
### Patch Diff Hash-SHA-256:

d414b7541a3bb6ac16fc9b9afa065e454cc7ffcc9e99079722a900b12a09a19d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.LevelRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Chart5
### Patch Diff Hash-SHA-256:

772b1b0d41699624a290925384193e0fb48346859e2abe7615c5b9a7f1d2b445

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x == null) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Chart5
### Patch Diff Hash-SHA-256:

b0e2bfade1aeb4c6a7bbec9a6c3fc421b963851095198993a761922d0a3ff98c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.ColumnArrangement) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Chart5
### Patch Diff Hash-SHA-256:

ab4526e15a49e2f583b5622b7690ed91c50159e1d8d85346c850464c08c23a7c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index >= 1900) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Chart5
### Patch Diff Hash-SHA-256:

21f460515b481d08c664ec5740d52749c046bf56fb0804c41b2f4b724000a456

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.AxisSpace) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Chart5
### Patch Diff Hash-SHA-256:

f32e6ddb8fd768c9e8e1eba2ab812819a97fd44ed69dbe0221b2efda15a110b9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < 0) || ((maximumItemCount) < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Chart5
### Patch Diff Hash-SHA-256:

6d489506e9d6977f8e4c0c330149d7c2c675b5668280e3b23fe024fbffa64aca

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.text.TextLine) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Chart5
### Patch Diff Hash-SHA-256:

adfbd4a0c3a36186912600923a00eabe9ba03d1ff573240864fa3183385ab549

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((data) instanceof org.jfree.chart.entity.XYItemEntity) && (super.equals(data))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Chart5
### Patch Diff Hash-SHA-256:

49e46ab997a4313bae4794c4989b4d77c43c97bac84b14f16097f962bdab6ca0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.CategoryTableXYDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Chart5
### Patch Diff Hash-SHA-256:

83862501b02d6b25b3b03b1f33ebc2ddc1bb05bf1e7d24afe3c23cc26b718924

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index < 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Chart5
### Patch Diff Hash-SHA-256:

d36d7004e635967932b1d3f95a68a16547ddcee3e1dbf215f6b6f46cb7952b86

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= 1900) && (index <= 9999)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Chart5
### Patch Diff Hash-SHA-256:

05a5a04282c625b730b35b36291e7befed4b066734bc3e4afc479d3b916d4555

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.CategoryTextAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Chart5
### Patch Diff Hash-SHA-256:

6d1297cfcf64cc0d5f545eba6e0df38c72c811fbe4faa30893087dc0237480c8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -207,7 +207,7 @@
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
-			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
+			if (autoSort = index == ((maximumItemCount) - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.remove(0);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Chart5
### Patch Diff Hash-SHA-256:

b34396f87daf5a0e28c2e324619f6f859dae0dc4b2b2d33fc0e33b340255cc36

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYDrawableAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Chart5
### Patch Diff Hash-SHA-256:

de03a20a6c1d3e20006e9137c4a782f775245962a94feeeac2f1a71bfeafbe12

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == (maximumItemCount)) && (index > 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Chart5
### Patch Diff Hash-SHA-256:

0d311a1e715ddd5a6fc20b8443d1db64ec175ee0f06a90d875c5e3cabe8a2d7a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index <= (index - 2)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Chart5
### Patch Diff Hash-SHA-256:

a449539f8f31f77f635e2d03a6a653b14a56614e67ef9fb0d3279f3b578f91bc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.chart.util.PublicCloneable) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Chart5
### Patch Diff Hash-SHA-256:

e8786cad3a3f9a358e2fad82fd19c8b4b0649fdf66db693f8355a2fbafcd0cd5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (!(x.equals(x))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Chart5
### Patch Diff Hash-SHA-256:

6a3d80e079d3655d5f32ae74814087921f9aa13d8c5e7d7796a95fc1401a1049

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.BoxAndWhiskerToolTipGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Chart5
### Patch Diff Hash-SHA-256:

ce86a79ec6da380165abfa37b55f83e460782071b61457b3b449b285a41671af

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.chart.block.EntityBlockParams) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Chart5
### Patch Diff Hash-SHA-256:

250b7c66d247bc3c8d0675283fa50bac4f41c4eb5326b2f3fbb10fcab0b23edb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYImageAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Chart5
### Patch Diff Hash-SHA-256:

c2d86457ea9b78320e47dc6a8dfc08f90c719acd62cf5a621a790c4663781434

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.DateTickUnit) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Chart5
### Patch Diff Hash-SHA-256:

2afc57f4c75d6f48dbdde9e913adf2820506ae660d442a52519f5400b57ef65e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Chart5
### Patch Diff Hash-SHA-256:

de8efce4db3e6cfcd882e74d4150f312c878c29e3e25ca13b52e43b00e7d0939

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.title.PaintScaleLegend) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Chart5
### Patch Diff Hash-SHA-256:

6e12258b2a93717bb1373837a7d5407ed2b24abc9efb615a7fe36dd3aa8f5505

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (java.lang.Double.isNaN(y.doubleValue())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Chart5
### Patch Diff Hash-SHA-256:

8664f833b936b19fd219e0527956143c938c5fc230e3ec3365a619a88a7a7282

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.SymbolAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Chart5
### Patch Diff Hash-SHA-256:

c032d767678835e2c14e7895b2a6de63f459ab254d99b8b686327047b1e6e8a9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.RegularTimePeriod) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Chart5
### Patch Diff Hash-SHA-256:

0e7b77c945c7b4c3c5775a8d9b510845e33bc9f253900e4895955cd6fd711453

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < 1) && (index < 5)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Chart5
### Patch Diff Hash-SHA-256:

5ef9190ba4444548a92535b71ade37cbabbdc793db1baeaaa066b216a82cd3cd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= 0) && ((maximumItemCount) < 4)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Chart5
### Patch Diff Hash-SHA-256:

caa6cd68c00ad29796bac8d86352ae0b0f299fdfcd2a19d19625860d3953644d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) > (maximumItemCount)) && ((maximumItemCount) <= (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Chart5
### Patch Diff Hash-SHA-256:

f698327f8cbf804f0ff5ff986a4329de7ebaa6f972a6ad262ded7a844ba8bb3d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == 5) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Chart5
### Patch Diff Hash-SHA-256:

951e98a3901c207309d3b4052093962cf27cf94d65d3266f494a638301b87d4c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < (data.size())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Chart5
### Patch Diff Hash-SHA-256:

34fefeabc73c0733d2c29f118a305fdbfec08533268c79691493db32e07c8bd7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < 1) && ((maximumItemCount) < 5)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Chart5
### Patch Diff Hash-SHA-256:

521e63893e9b35d3c62f2be605ebbf8bf2316cff1dea2323ad77948fcec04a98

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.TickUnit) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Chart5
### Patch Diff Hash-SHA-256:

7119fdcfed061617998658326af78e906196a46d9a04085fed9a3432e11ade7e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index | index) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Chart5
### Patch Diff Hash-SHA-256:

9aeaecbcd2b149c1d1bf287ce302d63deebd833990adf2b966c51d6fc99d0e98

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -188,7 +188,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(java.lang.Number x, java.lang.Number y) {
-		if (x == null) {
+		if (autoSort = false) {
 			throw new java.lang.IllegalArgumentException("Null 'x' argument.");
 		}
 		org.jfree.data.xy.XYDataItem overwritten = null;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Chart5
### Patch Diff Hash-SHA-256:

8e34f05f97736c4c3d21f6ac8d6e593152581b1a5b18b6cb0f7b45181159269f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= 0) && ((maximumItemCount) <= 23)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Chart5
### Patch Diff Hash-SHA-256:

7103748472da0b1f2a9630ebaf25cd0488a8edcc8f607b584d37dea314dbf4b2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYStepAreaRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Chart5
### Patch Diff Hash-SHA-256:

14bb55ca5f12ba57ef80db79714853fa24c0e3acb3f5c0ee5bdfb9881f61c70b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.category.CategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Chart5
### Patch Diff Hash-SHA-256:

e6cb984769c7db539d4fa2933ede7d1ce7900f653d94b5b3e8967b7775d27e3d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.ValueAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Chart5
### Patch Diff Hash-SHA-256:

89fd5737098638566440d7f05ce432b2f028b5e9cd092ff2f19f3cd9d591726c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Chart5
### Patch Diff Hash-SHA-256:

00100eaf8cca7c60e30daadeb46a434fe65eb0e8229880a023baa09a3b927210

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > 12) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Chart5
### Patch Diff Hash-SHA-256:

ee546355836abd830167d5c91ab26329a3a8928c421f32cfaae310688be914c7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(allowDuplicateXValues)) && (!(allowDuplicateXValues))) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Chart5
### Patch Diff Hash-SHA-256:

6b6ecfe360c482b9961c5949db747c8e0c57c5a763e23389b9913b690e41af2e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > index) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Chart5
### Patch Diff Hash-SHA-256:

41871c4776035e6a9db052c6a90e3750ac01fbd3b5f210b59db39e579a63f1f5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.data.time.SerialDate.isValidWeekdayCode(maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Chart5
### Patch Diff Hash-SHA-256:

269b2e8d2f0138b66a475b4620e36608872798f20d54563323edc9e9089e19bd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.StandardCategoryToolTipGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Chart5
### Patch Diff Hash-SHA-256:

045592f49c84a193ff1354592aebe199d3c00c8393ef21a2e5e63d74b477fa44

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(allowDuplicateXValues)) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Chart5
### Patch Diff Hash-SHA-256:

177b6e546c11262557555892b12ebfb9d808648528194a1296f587d9fc2b8cf7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == 5) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Chart5
### Patch Diff Hash-SHA-256:

91529ee972ab934d668a235fbfef6ae8a7ed1c060021b11171273e0e33bcd121

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.gantt.TaskSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Chart5
### Patch Diff Hash-SHA-256:

c0a5fb6720762439c5ccdf224d39c669a1325f952a57a89a301d255b91f469a2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.MeanAndStandardDeviation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Chart5
### Patch Diff Hash-SHA-256:

10b00d5572a2577a877481ea53ed88507359a8834e33a016e15c6126f2ab15cb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= 59) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Chart5
### Patch Diff Hash-SHA-256:

09a793a4d9a2cec3cb040989c287beae6cd665d89034f28143dfe1e181654bf5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index <= (-4)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Chart5
### Patch Diff Hash-SHA-256:

9df48958255fe8f0f142e7d868f249ad54e0909c84ae1b0b7ad8ba61913c68f6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.MultiplePiePlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Chart5
### Patch Diff Hash-SHA-256:

bca6889950d036dc031b629507e6c8ac1fd26056313487fd4d3d58b59c743f99

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.data.general.KeyedValueDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Chart5
### Patch Diff Hash-SHA-256:

6a4f3e49345a061f634222025b093f1affacad30491e16625749e022056c2bdd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.BoxAndWhiskerItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Chart5
### Patch Diff Hash-SHA-256:

b632b5f8ee275349f7225e7233f1b29de7c793c69de5c47ea4ad95595a96d218

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < ((maximumItemCount) - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Chart5
### Patch Diff Hash-SHA-256:

0f85033d4980c3cc44e2352f12e4e461c0b003a87d9cca0a316c22f8b0b5fd09

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.XIntervalSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Chart5
### Patch Diff Hash-SHA-256:

9dd88a31bc3f1da93225c9a88d0335787710dcb8ed052f7df21a1f8c5b583510

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((x.doubleValue()) < (x.doubleValue())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Chart5
### Patch Diff Hash-SHA-256:

d0f5cb5124a464f1386b248e7aa01fff583de89dce6f7ab8d0d0dd78416f5fdd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((data) != null) && (data.equals(y))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Chart5
### Patch Diff Hash-SHA-256:

da8059df1aa3fbb7bfe8017176ff3a4575cdee818cbe973a1d9b121e4fce9cf8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.data.time.SerialDate.isValidMonthCode(maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Chart5
### Patch Diff Hash-SHA-256:

82ceafabfd16fa951ac74e618875f7fc634acf671f92106b2263d4753ac58332

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > 360) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Chart5
### Patch Diff Hash-SHA-256:

1bc8c305ac87077c59e487839f6519f69cf35ddb774a403162539bc119e46cb7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index > index) && (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Chart5
### Patch Diff Hash-SHA-256:

e9630bcf67c50e697285edcdfc074b01b970b407ab1ff4a4136940ba8dc1f51b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.ohlc.OHLC) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Chart5
### Patch Diff Hash-SHA-256:

da282016fccf34e1ee86f039882fb1081425561f4e97c7eba0f426f4056b0878

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 6) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Chart5
### Patch Diff Hash-SHA-256:

cf4731098a38320af6da33aa778835a12c3ec88d35af288fcf8988fed6ca5332

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (java.lang.Double.isNaN(x.doubleValue())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Chart5
### Patch Diff Hash-SHA-256:

2b8f0432396bbcb26f90be8082c3971f335dc35331e0c2b9cbe9decd7f3ffade

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((x.doubleValue()) < 0.0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Chart5
### Patch Diff Hash-SHA-256:

7a7065ff9dda2d74f35fd03ddf7b1d21e0459d0e18c720f7085854fa304b9dbb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= ((maximumItemCount) - 2)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Chart5
### Patch Diff Hash-SHA-256:

1670d766c0ad90224cf9cd9e8a95485ec9987712d358182b9046e305751e6b13

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.StandardXYZToolTipGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Chart5
### Patch Diff Hash-SHA-256:

28b3377dde98aa6c54aefab602f6510e643332e365e415ef6183d7592062e57b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.IntervalBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Chart5
### Patch Diff Hash-SHA-256:

0403566d2a4f2e7d18a4172242894d3c47232d512c104d01a6bff2039980d906

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (data.size())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Chart5
### Patch Diff Hash-SHA-256:

cb85a4c540b5010254cd82b19ca72a191b1af268d93aadadee36fadfe0465d91

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (data.isEmpty()) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Chart5
### Patch Diff Hash-SHA-256:

8ce78afede1d39650dbd0bb9f2a8935b8315d41c24509bdb241f54e27ad8e691

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.YWithXInterval) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Chart5
### Patch Diff Hash-SHA-256:

9e23e28f0bfce8b6f3663acd53d9773da4b08978dee27fd2839e120fbe0302dc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.StandardXYItemRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Chart5
### Patch Diff Hash-SHA-256:

7f489fde684ef457a366d861cce275f82166a98fd33da241aa934adeebc98cd5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (-1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Chart5
### Patch Diff Hash-SHA-256:

690b4980966997c7b5387467dae450a4773de540b9e497aa953eb2efae672fd8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.StatisticalLineAndShapeRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Chart5
### Patch Diff Hash-SHA-256:

4d3c7e0988013e7f5e9aab431bcf546b4872c3fae60e7197e104d9e37fecb289

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.data.KeyedValues2D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Chart5
### Patch Diff Hash-SHA-256:

d28e68dfbe8bb02cf9dc6a572564566ee176794fccca1c34a7e83c267719e2c8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Second) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Chart5
### Patch Diff Hash-SHA-256:

0855897b8bac94f03991a258c4c93c36662378d07730c29e36aab92c59f15303

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.EntityBlockResult) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Chart5
### Patch Diff Hash-SHA-256:

170d37fe9f85f8b50127de44a98d989e6b5eecc9b3317d094c80bd9d26ebcf9a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index > (maximumItemCount)) && (index < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Chart5
### Patch Diff Hash-SHA-256:

01f5c79952aaa945cf96f327afa0952887af245e727da9d0acfa9d2723e54402

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.SimpleHistogramDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Chart5
### Patch Diff Hash-SHA-256:

836263910bdb512c8fb7561edeb42744d27b80572d3530d6f2a87c9a7ffb37a5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.Size2D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Chart5
### Patch Diff Hash-SHA-256:

0d1d278ba3c5ded339e1244a083b59e8f59b9a30c02d67c9fe3452cb06902184

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimePeriodValues) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Chart5
### Patch Diff Hash-SHA-256:

8a308424479bbdcd2901c59aa2d5282bbe3fd4f4474b88ad1c09fbdc08c28e76

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.StandardXYToolTipGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Chart5
### Patch Diff Hash-SHA-256:

3a97e10a551902a99f6f344f74192dbc6070a00a4ee47910ad27bf2d9b09c774

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimeTableXYDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Chart5
### Patch Diff Hash-SHA-256:

7945aa50afd1e13a10aac910f99c0ad40b881fbbad786fdac725400f05ffc648

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.YIntervalSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Chart5
### Patch Diff Hash-SHA-256:

ec17b733afba5debb7a9a875cd32acde1f810120ef1fc85f293577712bed2ca4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y.equals(x)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Chart5
### Patch Diff Hash-SHA-256:

bbe297339103bb8aa89b9ab38bc7498ca6d556ba46967187f8a9739168ce74cf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.Tick) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Chart5
### Patch Diff Hash-SHA-256:

7de0b04e555d758950d92fa73af333f5ba11491b72a462d0cf4a20d56d913777

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.chart.block.EntityBlockResult) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Chart5
### Patch Diff Hash-SHA-256:

634179a4ba346392a28be6cd9aed403b1defaa5be1a9f8b5d01c0bc4ce7f5b24

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((autoSort) && ((y.doubleValue()) > (y.doubleValue()))) || ((!(autoSort)) && ((y.doubleValue()) < (y.doubleValue())))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Chart5
### Patch Diff Hash-SHA-256:

dda4e540e694584a997ad956894ef8057264bea1025a0889b1b0196bd118e657

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.AbstractXYItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Chart5
### Patch Diff Hash-SHA-256:

5db5f6909567ffb105d609cf9a4eabce2359253b860976cf329e5417e7906b10

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((allowDuplicateXValues) && ((x.doubleValue()) > (x.doubleValue()))) || ((!(allowDuplicateXValues)) && ((x.doubleValue()) < (x.doubleValue())))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Chart5
### Patch Diff Hash-SHA-256:

616c5de5d9f59178194d91fc8b7e7487176a283632226f9ac2baa8ab5228a94e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((allowDuplicateXValues) && (!(allowDuplicateXValues))) || ((!(allowDuplicateXValues)) && (allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Chart5
### Patch Diff Hash-SHA-256:

0bbe723e8accbe6fdb46d881400cf9346efb5ffac2c6385bec369c63d167833f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.chart.util.PublicCloneable) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Chart5
### Patch Diff Hash-SHA-256:

58be04aec34139927ca8a256b7c81b7a3c5ac32946554901b2a2c93cfb9fdd76

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof java.lang.Number) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Chart5
### Patch Diff Hash-SHA-256:

4e27d29d807a9df4297a2d4d63f8805f50b00c6b87d3b4620f034ab625643051

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.SubCategoryAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Chart5
### Patch Diff Hash-SHA-256:

09e268849a841a2675d71f7e92cdc9e00f709db1c6b191463bc4a728aa753b46

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == 0) || ((maximumItemCount) == 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Chart5
### Patch Diff Hash-SHA-256:

cdaae8c91df0d186a8cd8f1ee610d0b814d1971c65cf65eb1785f22dc5f08359

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.LegendItemCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Chart5
### Patch Diff Hash-SHA-256:

4148ab39a5e2493c693c696bd40c00ad7f3f8352738fc71f9927d40f6988c351

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index >= (getItemCount())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Chart5
### Patch Diff Hash-SHA-256:

03f9be25a67921b6b495a0ce76942047fe7f7732eb11e11e9d3acc6acf19e605

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -207,7 +207,7 @@
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
-			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
+			if (autoSort = index == (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.remove(0);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Chart5
### Patch Diff Hash-SHA-256:

78ba6caa65730e52b698c6bd58b20b85b5a31af1792e03b3c8aeab4d98e14858

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((y.doubleValue()) < (y.doubleValue())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Chart5
### Patch Diff Hash-SHA-256:

4e87d0cfdcab1e370f9b4aa762e0eaa97e5d05f07f437fd3fd39935f8dd5231b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYPointerAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Chart5
### Patch Diff Hash-SHA-256:

00f1da3a4acc39cbe81a6048ac3dcf19d465f224b2c8b99aba390d376003bba5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.data.time.TimePeriod) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Chart5
### Patch Diff Hash-SHA-256:

5a306fcf4d8d68a21d89ade8695176cb6cc2c1c07a5a313e6179605a8a64e271

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.DefaultMultiValueCategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Chart5
### Patch Diff Hash-SHA-256:

9ed07384e436e9af2a6e5ddab3763dbdd7cd75132cc709a363c2e4d43746a5e7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.PeriodAxisLabelInfo) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Chart5
### Patch Diff Hash-SHA-256:

5b9a0483b91d499287ce5a37d8aa26183147794320f0109cb664057d6d0b5b13

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < 0) || (index > (getItemCount()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Chart5
### Patch Diff Hash-SHA-256:

3ec5b7aed0288cc0c50953a5521ac49c832ee8f4098321ee64a7d29d0d8265c9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.ComparableObjectItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Chart5
### Patch Diff Hash-SHA-256:

81de90dc1c0108ba21d0e53bcee0fcfb9879ab2f781929fab79b087b11884710

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Week) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Chart5
### Patch Diff Hash-SHA-256:

62b85671564e4f041cbd93abad0563cf0f5880213570c6d31a9d713bc016ab14

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.MeterNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Chart5
### Patch Diff Hash-SHA-256:

224dde9fb546dcda8a4307b914509ed4b35d2bbbd2ce725760167dd734a17d26

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.general.ValueDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Chart5
### Patch Diff Hash-SHA-256:

f9e7d80fbd11922f3d632f5da13066e9110b198e3166973cfc64cc3489fbaec7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((x.doubleValue()) > (x.doubleValue())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Chart5
### Patch Diff Hash-SHA-256:

fcc338bc175ed35274bf0ab002dbca60c57d6bd507b91f67ea4a5af7d72eae48

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x == (data)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Chart5
### Patch Diff Hash-SHA-256:

d16e5044170de3f75b6624e6e4d7ccd27556fd5aea618cefd8d5deaf224a0c15

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= index) && ((maximumItemCount) < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Chart5
### Patch Diff Hash-SHA-256:

d85691184c2e9b3ad7c98ff9d57ba22f3823f08fcedf9f343784c972379a08be

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.ScatterRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Chart5
### Patch Diff Hash-SHA-256:

5b5cbf9b95448ed20388a22bd2b4802f3413ac0b2368cd71db0b6d995d3b95b7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Quarter) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Chart5
### Patch Diff Hash-SHA-256:

dc5d8ce6fc8572930aca50991897e57f0b017bb6475a9293c1b80febad571069

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYAreaRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Chart5
### Patch Diff Hash-SHA-256:

cc8202c89d00a30ff6a1edc7409c7712ec14a06a8aff15197c4e305097e43beb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.title.Title) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Chart5
### Patch Diff Hash-SHA-256:

8dcc461f304536990340170ce120bc8892a162b184dfa2d994209e9e23d57d6a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.PieLabelRecord) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Chart5
### Patch Diff Hash-SHA-256:

fb05f5cb58b532a4c887482061ecf009e7f7981cac9dbf503c0f11bc02d4a3b9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Chart5
### Patch Diff Hash-SHA-256:

16acaf6e056e4473f99ecbcd7816fa0941b7c9588e5f92daeab9f51135287b3a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.urls.TimeSeriesURLGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Chart5
### Patch Diff Hash-SHA-256:

f33678089cabb4d80c8194c2ce8af50f7412fec76d978cd0f20d1f9db048fe36

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(allowDuplicateXValues)) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Chart5
### Patch Diff Hash-SHA-256:

940a1c865f3416ee381d5f927a6beada04660e7026e162e4f936ed0ca1298dd7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.gantt.TaskSeries) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Chart5
### Patch Diff Hash-SHA-256:

5c540092fcfc316613352cc9748161e434099de0d379a040ffe4d9875afc5c8e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (data.equals(x)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Chart5
### Patch Diff Hash-SHA-256:

7f3e5e6f369f87aaa1ff03fd30ab58c47c4335cae21afcb358776c212efad903

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.ClusteredXYBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Chart5
### Patch Diff Hash-SHA-256:

45bf6204e59f1e00b8845552256c9bf56e5fbddfba30ade2a3fdc87f0a0197b1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.data.category.CategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Chart5
### Patch Diff Hash-SHA-256:

304df967973d38491ec4cbc666fd44b0acf6c112d5c066450c661c715ae42687

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(autoSort)) && (!(autoSort))) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Chart5
### Patch Diff Hash-SHA-256:

650c9d590a869a0de0c6b2c3013e5fb1210d9c96d61e0cee831881dcde853baf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == 0) || (((maximumItemCount) > (-4)) && ((maximumItemCount) < 2))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Chart5
### Patch Diff Hash-SHA-256:

6752375e91eea68be8792c55dce35019e6aadd26ae14f9fde3532ba57834e7a0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialBackground) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Chart5
### Patch Diff Hash-SHA-256:

b0f0d1d5e234e8e1ea36c280252359bde10ada9f27e1a9f1d834bfc56bbdc4ea

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == (-1)) && (index < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Chart5
### Patch Diff Hash-SHA-256:

f8139412918c4ca7f3df4dcff10c07b8e0f7029edeb3437e962ab6433ca2c3c0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.KeyedObject) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Chart5
### Patch Diff Hash-SHA-256:

cb2b032da9d72ad79ec6087af8490f5e72083c06d357ff1e02c7fead9fcedfeb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.Outlier) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Chart5
### Patch Diff Hash-SHA-256:

653a943b4a0ccd6ca6af44685f9b44a2ed7ee0b315e0f72dc3e35ac3cf3b45e7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof java.io.Serializable) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Chart5
### Patch Diff Hash-SHA-256:

16f6ca506e3724ad0401023fda930ae196075b5dd02dffc3c822032557354297

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.CombinedDomainXYPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Chart5
### Patch Diff Hash-SHA-256:

689ebbf808164d823e41ee35e4ddd141da650a7bab0f5d2fe9e7a3273c9bcb00

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.CategoryPointerAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Chart5
### Patch Diff Hash-SHA-256:

07d80a3ce0d9a6c77b881367fad08c99c56095b01d0546fee327e0295a69a081

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.CombinedDomainCategoryPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Chart5
### Patch Diff Hash-SHA-256:

8859b428e9863abe7fe479a556aff762e969aad2f92b47143cd07cd59bf5bea6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.BarRenderer3D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Chart5
### Patch Diff Hash-SHA-256:

1860eb54df688c11da7b20d1f97e14d8eccd68c58e20d16ab33623e805e3c976

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialValueIndicator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Chart5
### Patch Diff Hash-SHA-256:

05b8467e3c736275557aae3aa6762c9be8694b45fc41b3fdcc6647ddf0934c9f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == ((maximumItemCount) - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Chart5
### Patch Diff Hash-SHA-256:

24293bc02bac2a1168fb27de8138c905f0eed1ee8f0981338204c56b0c5b6032

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.AbstractBlock) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Chart5
### Patch Diff Hash-SHA-256:

6ded27d07173535dfc9dd1cc9d59d0e1014e9f82dfba064adeffff21f8cc868e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.PinNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Chart5
### Patch Diff Hash-SHA-256:

ae3b22381a13fea6dafd7412c8b28c48ca0e2618cef17a32945424c74ebe3506

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.CombinedRangeXYPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Chart5
### Patch Diff Hash-SHA-256:

3b582c5419690e4a244829644dd3ee8d5db7d476ccefaa1aa037cb8613d67776

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Chart5
### Patch Diff Hash-SHA-256:

7b268af204027da691e63b3c1268281f86f20a67ac9faa0a4d666ddfe3afa40d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.JFreeChart) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Chart5
### Patch Diff Hash-SHA-256:

4c950317f1ea2d649af999966d5e0c2149d7532c59a7f797800b9dcf555a816f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 5) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Chart5
### Patch Diff Hash-SHA-256:

7fc3b4e89c34549909597382f84148f51c546ecf49429a47ede72f4213fa73f7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.RelativeDateFormat) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Chart5
### Patch Diff Hash-SHA-256:

1f88e3936884b3fca773b1245f1a4ff10b24b2538f3e01e7a47545f8a87bdd3b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.IntervalXYItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Chart5
### Patch Diff Hash-SHA-256:

eb15b4baa52d9b302b9ad97d41f699e0eb7faa7c2f442f505c2989bcda0288d1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.XYIntervalSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Chart5
### Patch Diff Hash-SHA-256:

e89d3153019d859884d7d775df02364748bf4b5554794d621f2efff090058867

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((data) instanceof org.jfree.chart.axis.PeriodAxis) && (super.equals(data))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Chart5
### Patch Diff Hash-SHA-256:

71e926b840f5d2a0af686db01a8feb74ce63ec3140b188097fc78523d190895a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYBoxAndWhiskerRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Chart5
### Patch Diff Hash-SHA-256:

e7c6007a13f3d8d325b28778ba26f4988307ab6c009ac63159ff9141bea7a1b0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.title.LegendGraphic) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Chart5
### Patch Diff Hash-SHA-256:

407b47395957fac0bdb9d4f5b3348f42148f5a17320a6a987c3fa0e2eaad4024

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == ((maximumItemCount) - 1)) && (index != 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Chart5
### Patch Diff Hash-SHA-256:

9d36c74875d8fb3ef7e53e25cc08831865a64d4ff090c2e360abc99ea355139a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= 1) && (index <= (org.jfree.data.time.SerialDate.lastDayOfMonth(maximumItemCount, index)))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Chart5
### Patch Diff Hash-SHA-256:

fad727e0823726b50f7b83dd0ea96eb4b799015dca8e9a1e13486ef3e34aa6b9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == 2) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Chart5
### Patch Diff Hash-SHA-256:

f827b760ac84a34beef9c241b10b418dca6004b6e445e6e6b0d0f66da3fef9e0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.DefaultKeyedValue) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Chart5
### Patch Diff Hash-SHA-256:

7fdd30667f326924e57f435a986283b0b3c37758471e357499dce365d8dd876d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.text.TextBox) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Chart5
### Patch Diff Hash-SHA-256:

8fa06bef0a7171ae5b7b65855c38ee5340821a13e207dcf9b7d1b296e09112fb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) > (-4)) && ((maximumItemCount) < 2)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Chart5
### Patch Diff Hash-SHA-256:

fc43dd5d69b99b4ea8ebc5475d8f39491ff14a72a6fcf2a3239d4b405c563d6e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(allowDuplicateXValues)) && ((y.doubleValue()) < (y.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Chart5
### Patch Diff Hash-SHA-256:

c6299d6c0ac5509b1e4d083a3571457df16e385afd6ad440f424aed309c6770e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.ItemLabelPosition) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Chart5
### Patch Diff Hash-SHA-256:

4745ae4d78288ddfda0d1f4b7dbe0a4a428d3a27706862518528a9bf3da25bab

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (0 < index) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Chart5
### Patch Diff Hash-SHA-256:

6ebce5fed8aab78f6531c88772e7d7ae24718e2a9b2ed156f4f1b59764758072

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((y.doubleValue()) < 0.0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Chart5
### Patch Diff Hash-SHA-256:

615a61375b1939242ff0a51fc287f2a13373f93e497e91ec4ed250847349610a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = (maximumItemCount) == (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Chart5
### Patch Diff Hash-SHA-256:

242c5c8d2d05184796842d8e4c55ce8cc35d674730b30a3bc456cd2ac7052079

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == index) && ((maximumItemCount) > 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Chart5
### Patch Diff Hash-SHA-256:

dfbef6af90774fb9d1ae6d50957a5eebb90ec76429ae35e0980093c24828caea

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= (maximumItemCount)) && (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Chart5
### Patch Diff Hash-SHA-256:

12337457dc7d2f6cda76fa5aec29bb316730233c02d72108c7fd340b864d38bf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.title.CompositeTitle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Chart5
### Patch Diff Hash-SHA-256:

8102f0556be57595e81b944fef3c44f3b84f1772542b035c4a8e8826754a57bd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.general.KeyedValueDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Chart5
### Patch Diff Hash-SHA-256:

458d0d2798bf0c53c81bd578163c6a3f16e8e35ebd515976c0be279bc4cc2c3a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.SpiderWebPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Chart5
### Patch Diff Hash-SHA-256:

5a12794a024d983b7fb07c861980c39f654e89b71407513e4e8cb198f6568c8b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYLineAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Chart5
### Patch Diff Hash-SHA-256:

2655edfc0b87243003f9a94738ba1244e38f43943d2cb97d2a6319587c9d1cb9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = index == ((maximumItemCount) - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Chart5
### Patch Diff Hash-SHA-256:

a64ebc9086dc8f003ce3d55cc2ab6af026d08065c44aa7a111de8212731c47c5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == index) && (index > 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Chart5
### Patch Diff Hash-SHA-256:

348a2b4f1d23d073b4f8899ac1542250f51434ea5b05a7286d3448bfa689dfaa

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(autoSort)) && (!(allowDuplicateXValues))) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Chart5
### Patch Diff Hash-SHA-256:

6d0a5d084e1f1b015025de5e1b37d298edadca17464418a08010fa73bb87f9e8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.data.time.SerialDate.isValidWeekdayCode(index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Chart5
### Patch Diff Hash-SHA-256:

92b73330da2d9e5957fa0c869149682aa94267086e7d0d39b98b34f56a8781c5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= 9999) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Chart5
### Patch Diff Hash-SHA-256:

377b019cf22e52a1d772fb77bf37c1a5b539141f72286fc0628df36a91e404dd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.PiePlot3D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Chart5
### Patch Diff Hash-SHA-256:

3de6308cbfa28c9645eeefe90dc4b1866e6dfc8a5afe9dff238fe4ccbcfa28a0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.PlotRenderingInfo) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Chart5
### Patch Diff Hash-SHA-256:

8c09caf9b0040d95f6a801ec578c77ead86319fe38e102020aaa54dbd41929cf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index - (maximumItemCount)) >= 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Chart5
### Patch Diff Hash-SHA-256:

69098e955a37c7e95783de67b1a9f386bf347b1fdeef3c663d7130731b6eb559

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.BoxAndWhiskerRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Chart5
### Patch Diff Hash-SHA-256:

53aebd67721d49d5c81019d35cb852d69f6f05758381bce8872254c85faf9cda

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((data) instanceof org.jfree.chart.axis.SubCategoryAxis) && (super.equals(data))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Chart5
### Patch Diff Hash-SHA-256:

04b2f4b1a9246dfb82ac84462bbecaf055689edc19e346c970306a95d8bc1734

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.CompassPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Chart5
### Patch Diff Hash-SHA-256:

53e67cf4a553b0568acb78b5278953ee35956833dfa8572725a44df364ead151

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Chart5
### Patch Diff Hash-SHA-256:

9a9cc400d388d49f1e71818dcc2903dfeaf26208987a040ab919d9fe3901e88f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((overwritten != null) && (overwritten.equals(overwritten))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Chart5
### Patch Diff Hash-SHA-256:

fe41e4f3a9c8e89592e334f2afa9a36eeb08831bf58bea702bc937034e1e9811

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.text.TextBlock) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Chart5
### Patch Diff Hash-SHA-256:

331f2b1c246643f61d155163d2a28f7214d43d84c92c1df90706064853bdf00a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index < (4 - (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Chart5
### Patch Diff Hash-SHA-256:

ebb186c5226c8b15d214a5a9dae23ada9ec9f8239e30a0b5f9da437d5db98978

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.ComparableObjectSeries) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Chart5
### Patch Diff Hash-SHA-256:

cdc09fff19df6202055787e005cb4f9748475d4d9bfb770aba9a1588f3d87dc2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.chart.util.PublicCloneable) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Chart5
### Patch Diff Hash-SHA-256:

4ea1dde78fee901b87b0396f9fdc30f22649189b3c45ec89c5e31c56c5759acc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= (index - (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Chart5
### Patch Diff Hash-SHA-256:

5fd226ef2e30fcc45772e869c9c60f5ecd14882f017097c0093f5fbe85aa58e7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((x != null) && (x.equals(overwritten))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Chart5
### Patch Diff Hash-SHA-256:

bde47aba9137243c6b25b2f7d1ebbceb785b22f30115ba8dd7d38255162b708e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) > (maximumItemCount)) && ((maximumItemCount) < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Chart5
### Patch Diff Hash-SHA-256:

1d8a5a50af5bf1c84de874a4a7937e543178959280b02bd64b3653800eb03372

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (0 == (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Chart5
### Patch Diff Hash-SHA-256:

9f6440234927f9c8d22284f361e4f604e9e36952e8edc28999af4f8a40a545af

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.general.Series) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Chart5
### Patch Diff Hash-SHA-256:

a91af5ef5983d86cc3d3234c80cc574e2e8c3e70f5b122d109201a409417b2fe

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.LogFormat) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Chart5
### Patch Diff Hash-SHA-256:

0de3c79ce34c79ef7d4432ae6da07b51003513ecd093e88389d62aa2aa395dc2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.data.general.KeyedValueDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Chart5
### Patch Diff Hash-SHA-256:

39a8799d853f892235b7aa3c2b8a45202380c675e9d5d576c70203b5a0c4003e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index - index) > 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Chart5
### Patch Diff Hash-SHA-256:

2dbf4d8faf3e3d1e74a30b1f54d50eb8e8ceb600444d9d74343a633fde3f95c1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.StatisticalBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Chart5
### Patch Diff Hash-SHA-256:

6ad2c5ac165fde1429037ae15e2a8b2a154ca1c43569552ef0f3f88020319eb0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.StackedXYAreaRenderer2) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Chart5
### Patch Diff Hash-SHA-256:

44849c1f9e4fe66cb11c317357baee55820958210b0c0e1219fd68b28412b526

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.urls.CustomCategoryURLGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Chart5
### Patch Diff Hash-SHA-256:

dd6e870571e3ecf37f2613a8012e3435c74ee54df82c1da69e6122ee10cb151c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.YIntervalRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Chart5
### Patch Diff Hash-SHA-256:

745c17e30e1621c16bb504863dcf6dc4d4f6a5f135b988dc1aec420a3fd784d8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.CombinedRangeCategoryPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Chart5
### Patch Diff Hash-SHA-256:

9449249474f091fa3aac784dff95e2d064a4961544d8da2e352385fdd2ebe74e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.AbstractObjectList) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Chart5
### Patch Diff Hash-SHA-256:

33909042e52c8d1d9a6a2aacc26306654bc6674ec07ea2d7fd96a80572004476

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.DefaultTableXYDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Chart5
### Patch Diff Hash-SHA-256:

2a759f0250bd29e063abe1173af5e955b17ed4b286bbeaafab5a0788b09283c2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.DefaultWindDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Chart5
### Patch Diff Hash-SHA-256:

d8c1371c9816cbf562b875d79c43ccd8635329c73842c2087e7902b548529f7a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.CategoryMarker) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Chart5
### Patch Diff Hash-SHA-256:

63bdd5be7c2cc2ac0de5554ab47a3f2be61a0b84a7fe87a06c9bfd9bf9f0ed6d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.StandardGradientPaintTransformer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Chart5
### Patch Diff Hash-SHA-256:

25b9947e38281bfea852109ad5c263f3d7963162e2d5fecc9ca7378ba74e9f61

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(autoSort)) && (!(autoSort))) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Chart5
### Patch Diff Hash-SHA-256:

31fb5a7200e2203cdd5a657fd2c46409bc6ca3959dd5a83688ea052ab6bd8ebd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.entity.CategoryItemEntity) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Chart5
### Patch Diff Hash-SHA-256:

d2665c644a45e428f6b725da1e385d35efcf2c4fccb69c8dd4d41728bd313ae7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((--index) >= 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Chart5
### Patch Diff Hash-SHA-256:

9d5bb74b86ca2c165f049c341a205ccc9d5e59d587f0eaf5da389220ea383402

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialTextAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Chart5
### Patch Diff Hash-SHA-256:

12848d4c96339b8575033fdfd4341f0f6f08e21a0bb20020a2572e27cc644a1c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.StandardDialFrame) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Chart5
### Patch Diff Hash-SHA-256:

aaed894c63fddba69a30f70825434f165eb4d17c041ea336811c65143a16d2e2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -188,7 +188,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(java.lang.Number x, java.lang.Number y) {
-		if (x == null) {
+		if (autoSort = (maximumItemCount) == ((maximumItemCount) - 1)) {
 			throw new java.lang.IllegalArgumentException("Null 'x' argument.");
 		}
 		org.jfree.data.xy.XYDataItem overwritten = null;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Chart5
### Patch Diff Hash-SHA-256:

8862d0432864bee2913da1746397bfc8b62bd23f251c66e3cdb5e92a0d61f074

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.FixedMillisecond) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Chart5
### Patch Diff Hash-SHA-256:

5c2560db841dab87a5d81e277fc5b366604355e9327c581747a6f28d7f0ed1b5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index > index) && (index < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Chart5
### Patch Diff Hash-SHA-256:

5710ff28f9bb26e267e5ca3bb78f9630b8f9b5b273fb5b085fd52bc7f9169a02

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.XYSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Chart5
### Patch Diff Hash-SHA-256:

c1e26f51265b521278e7f9177bc529810fdd11c41bbbba0509862d47a956c03c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimePeriodValuesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Chart5
### Patch Diff Hash-SHA-256:

5b5937a34f93ac711331145e7d477c814eea0e997b4efe0546329ed08bc5d49f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Minute) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Chart5
### Patch Diff Hash-SHA-256:

68098b0df88c9f5860264df69e9fb617a380379967dec6bee9edb8e12c8efbd6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= ((maximumItemCount) - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Chart5
### Patch Diff Hash-SHA-256:

35c9a41fba57242bbb11d373e63ad5d536ed17ac97b07778ac15723c28fa7c3a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & index) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Chart5
### Patch Diff Hash-SHA-256:

653164891cf61e7b19ddea0f211b9c23de8612a35cdca3c87ce604a3eb60984d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.RingPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Chart5
### Patch Diff Hash-SHA-256:

38606a1b0f51b8dd394cc6bafc4406574622315a7c26edaac62db86bfb5556bd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) - (maximumItemCount)) > 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Chart5
### Patch Diff Hash-SHA-256:

d7ea88dda6805a01b32dfc79a20725395761245efa2886910a7d7a5bdff9a33b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == (-1)) && (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Chart5
### Patch Diff Hash-SHA-256:

a28dbc82836dbc858440e9c05942b6d2edc4655714d093aa076f3ded7389ce37

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.AreaRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Chart5
### Patch Diff Hash-SHA-256:

ede2b50e3b8614c2633ce588170622191970d33e8730144538f6f8339146c594

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYPolygonAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Chart5
### Patch Diff Hash-SHA-256:

3c2cf30c8b5851e0dc8ca380c824c85b19e6ca8451e280a15fcb2744a821d79f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.XYDataItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Chart5
### Patch Diff Hash-SHA-256:

df23d9bfb1fa881086e8811cca10134ba8f0fd5ad2f0878c21466dab7915a77c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.entity.CategoryLabelEntity) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Chart5
### Patch Diff Hash-SHA-256:

799b2e080aa5998cf9ad431703420491c175511896ef3261db23c2dd5ade01d9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.LineBorder) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Chart5
### Patch Diff Hash-SHA-256:

174ed69bd0184c5337b246d34c531ababdfafdb0f148d41baff245d6f0886798

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x.equals(overwritten)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Chart5
### Patch Diff Hash-SHA-256:

63ef1d752ee00826b403d42075c87cc876b3c81c59c7b0e74fcf447033205b6e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Hour) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Chart5
### Patch Diff Hash-SHA-256:

c1dca042d2dfe288c41064f603d21992f4bcafca5a7dffe75850cf1845168a3a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.data.general.KeyedValueDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Chart5
### Patch Diff Hash-SHA-256:

8eb9a896862625c4cc68b362072cd7f1842d14c79c98d6f85991d3361b3865f8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.DefaultPolarItemRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Chart5
### Patch Diff Hash-SHA-256:

b8f3bfe2ae16bb8d4d2cbfa9175816e06dd0731173de5322e0994fc5251c4d0b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.DeviationRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Chart5
### Patch Diff Hash-SHA-256:

514812a27aecaa70bbd39fdc5cb0606831fd0afa012438e8a54e5fe1839bedf1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(allowDuplicateXValues)) && (!(autoSort))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Chart5
### Patch Diff Hash-SHA-256:

e6ea4cac3657818a985bef8feae25822ae47959da2cdd1ef2e1a1a1a9f520ad3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.StandardXYBarPainter) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Chart5
### Patch Diff Hash-SHA-256:

c8197315771c53544885be0fe38f7f129bccf02fb585605027fafe3933e438f0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.CandlestickRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Chart5
### Patch Diff Hash-SHA-256:

ae15bff4a4dd8d39265c3bbfc13113e463c357ebb187f37438b7641117326532

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.LineAndShapeRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Chart5
### Patch Diff Hash-SHA-256:

f892ce0c4e229ef39c2dc12b83512612e452210d480b2c92679a5b50727a6427

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimePeriodValue) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Chart5
### Patch Diff Hash-SHA-256:

7db1420bd88ab18cacacf5bb39668e12c082727030d46516531836d66798af27

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.DefaultBoxAndWhiskerXYDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Chart5
### Patch Diff Hash-SHA-256:

ed0a07cf6768d396eac84cca019ff9965a1b85a9917ae98f8ca0a32972cc1aad

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.PeriodAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Chart5
### Patch Diff Hash-SHA-256:

6c4b44e25eb99e8c8c1f184bf50493c62db95ee506e73c13eada55d4b5ab4ce2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.VectorRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Chart5
### Patch Diff Hash-SHA-256:

e35b650ea614f018c65c1c2f6fc3258c8af88bba377f348449cac834fd3ea40f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.HistogramType) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Chart5
### Patch Diff Hash-SHA-256:

22aeaeffe1be021836337e8d8be7646f06a8a997b67ea08a5a448f1129397270

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y.equals(overwritten)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Chart5
### Patch Diff Hash-SHA-256:

6eefaaeb6ebaca29139f0f91640f042f64489b17048d7e168c7d1f70715965d5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < 1) || (((maximumItemCount) < 1) && ((maximumItemCount) < 5))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Chart5
### Patch Diff Hash-SHA-256:

342114baa688ee632a33a2f0c9de23c17cc5315f83ccb278e3e007ca75afc738

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.CategoryStepRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Chart5
### Patch Diff Hash-SHA-256:

d54a67cc5a826eb11c06f0f63bed6def63cb5b44acae8ded95000f0e548de8bc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.StandardDialRange) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Chart5
### Patch Diff Hash-SHA-256:

f06a7b3de63c3a3c11c3e6abf2a2932c37f15bd6685e1ccff6fcf6e55b427733

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.AbstractXYItemRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Chart5
### Patch Diff Hash-SHA-256:

a30a6ce1e962ec36c419934ef1b4a88e0a9e15dbd069c1c955c8ca33651b1f09

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.StrokeList) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Chart5
### Patch Diff Hash-SHA-256:

bb2594d749e6a585a9750587daeb3f50f28013de56bbed4676bb4cc744fe75b7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < 1) || ((index < 1) && ((maximumItemCount) < 5))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Chart5
### Patch Diff Hash-SHA-256:

784b59ee32f4a88c29644e8be687d8871a3e4106766ba756834c195d12c3fcbc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((allowDuplicateXValues) && ((x.doubleValue()) > (y.doubleValue()))) || ((!(allowDuplicateXValues)) && ((x.doubleValue()) < (y.doubleValue())))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Chart5
### Patch Diff Hash-SHA-256:

1ce1ab94d9a92728e95119993e4ce9f44ea47e5d3e0dc1245d4a4ccf65fc1fe4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.title.TextTitle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Chart5
### Patch Diff Hash-SHA-256:

b8a83f05f5d0f99cb99ed8d2de7a394de9058a6e37aa6b9745b9983a80bdab3f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index > (-4)) && ((maximumItemCount) < 2)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Chart5
### Patch Diff Hash-SHA-256:

a4a710f5f962f6c2e7be9ca56c25460f302a66446bfebdb76a15b40eaf1f95ee

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) % 400) == 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Chart5
### Patch Diff Hash-SHA-256:

7f8c24f407215373e6ffe340fdbafbf3f9decb453b580c1b0534c4527655f3eb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYShapeRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Chart5
### Patch Diff Hash-SHA-256:

8d0682dfc9de7af0b3dcc41a7793837d5a3574ee0e4dbc3e3a7733ba87d5355e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.chart.block.EntityBlockResult) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Chart5
### Patch Diff Hash-SHA-256:

209bfe950871f4200fb397202d7544a840d39b5e898680bfe021eadecbf8841b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < 1) && ((maximumItemCount) < 5)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Chart5
### Patch Diff Hash-SHA-256:

055058b38a05f5cae4ca8401f1205f2565dc8602d68d0c2292bc51249d6529e1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.LegendItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Chart5
### Patch Diff Hash-SHA-256:

82308889c2d68a38583392d5f7211901437bf53508493db7914a6ce543d786d5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYBubbleRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Chart5
### Patch Diff Hash-SHA-256:

e5c9b896b2cde00f3da8c084d01cb323f65927f45fe0c96d342e3da77c8b96b8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.BlockBorder) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Chart5
### Patch Diff Hash-SHA-256:

a2a6b3bad826a5647b7d3bf65bea3dafab7b52731ef32608d46d3d461bc3a52d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < (maximumItemCount)) && ((maximumItemCount) < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Chart5
### Patch Diff Hash-SHA-256:

68ec9b8863de82e78792f4795ae8b5bd71e0e293544b7cea47add521c07f1cb4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= 23) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Chart5
### Patch Diff Hash-SHA-256:

fb223731609a3d487e90e7cbd701aaf1d25522892a5a9379403bdff4cc6a50e7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Year) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Chart5
### Patch Diff Hash-SHA-256:

a698be6f95516c26f5b0cd3e3d8ad9f2fa9adf6e823ac7838bbfbd2acaa43d0e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYErrorRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Chart5
### Patch Diff Hash-SHA-256:

478a7e3691abe4ae6be8c13d8c5547c398d3afaeea76db78472dc8b511071e96

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= (maximumItemCount)) && ((maximumItemCount) < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Chart5
### Patch Diff Hash-SHA-256:

2f3d3a4a6374dad8d4eb4f72d0b7484f71f6fcbc187628236f52cc704cffe7fc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.data.general.PieDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Chart5
### Patch Diff Hash-SHA-256:

fd8a575a251b863759580d383ebaa39fe4290e2b9001f076689cc5dc4295acd6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(allowDuplicateXValues)) && (!(autoSort))) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Chart5
### Patch Diff Hash-SHA-256:

fff560e35b68ef5ad4abcc43a26bd77e85d5799b74617dd3e591d4d15d164b64

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index != 0) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Chart5
### Patch Diff Hash-SHA-256:

0c272703c246f05a17686559f79c83e56b5125a48684ebb20082cb52816c993f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= (maximumItemCount)) && (index <= index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Chart5
### Patch Diff Hash-SHA-256:

b157b7f4640abaeb25cd4248e4d9fff474375b0dbbdd7c421129bf7b120958ce

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) == x) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Chart5
### Patch Diff Hash-SHA-256:

1d4638cb2e7ee3ab63769145f27ab52a71d6b94da14913cd6233f6260ef06655

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < (4 - index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Chart5
### Patch Diff Hash-SHA-256:

2ed82bdfebd2b90aa8e23b4710e7bb90bdce9648c8720ab5a10ca226c2262a85

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialPointer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Chart5
### Patch Diff Hash-SHA-256:

92d550dec03e4fe0284b00654530b4a073ac96dc6ec12014f91a7b9e0c5c8bd0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) == y) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Chart5
### Patch Diff Hash-SHA-256:

c4541ebc17509f499cbee120ace19f6fef19f77879df5e3e11e9498326d988d4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.StackedXYBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Chart5
### Patch Diff Hash-SHA-256:

dca8e7dbb5e7d0858e313e0d953e7228bda15414812e995c8a966b148df21242

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.CategoryLabelPositions) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Chart5
### Patch Diff Hash-SHA-256:

9d2268d57b9291b0076512c2b2c66c65a3b7235e99ea56ccd38ed88b30526045

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.data.general.ValueDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Chart5
### Patch Diff Hash-SHA-256:

473804acc883559d558a7521dd2470607eadc9c46a8fda5e9ee6aca66067bfac

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < index) && (!(autoSort))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Chart5
### Patch Diff Hash-SHA-256:

405bc8b3989784ed59d76af55be4271132c0d82be24f02b368125cf52e92641e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.NumberTickUnit) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Chart5
### Patch Diff Hash-SHA-256:

d560e496ef677f0c789623686f0b034690c75fe33e27996c1f3bf5db75752972

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.KeyedValues) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Chart5
### Patch Diff Hash-SHA-256:

204c493e19fb8476ee0699fe990a120a803b5a3b5da5ff20d2e7d24480557549

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((0 == (maximumItemCount)) && (0 == index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Chart5
### Patch Diff Hash-SHA-256:

6f549ab69195d7372941090a63e6bd281159d4bdd9666ab3f4ee60ac519d67ee

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y.equals(data)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Chart5
### Patch Diff Hash-SHA-256:

54ec6127dd50b8633d6c003f3f00be594711dea6cd0050e6f2a12d533e74ae10

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.Marker) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Chart5
### Patch Diff Hash-SHA-256:

f1f02806002ec8eeb6fd268893aa222b346db46e07bceaa033ea41e4de77e284

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -216,7 +216,7 @@
 	}
 
 	public int indexOf(java.lang.Number x) {
-		if (org.jfree.data.xy.XYSeries.this.autoSort) {
+		if (autoSort = (maximumItemCount) == ((maximumItemCount) - 1)) {
 			return java.util.Collections.binarySearch(org.jfree.data.xy.XYSeries.this.data, new org.jfree.data.xy.XYDataItem(x, null));
 		}else {
 			for (int i = 0; i < (org.jfree.data.xy.XYSeries.this.data.size()); i++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Chart5
### Patch Diff Hash-SHA-256:

b2f13bf4e4241071cdef2ddb5cbfa1b36b5645ec09e4eda9f30cbf8a59f8b72c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.ChartRenderingInfo) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Chart5
### Patch Diff Hash-SHA-256:

b451c08d6f2b1fb23f8c885a0037f899fb4a1f6be7106f1c723da9e8975d2502

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.NumberAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Chart5
### Patch Diff Hash-SHA-256:

280069b463078c19e6904198f470763d0330a5d5cd4de9dc91467ef80a555199

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < 0) || (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Chart5
### Patch Diff Hash-SHA-256:

b8445a701311f371883c7bfeb042083cb5ed1a0173ee1694bb7d42c6049283db

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.ShapeList) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Chart5
### Patch Diff Hash-SHA-256:

34dc7e713edf6f9f5ebaa40d1aa4a54a74030c04e36bdb6f99bb1771c0c4482e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((overwritten != null) && (overwritten instanceof java.io.Serializable)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Chart5
### Patch Diff Hash-SHA-256:

2e72cfdf34042bd2da5e853705a7b19b3d768ede3dd8e7fc4ef5ea8928f41a68

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.StackedAreaRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Chart5
### Patch Diff Hash-SHA-256:

b314c0e6fdc17591ec3c0ed59448e8ea720110a64472ebb82eeec7f5e17ba3ca

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((getItemCount()) > (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Chart5
### Patch Diff Hash-SHA-256:

7ee899b88befbfae5e6818f3b3d7229befc18ecf566f7bd540e774a4fcc1dc0a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((data) instanceof org.jfree.chart.axis.CategoryTick) && (super.equals(data))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Chart5
### Patch Diff Hash-SHA-256:

c526acbb8122a42deca73046891645b97bcfa320c8c7d481408c187139129bfd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == 0) && ((maximumItemCount) > 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Chart5
### Patch Diff Hash-SHA-256:

4cb81c581778effc7277662e962b2e1eb735ca069c8f3cc8110c3a2720088257

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.AbstractPieItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Chart5
### Patch Diff Hash-SHA-256:

47ca5328d0eeab24efd6bfb9912f90ee3b7689332b8b80cba4ba7dcb243d6cda

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.chart.block.EntityBlockResult) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Chart5
### Patch Diff Hash-SHA-256:

fa5bf63605f1e6149a5df9ffbef183d23377d5069121b1c05a6a9e6e24a6a8d4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.DefaultDrawingSupplier) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Chart5
### Patch Diff Hash-SHA-256:

321a01cdf262ea04c2fe4e414dcb561afa7852c2f98fa94a9c021bef59a7a157

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.ValueTick) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Chart5
### Patch Diff Hash-SHA-256:

00f49f1749db3891ee6aa9e7db7c728d62883a484779c4822b155f7362b14ed7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.SerialDate) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Chart5
### Patch Diff Hash-SHA-256:

62799aaef6e838a219478414fed52501732605ffeb69b665bcedae1b0b71260f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.DefaultXYZDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Chart5
### Patch Diff Hash-SHA-256:

c0555fef7d7aff8215327c1fdb201f85ac7630c09212323a1a9bbdc10bac991e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -207,7 +207,7 @@
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
-			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
+			if (autoSort = (maximumItemCount) == (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.remove(0);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Chart5
### Patch Diff Hash-SHA-256:

294c042c141133eb729f209e0a1fd3dcfece4a81925457808a7c48fdbae40c91

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == (index - 1)) && ((maximumItemCount) != 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Chart5
### Patch Diff Hash-SHA-256:

75ea8f5c1f0519b66570f17b43a2db3149c46a314e9e6b8442bee1163091f7ac

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < index) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Chart5
### Patch Diff Hash-SHA-256:

2787818f3e30a1c7a266249f9b38d93ad5bb2f0aa4b446827e123e14e7703c62

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.KeyToGroupMap) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Chart5
### Patch Diff Hash-SHA-256:

a7446fb2d4ecf0b25c1416b1735a50a6c4009a49330c9cbf1f850f3419bea991

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.data.KeyedValues) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Chart5
### Patch Diff Hash-SHA-256:

b1572222bb1f51ff357f3597d9a629a464852acbd3458b38de8385b7f0bc8ed9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.ModuloAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Chart5
### Patch Diff Hash-SHA-256:

0253e7fbc717746b1c516777e80a27f304704ef99fb87079e04b4221476eb068

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.PaintMap) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Chart5
### Patch Diff Hash-SHA-256:

d393d5823cf1868c1731d410e5d3bbab83f443b67f35926cb4a70964b3e9b916

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) > (maximumItemCount)) && ((maximumItemCount) < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Chart5
### Patch Diff Hash-SHA-256:

4717b9e39bc028975955a9b40c7633f95976433c751d7c38b87f4ecaca0d3b68

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.SegmentedTimeline.Segment) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Chart5
### Patch Diff Hash-SHA-256:

0cbb89f901400ac0b336bb6a41ee2d1a21983d9b7c6ff1713c726624776e31ab

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.StandardBarPainter) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Chart5
### Patch Diff Hash-SHA-256:

607590e2da2d9993beeeed382eacee447db8ac8fb5a39a6c6a630666e82e7b72

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.entity.XYItemEntity) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Chart5
### Patch Diff Hash-SHA-256:

a7126f755e76a81472fb6d1ffe955f17adecd14c63c981a53b6fb626e8bc76a6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYBlockRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Chart5
### Patch Diff Hash-SHA-256:

48574273bcd43b2e2143c30afa46433d926e536dec2ec433593223d4a24ef5e6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(allowDuplicateXValues)) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Chart5
### Patch Diff Hash-SHA-256:

8824ff26588e3818e79ca95b6a489f56ead0c7054c1d223e40e80945b7a226dd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < index) && ((maximumItemCount) < (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Chart5
### Patch Diff Hash-SHA-256:

a27a3c7c6d21c90c8b15325d005df6bd408cd25281e1f71aa8d847e8cd532f51

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= (maximumItemCount)) && (index <= (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Chart5
### Patch Diff Hash-SHA-256:

4511bc8fec2340d1c0ef33fda0a6ba5e5c1a11224a142762ec3771ea71e84082

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.urls.CustomXYURLGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Chart5
### Patch Diff Hash-SHA-256:

8bf1760f6e92f45bac470f19cb88db7b6ed42d6a2407cd34ee16c89497a980ac

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.StandardChartTheme) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Chart5
### Patch Diff Hash-SHA-256:

47693f891501675b35cd25b8dd1270ffa5551f4b59cf16d097492807a4c3758f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.StackedBarRenderer3D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Chart5
### Patch Diff Hash-SHA-256:

f02457c8bd06ba083680d128aa603b2ceb7dd62219faca03219b8d4edee7d34d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.VectorSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Chart5
### Patch Diff Hash-SHA-256:

b1ec5dc1d03c18cdb621263f1a8ab018e1480dd10b203d0d992a77fcac6f59f7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < 0) || (index >= (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Chart5
### Patch Diff Hash-SHA-256:

60b5b60972eef2f69c6c9ca65024b97e6e87ac490b3432522ae1121851aaa046

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.MatrixSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Chart5
### Patch Diff Hash-SHA-256:

3f14b4bf167680413ad2ddba6e25712bdd8f6fddf692ce89841187ee3894946c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.MiddlePinNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Chart5
### Patch Diff Hash-SHA-256:

b4a17f994e76771bd3784c4d16d1f300f56b47cfb27e7fd7765978502ddb1764

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index * (maximumItemCount)) > 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Chart5
### Patch Diff Hash-SHA-256:

947ebd095610970274d97500fd14cf84287709bc2e1286d8c099439ffa0049e8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < (4 - (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Chart5
### Patch Diff Hash-SHA-256:

3d2b2510e59456900ed8709500047155abfb3756a8a2c329b84f1356a78d4cf4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimeSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Chart5
### Patch Diff Hash-SHA-256:

dbb02f3556a3aa67aab5176f5e05168044708621b04f46a5ffe89913245cabfc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((allowDuplicateXValues) && ((y.doubleValue()) > (y.doubleValue()))) || ((!(allowDuplicateXValues)) && ((y.doubleValue()) < (y.doubleValue())))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Chart5
### Patch Diff Hash-SHA-256:

ce18106ad7dd874f894e3b1a32c3bb792eaf3e57f69c045fc17d017c0e09d2c4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Chart5
### Patch Diff Hash-SHA-256:

9b4cdb3c109bfe0e881d5b06ad348fd66ca22a758d3c064915bc6672dc54a79b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.PolarPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Chart5
### Patch Diff Hash-SHA-256:

dcd7191a72b1186467ef02034eb93a568009a306f0e90e77be53af2d562f0e96

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.QuarterDateFormat) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Chart5
### Patch Diff Hash-SHA-256:

17bbd4e2b9d31fb2cc95b7d6435e30c3efd27266a29e9eafe3d239b3961ace08

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index - (maximumItemCount)) > 1) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Chart5
### Patch Diff Hash-SHA-256:

60fed1619985affb643fb47d62b9f4ccd2392d8fe5c5e1081fe6425e58e54cf7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.gantt.SlidingGanttCategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Chart5
### Patch Diff Hash-SHA-256:

4b74491e86a9e095ab8c84465663c2ca650124031926449f0db082bb43f5d2ab

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.urls.StandardPieURLGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Chart5
### Patch Diff Hash-SHA-256:

add3b346b71a9313f1878fa6240460dad73b2f48de246bd39655814f3928fc48

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYTextAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Chart5
### Patch Diff Hash-SHA-256:

0e3a1adca95f032f8445762a3108cfffce6c8c713c92b6e50dd6be153ef3f2bf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > 3) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Chart5
### Patch Diff Hash-SHA-256:

015a3b5a2549ad5e0fd30c400bcc04ed77ac87b381bfaf66ebb403569f3d59fc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (y instanceof org.jfree.data.KeyedValues2D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Chart5
### Patch Diff Hash-SHA-256:

8d3a4b9481f809b9c299399845de510dc586b07dcb2997c674afb5f7e9031242

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((allowDuplicateXValues) && ((x.doubleValue()) > (x.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Chart5
### Patch Diff Hash-SHA-256:

777719039e37bb8f1fd4fcfb96371d4035bbe2e71cfca57528f97d4ee43d5a5f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.EntityBlockParams) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Chart5
### Patch Diff Hash-SHA-256:

e2b663fab16dae2ed3b0a587b917109f4b7ec3b47c82cc64fe617c868f40450b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.data.time.SerialDate.isValidMonthCode(index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Chart5
### Patch Diff Hash-SHA-256:

bead6681a4cb079230883bb988fde25a009e432ef9f5a648c6e104afa478ef2a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.urls.StandardCategoryURLGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Chart5
### Patch Diff Hash-SHA-256:

73c33e554b9ecfbbfdce04a25797831314fdc34f597a37528152366d0f6c741b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(allowDuplicateXValues)) && (!(autoSort))) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Chart5
### Patch Diff Hash-SHA-256:

7ef11e6da6d9b64763706c3276d6cf20cede9f6e918c4092bab29fd0d2c5fd07

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.MeterPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Chart5
### Patch Diff Hash-SHA-256:

54b38397ffabc5327f24912ee6e9319c2b105bba644e1d4db9d0ff1a11b5f9e4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.chart.block.EntityBlockParams) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Chart5
### Patch Diff Hash-SHA-256:

392e236c72fa7919aa25639cb8021fcc2f4f0433e96959652ede8d637332b613

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.StandardXYItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 455 of bug id Chart5
### Patch Diff Hash-SHA-256:

cd02d600fb50fa77f335584f48bba954665fb93ca13556b83a5e747b8440995c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.BoxAndWhiskerXYToolTipGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 456 of bug id Chart5
### Patch Diff Hash-SHA-256:

edfa2e896f386edd924a6418ed9d38315b3ac2cb3e4c84d379047a1357314be0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimePeriod) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 457 of bug id Chart5
### Patch Diff Hash-SHA-256:

235c6235baa7e3a50ce1ad0be58401a36338c586bf098b80e87b4b1b806d9a18

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) == (org.jfree.data.xy.XYSeries.this)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 458 of bug id Chart5
### Patch Diff Hash-SHA-256:

884ef8a65d8a09c552cac40dc314f388072f669b9d14577535229487dadc22d0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < index) && (!(autoSort))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 459 of bug id Chart5
### Patch Diff Hash-SHA-256:

b9c19f20f559d56534cd206edb7404b1b6c0780a43b1998c047eb473dcc13b39

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index > (maximumItemCount)) && (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 460 of bug id Chart5
### Patch Diff Hash-SHA-256:

8e46a054bf850632b66d038998cc04a9fd1e4fe2c22db464e8be4a565f71ab1f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.title.LegendTitle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 461 of bug id Chart5
### Patch Diff Hash-SHA-256:

305679490b29c17837d96dc538671b1edac402aa02afd93ca8c2cfa41102b87e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.MultipleXYSeriesLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 462 of bug id Chart5
### Patch Diff Hash-SHA-256:

62265afe82652945b585fea80e6359c6cbe1a5376d0b3332a50d0af0c6460382

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.KeyedObjects2D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 463 of bug id Chart5
### Patch Diff Hash-SHA-256:

8a2ac86e0b3a5b91f99e13e45651f1f2a029c83d0e36df3d26646c2a23e8ef63

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.DateTick) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 464 of bug id Chart5
### Patch Diff Hash-SHA-256:

6e4c6768749b97bcf03d1b29efe74db328a2a7d94498716bfeaaaca36c7698cd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((y == (data)) || ((y != null) && (y.equals(data)))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 465 of bug id Chart5
### Patch Diff Hash-SHA-256:

62d81d304d05d1f079da94a56afa2630830cd17b736e26b4fbe4ad59bc555136

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index != 0) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 466 of bug id Chart5
### Patch Diff Hash-SHA-256:

273d1259c3941bfcdc53241ea710b0d9e4c7cd4deff248b7a59b5fef82d984f7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.data.time.SerialDate.isLeapYear(maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 467 of bug id Chart5
### Patch Diff Hash-SHA-256:

484083807f4ae628b1a7cbda6e874869a7658e9474cfa8870b36289ccf9fa1dd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (data.equals(overwritten)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 468 of bug id Chart5
### Patch Diff Hash-SHA-256:

1d201af935c9b9384ce8464f33fdaa47e64933af4fb0ab564b03b005fa136196

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYAreaRenderer2) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 469 of bug id Chart5
### Patch Diff Hash-SHA-256:

7a26b03b19c565c584351a0f2aa38c53a5fcab1e26c69f1b6587f1aba9b343cf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > (getItemCount())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 470 of bug id Chart5
### Patch Diff Hash-SHA-256:

ff5063051bf23b1c07b3817eef93de9e822a06061507d76be88e9c443337e70f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.MarkerAxisBand) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 471 of bug id Chart5
### Patch Diff Hash-SHA-256:

084fd2cda8b46f9799e2a81ca6acda11b0b7a3a078f700b0522067572afd3003

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((autoSort) && (!(autoSort))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 472 of bug id Chart5
### Patch Diff Hash-SHA-256:

b2f609fc0fe909b6b93e6338350d97b4fb8238ad8f5e8012032d1eb10407981b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYLineAndShapeRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 473 of bug id Chart5
### Patch Diff Hash-SHA-256:

3c7e51a72ab5db71491d6a7c0eb526169819563215cd898eb4494d07ef0ebcce

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < index) && ((maximumItemCount) < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 474 of bug id Chart5
### Patch Diff Hash-SHA-256:

a35e689970d4e94b73f455f465200d69d645ad76d2631ba40600862566629d1d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.ohlc.OHLCSeriesCollection) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 475 of bug id Chart5
### Patch Diff Hash-SHA-256:

a7adfdf0efcb1f772dc943cc95ffdbc4d6e8af4ee43a831bab31f0348550ec53

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.DefaultIntervalXYDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 476 of bug id Chart5
### Patch Diff Hash-SHA-256:

2727e4e09549a0b152bfce9f81024e56277570c65768ecf2aba79faf68db5477

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.entity.XYAnnotationEntity) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 477 of bug id Chart5
### Patch Diff Hash-SHA-256:

6494a5edeb99da598ba6ec5035900fc8c41041566955a119fb5d22761e7f9f45

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.LabelBlock) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 478 of bug id Chart5
### Patch Diff Hash-SHA-256:

dee2488626ea8ae0c63afd7fdf254a3ce45536443cda427b6b9c5f9cf226b10f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == 0) || ((index > (-4)) && ((maximumItemCount) < 2))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 479 of bug id Chart5
### Patch Diff Hash-SHA-256:

35f6f7f5924f568ba678e3c5513ebdf5da1133429f97772c7bbc0022d4f7107c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x.equals(data)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 480 of bug id Chart5
### Patch Diff Hash-SHA-256:

f9940af051381da5724c8c3dec4da485ae90561a1d50af7db374e7d921116c4d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index < (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 481 of bug id Chart5
### Patch Diff Hash-SHA-256:

0dd0a9fa07aca9e5b4f69b0002dc1e6330a398c04fa7c4e516fbce4c68b0da23

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < (maximumItemCount)) && (!(autoSort))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 482 of bug id Chart5
### Patch Diff Hash-SHA-256:

75a0d46e00002e77f398186c156ad2ab9a5c4ac27587a61a1b6ce760223e1a15

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(allowDuplicateXValues)) && (!(autoSort))) && (!(autoSort))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 483 of bug id Chart5
### Patch Diff Hash-SHA-256:

f6acda9b82c4e17b96eb4f75be6e0d9ee94de5fe45ca2d7b618f0807e79b813f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= 0) && ((maximumItemCount) <= 59)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 484 of bug id Chart5
### Patch Diff Hash-SHA-256:

78354cd1ac59eb9eac69a120ab2f90649eb0f24c2db9e43d678889f80c55b95e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.GanttRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 485 of bug id Chart5
### Patch Diff Hash-SHA-256:

0547cd04add06a05c39063abdfac98c89b4502b2bf501b2cbdbca3d4db7da024

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == ((maximumItemCount) - 1)) && ((maximumItemCount) != 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 486 of bug id Chart5
### Patch Diff Hash-SHA-256:

afc9528475c1a9889fd03f6c4a147f2d9dcc133146a23e0023931712a10a0b84

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((0 == index) && (0 == (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 487 of bug id Chart5
### Patch Diff Hash-SHA-256:

47d35d4db168c2595ea760525ef3d017897d8d13aa93d66a4427653e0f46e803

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof java.util.Date) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 488 of bug id Chart5
### Patch Diff Hash-SHA-256:

f59ed6e33f19366e38dbfc5912b4f6d943c5d394f8d374b8f0433ac39367c2f9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.GradientXYBarPainter) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 489 of bug id Chart5
### Patch Diff Hash-SHA-256:

ef3446b55b21907213573b647a630937634b2ee259cac5f6b1005b0e8620e9e8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialPointer.Pin) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 490 of bug id Chart5
### Patch Diff Hash-SHA-256:

cfe6073d8cc9f0d182e5887c2292c896d745c373b4c09252f5afafd3d5e6dd7d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.GradientBarPainter) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 491 of bug id Chart5
### Patch Diff Hash-SHA-256:

705e91c97c8bd7a8214e6d00456e2f279f735c157894819cdfce9550bb83e3cf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Millisecond) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 492 of bug id Chart5
### Patch Diff Hash-SHA-256:

76c97114056012307ae58337e7c14cb27c51aeab9d56aa836bfc2e59c5b770ac

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYDotRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 493 of bug id Chart5
### Patch Diff Hash-SHA-256:

6ae4595bc4e4b59be04d0a4b504ea4128e6cd2ca70db03712204f0b7ab8baba6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > ((maximumItemCount) - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 494 of bug id Chart5
### Patch Diff Hash-SHA-256:

a5446d73d69512a2a125e63901dfadd5ac556407984c0501432b77d8df1d6c84

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((autoSort) && ((y.doubleValue()) > (y.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 495 of bug id Chart5
### Patch Diff Hash-SHA-256:

01902a863a135acd6bd48a2eaa2e1ccac35b24fd2138c0f5727ebc60c37a7f84

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((autoSort) && ((x.doubleValue()) > (y.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 496 of bug id Chart5
### Patch Diff Hash-SHA-256:

4a4309a6b8c947af76b1994ab2b138e673ceb57e340375c5923d2242175aeece

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.AbstractDialLayer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 497 of bug id Chart5
### Patch Diff Hash-SHA-256:

daec4ee85c3bb39ad64b7dd3c7947be789a1e4bae2af624a3cad39d45cedb54b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(allowDuplicateXValues)) && (!(autoSort))) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 498 of bug id Chart5
### Patch Diff Hash-SHA-256:

827cbfc87e25ed23a32c799c8185ee60b393b5887933879d7b6074715e07227f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index <= (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 499 of bug id Chart5
### Patch Diff Hash-SHA-256:

62a96b237f39cfbc4d34456937753673f708bce124d67224a2775b699483caa7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.category.SlidingCategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 500 of bug id Chart5
### Patch Diff Hash-SHA-256:

4c88b8ad1287b2a999d6e05ec82132131e01a5cf37495c04314c136696bcb483

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimeSeries) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 501 of bug id Chart5
### Patch Diff Hash-SHA-256:

43e1323fe942e7e60cd47bc2ca6befe5532fe1c6f8fd419bf880e3dd02e14d24

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.IntervalCategoryToolTipGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 502 of bug id Chart5
### Patch Diff Hash-SHA-256:

957607d01a35ca0ffd903c56276a4d66fd74e92ca95dbbe28d65753decc4fe2d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < 0) || ((maximumItemCount) < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 503 of bug id Chart5
### Patch Diff Hash-SHA-256:

a1de34d70e2be15751916816962c3c9cbf54e8ee3d53e8857f812afd70faec44

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == (index - 1)) && ((maximumItemCount) != 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 504 of bug id Chart5
### Patch Diff Hash-SHA-256:

38db9eb37d4ce38f8657dbd73a83121b1f1b47e5d6433d038b34d3414d688248

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.StandardTickUnitSource) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 505 of bug id Chart5
### Patch Diff Hash-SHA-256:

1d4cc2549d35d31c98b069f3743d62974b1010536327f16a7d0f814bc3ffce25

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (overwritten instanceof org.jfree.data.time.TimePeriod) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 506 of bug id Chart5
### Patch Diff Hash-SHA-256:

7b18b44ecdbe978bca1cd210510ff2103c1ab239d709783db8e896144dae72f3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.BubbleXYItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 507 of bug id Chart5
### Patch Diff Hash-SHA-256:

bde48d79ce8a0db0d59b97b603a2f488b12598e9cc6592ae0215b4450180b08c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.LogAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 508 of bug id Chart5
### Patch Diff Hash-SHA-256:

50ce4416a3bef7505ae6caa2604eadba636dec37fdeb599e0d81cb47286d5033

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.PointerNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 509 of bug id Chart5
### Patch Diff Hash-SHA-256:

c89cb1fcf95b2b92df33b9877d9d400801093ba51df59fdcb87f3597e088636a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((allowDuplicateXValues) && ((y.doubleValue()) > (y.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 510 of bug id Chart5
### Patch Diff Hash-SHA-256:

4a4cc4b7b2cfe13f67141cb3100a7fe7d97ffa3537009b49543eafa8f8d6e1d3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.ArcDialFrame) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 511 of bug id Chart5
### Patch Diff Hash-SHA-256:

85f83a5f63b92d42364d445bc844cc639ec993ac54b341a6895fb0bf383e0995

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 360) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 512 of bug id Chart5
### Patch Diff Hash-SHA-256:

cc2abc2c1bac2c7af18dcf296a041e2da7b99ee43807a72441dd3d5f4f06e6c3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= ((maximumItemCount) - (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 513 of bug id Chart5
### Patch Diff Hash-SHA-256:

6745c448d2902aeb3c4f122d329bc3c35c0a1c0d46bb961dd81e1e0cc4fad93b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((overwritten != null) && (x != null)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 514 of bug id Chart5
### Patch Diff Hash-SHA-256:

2cbc3c5cd97dd8285f31eeb7af7aed12bb1e76644aad4960b3b0d00304750f45

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.StandardPieSectionLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 515 of bug id Chart5
### Patch Diff Hash-SHA-256:

60385b86d1c3d4ffa103c19c61e97d5b676b94effc2bd44a5a04713312cb537f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.WaterfallBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 516 of bug id Chart5
### Patch Diff Hash-SHA-256:

cc5aa6b01554fccf20a403484cac272b8ad1521d9312bcac67539e43d4fccea1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.CustomXYToolTipGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 517 of bug id Chart5
### Patch Diff Hash-SHA-256:

85d88f4736151e881bb0dc6ec3a272320663548137ce1d7c5babb4666909c034

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.urls.CustomPieURLGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 518 of bug id Chart5
### Patch Diff Hash-SHA-256:

3b9f29f3ba039e069d1b7b8b40a1d06de0704f1596f2bbf4b459ff7ad8e7c30d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.DateAxis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 519 of bug id Chart5
### Patch Diff Hash-SHA-256:

dc8aaa2c6a73baacbec18bef61f43a415ed818d90eec64dc102bd454beea454b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.entity.PieSectionEntity) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 520 of bug id Chart5
### Patch Diff Hash-SHA-256:

6db4b47a61ee39ed5b994d4b24824a13173c1d553929964d3b07145abc88c162

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((!(autoSort)) && (!(allowDuplicateXValues))) && (!(allowDuplicateXValues))) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 521 of bug id Chart5
### Patch Diff Hash-SHA-256:

d9a976c0220f59d164d9941fd46270048fe6e0b01cf7386ccc250adca363a960

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= 1900) && ((maximumItemCount) <= 9999)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 522 of bug id Chart5
### Patch Diff Hash-SHA-256:

faf79b531f2582af57f974541bd7c8ade632b4ae265ad58595aa4450e42ffc94

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index != index) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 523 of bug id Chart5
### Patch Diff Hash-SHA-256:

bf6ada45a8da878a122d95721151b759d29f544b766af641fe71168b58b5c45f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < index) && ((maximumItemCount) < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 524 of bug id Chart5
### Patch Diff Hash-SHA-256:

f895c37074ae53240b3fff171f672a039c8f7a6fbc25f194643e41f3421030e0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.urls.StandardXYURLGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 525 of bug id Chart5
### Patch Diff Hash-SHA-256:

d6971ec53d32fab0f76b27e652828565559d0154e5d2afb15be61cefb2060189

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < (getItemCount())) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 526 of bug id Chart5
### Patch Diff Hash-SHA-256:

0aa7a1249afd1b7b7e011450ea5953f7a55ac013dbb157baa681be290359d972

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.chart.renderer.xy.XYAreaRenderer.SHAPES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 527 of bug id Chart5
### Patch Diff Hash-SHA-256:

b1eb4d895a4b823b1b1cbe0917832106d23c561534f279063180b5ae18725924

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > (org.jfree.data.time.Week.LAST_WEEK_IN_YEAR)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 528 of bug id Chart5
### Patch Diff Hash-SHA-256:

ed3717dcf833250618294ab64ffbad5114f80a15906c57b013d5e46774b388ec

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYDifferenceRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 529 of bug id Chart5
### Patch Diff Hash-SHA-256:

aac1721ddf36a85251e2f619c23a0e3351635526fb4e0b9e724ab10ad9f0021a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((autoSort) != (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 530 of bug id Chart5
### Patch Diff Hash-SHA-256:

402da50a169691b63218750b25ce0ac2fc1d513e9bf2b1aa03165e2fc3f8658e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.chart.renderer.xy.XYAreaRenderer.AREA)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 531 of bug id Chart5
### Patch Diff Hash-SHA-256:

bf8081421d24b210c7e13b847ab056b92aee2a79021defe7cba1f2cc9b23493b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.TickUnits) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 532 of bug id Chart5
### Patch Diff Hash-SHA-256:

5a6d85820822d3d6d1f96160b70659885237975ff90a014eb03b3074cce168fa

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > (org.jfree.data.time.SerialDate.SERIAL_LOWER_BOUND)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 533 of bug id Chart5
### Patch Diff Hash-SHA-256:

43a86547f284696f009c1aa533d938d245513874f3d91d01d097f348d364bd38

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.data.time.SerialDate.INCLUDE_FIRST)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 534 of bug id Chart5
### Patch Diff Hash-SHA-256:

93344286596463b37cbc78e791250a0f063c970f93e2363472b906f2d3c96770

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.CenterArrangement) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 535 of bug id Chart5
### Patch Diff Hash-SHA-256:

5f4ab306b55a5a1b4f8e3b44d3fdef9233f55ae72ca84830ef82025750ffeaa3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.StrokeMap) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 536 of bug id Chart5
### Patch Diff Hash-SHA-256:

97f271031cded6014672311aa8b99c2102c120345805d8b45e72a76b76a4e980

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (java.awt.geom.Rectangle2D.OUT_RIGHT)) == (java.awt.geom.Rectangle2D.OUT_RIGHT)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 537 of bug id Chart5
### Patch Diff Hash-SHA-256:

84a02081056b9bb0bbc4e307c12bdbc1c20f7ee0029c2a3b684d606ff324ff15

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.gantt.Task) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 538 of bug id Chart5
### Patch Diff Hash-SHA-256:

989e7384a65a3063e4910c7eaf660528227f5ba70d490ef5bde5b64e5e97df89

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((allowDuplicateXValues) != (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 539 of bug id Chart5
### Patch Diff Hash-SHA-256:

77d749fa18924c943dc9e9bfb1181e29ac95f5fc5d2f20e92f70bf5ef06c1248

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.chart.plot.CategoryPlot.DEFAULT_DOMAIN_GRIDLINES_VISIBLE) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 540 of bug id Chart5
### Patch Diff Hash-SHA-256:

f154260e896e387706e9b0bbb52a2b48c1f71dc3b97aa2326512887aa0efeecc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.CategoryLabelPosition) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 541 of bug id Chart5
### Patch Diff Hash-SHA-256:

c534bc35a84690c47eaaf3801c1e17910fbe6e9a3654e188cf689dc281f8d552

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.chart.ChartPanel.DEFAULT_BUFFER_USED) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 542 of bug id Chart5
### Patch Diff Hash-SHA-256:

862ab2a48c7502433f3cc0d7d5e4692436fbebf4461881a798efe15238407e9f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.LookupPaintScale) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 543 of bug id Chart5
### Patch Diff Hash-SHA-256:

488baf13547c1f17a044dc016075018baa907c25e81e9a1ab9753475b09783f7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > (org.jfree.data.time.Quarter.LAST_QUARTER)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 544 of bug id Chart5
### Patch Diff Hash-SHA-256:

ef008a46cb2c3a870db059306ff3a818854343c8195931b9f58217d3ae926085

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((autoSort) && ((x.doubleValue()) > (x.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 545 of bug id Chart5
### Patch Diff Hash-SHA-256:

b50012e249620fd21d58bd631c8dcc34f15891ea9a18bb6a86315d7d9139d68b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.entity.LegendItemEntity) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 546 of bug id Chart5
### Patch Diff Hash-SHA-256:

f30155eab0e3c4069350d7cab652a4c01f59978dd1e7f05ee31ffd8573a6f4b9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (java.awt.geom.Rectangle2D.OUT_LEFT)) == (java.awt.geom.Rectangle2D.OUT_LEFT)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 547 of bug id Chart5
### Patch Diff Hash-SHA-256:

a2f385f4a2ef7e58194b639844aea5bc0028d5b69aa05ec222d455602eac3225

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (org.jfree.chart.renderer.xy.XYAreaRenderer.SHAPES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 548 of bug id Chart5
### Patch Diff Hash-SHA-256:

9044a5eea79d53a3e082b104c97b824a517c25d763641de6fd9de01cce7ddadf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.category.DefaultIntervalCategoryDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 549 of bug id Chart5
### Patch Diff Hash-SHA-256:

89ed9311a9777fb3e74846c10c4b14e247464a0491bac5d297b00e8ff3002df7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= 1) && (index <= (org.jfree.data.time.SerialDate.lastDayOfMonth(index, index)))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 550 of bug id Chart5
### Patch Diff Hash-SHA-256:

a43221eedf15462d483fb0c4cdeb8fc5db91204c11ba4553dbea6773c36140f6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.Month) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 551 of bug id Chart5
### Patch Diff Hash-SHA-256:

415d3e11a167ecab8c9197fb8216affd0d5ff6649ec4a490e25e626da8b947c1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= (org.jfree.data.time.SerialDate.SERIAL_LOWER_BOUND)) && (index <= (org.jfree.data.time.SerialDate.SERIAL_UPPER_BOUND))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 552 of bug id Chart5
### Patch Diff Hash-SHA-256:

498f02579e950871e18a1891a0dcf249419f250963572adbb6816a0d197ca6d2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (org.jfree.chart.renderer.xy.XYAreaRenderer.AREA)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 553 of bug id Chart5
### Patch Diff Hash-SHA-256:

bcf87f45dde4caa1bc4d57010ea2c155da68c0ba59a107a63c2db2e63e040421

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.util.Align.FIT_VERTICAL)) == (org.jfree.chart.util.Align.FIT_VERTICAL)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 554 of bug id Chart5
### Patch Diff Hash-SHA-256:

82f7266497181fa6a6f069e8afa24968a448b505d9a042bc308ec3be3f327b7b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (java.awt.geom.Rectangle2D.OUT_BOTTOM)) == (java.awt.geom.Rectangle2D.OUT_BOTTOM)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 555 of bug id Chart5
### Patch Diff Hash-SHA-256:

9d26f1e62c6f2a6d051da82bf5401b16a031e93fb133d436e02f11a1ff1ee2a2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.ThermometerPlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 556 of bug id Chart5
### Patch Diff Hash-SHA-256:

c0653cb65e1211dd2d4d7f07f51296a17550a19d6a2ef8fa8c1db32647804e14

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(autoSort)) && (java.awt.RenderingHints.VALUE_ANTIALIAS_OFF.equals(data))) || ((autoSort) && (java.awt.RenderingHints.VALUE_ANTIALIAS_ON.equals(data)))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 557 of bug id Chart5
### Patch Diff Hash-SHA-256:

65289f263f618bd9cd8ba4dfe6ec2c9ebfc99aaab7a7f5e276ddcf4a0f95b07f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.data.general.PieDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 558 of bug id Chart5
### Patch Diff Hash-SHA-256:

98fe666a4682f17816c4d92576b33ef85e953107d689ca7db0f52eab5622e369

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.general.DatasetGroup) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 559 of bug id Chart5
### Patch Diff Hash-SHA-256:

86c8b2e841bf54542db844575e7cb13bf442ae6dbc425d4fd7d0b6628badbbc0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.util.Align.BOTTOM)) == (org.jfree.chart.util.Align.BOTTOM)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 560 of bug id Chart5
### Patch Diff Hash-SHA-256:

6592ee13944807749212d8b256e2d8b9b25c4087b7b0ad485370031b4ad99891

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) != (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 561 of bug id Chart5
### Patch Diff Hash-SHA-256:

ed67870fc98c2d7c9be3112d579b9e83e1a4bba7410b77c46b148255883e9bf3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < (org.jfree.data.time.Week.FIRST_WEEK_IN_YEAR)) && (index > (org.jfree.data.time.Week.LAST_WEEK_IN_YEAR))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 562 of bug id Chart5
### Patch Diff Hash-SHA-256:

fde6684d15e8b340234b84c6444e42c53b1d276c68783cab56f6949579752c4b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.BooleanList) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 563 of bug id Chart5
### Patch Diff Hash-SHA-256:

7daf6336f65bd36cd0aa0fd78eda45916461d3c0ac7464aa46c4d9c49f91cd6f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -188,7 +188,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(java.lang.Number x, java.lang.Number y) {
-		if (x == null) {
+		if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_CROSSHAIR_VISIBLE) {
 			throw new java.lang.IllegalArgumentException("Null 'x' argument.");
 		}
 		org.jfree.data.xy.XYDataItem overwritten = null;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 564 of bug id Chart5
### Patch Diff Hash-SHA-256:

d4226546f6dc4670805c3ec63d392f2679bdedb62a1eacda7d1732df2baa86f3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= (org.jfree.data.time.MonthConstants.JANUARY)) && (index <= (org.jfree.data.time.MonthConstants.DECEMBER))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 565 of bug id Chart5
### Patch Diff Hash-SHA-256:

ce5cf0dcba20d4b8c1f52d7e5c18eb9217ccd88de7e9fc09fd63623be1de3737

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((autoSort) && (!(autoSort))) || ((!(autoSort)) && (autoSort))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 566 of bug id Chart5
### Patch Diff Hash-SHA-256:

c2f6964540317dbe8a6758ecc7eaeb8cdd64f0527c26504c447e7e459a1527fe

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.KeyedValues2D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 567 of bug id Chart5
### Patch Diff Hash-SHA-256:

23572c4c42c9ed061a34e4e6f7376e30dee8baddc34b96d46855d9a82aa44493

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.YInterval) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 568 of bug id Chart5
### Patch Diff Hash-SHA-256:

cfc8b8d4886f972000140132073795132ff095d92058c1e1492a9211ec188ab4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.gantt.XYTaskDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 569 of bug id Chart5
### Patch Diff Hash-SHA-256:

2f4b81e6e1785b43c8b5d4c30de7eb7c84a9d6ed3086de685012e2497ac298c0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.XYShapeAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 570 of bug id Chart5
### Patch Diff Hash-SHA-256:

5c0b4a7e7c8ff895b4a2776fc11caffacfa71c12e80019144602f6cbcb4b4313

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index >= (org.jfree.data.time.SerialDate.SERIAL_LOWER_BOUND)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 571 of bug id Chart5
### Patch Diff Hash-SHA-256:

9abfb574e233fbb485a27b59e7a19926eec1cadf34fe164264c0af6511743643

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -207,7 +207,7 @@
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
-			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
+			if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_DOMAIN_GRIDLINES_VISIBLE) {
 				org.jfree.data.xy.XYSeries.this.data.remove(0);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 572 of bug id Chart5
### Patch Diff Hash-SHA-256:

e368ebe73fa590f148b0f8e068fd2513d82a3e5bb2e515caf372ac522e91ee56

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYLine3DRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 573 of bug id Chart5
### Patch Diff Hash-SHA-256:

a3c223087526599dcdcb0a36bbc1cd7b9ca309f88cbf43eb07ead3cd33b965f9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = org.jfree.chart.axis.ValueAxis.DEFAULT_INVERTED) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 574 of bug id Chart5
### Patch Diff Hash-SHA-256:

d63e6c0c7b06ba965e27f104eb779fb3260241680f40d37c436eb06dd4619386

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.LINES)) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 575 of bug id Chart5
### Patch Diff Hash-SHA-256:

32cb662c5c18711bf3088e3107bb7f581ca116aeca9897fae5e67210bd86b953

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (java.awt.geom.Rectangle2D.OUT_TOP)) == (java.awt.geom.Rectangle2D.OUT_TOP)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 576 of bug id Chart5
### Patch Diff Hash-SHA-256:

3022ada2bbc4208a2dc1b584eb3a590c21ae23485ff46442622d9bb9b1a2b360

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(autoSort)) && (java.awt.RenderingHints.VALUE_ANTIALIAS_OFF.equals(x))) || ((autoSort) && (java.awt.RenderingHints.VALUE_ANTIALIAS_ON.equals(x)))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 577 of bug id Chart5
### Patch Diff Hash-SHA-256:

3da77936bcfc89d57c92be0acf9d1db3fda3339547e50ab5e2053a893521997e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.util.Align.RIGHT)) == (org.jfree.chart.util.Align.RIGHT)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 578 of bug id Chart5
### Patch Diff Hash-SHA-256:

1e3b5bad9b4f2ae0e41bfa1b014d82387132089f5857e2d43c302fa137d6abcf

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.GroupedStackedBarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 579 of bug id Chart5
### Patch Diff Hash-SHA-256:

50347244237dee5ff8c30ed522f94d64eaa38ba9a142c17337eb0e6dba100b9c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.RectangleInsets) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 580 of bug id Chart5
### Patch Diff Hash-SHA-256:

0e558ccecb4a05b0c33ef33cb435d52373127d1a88a54d357b60457c8693ebc8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.PiePlot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 581 of bug id Chart5
### Patch Diff Hash-SHA-256:

43c553846acc5951d576830fcb2e8044d8045e9cd141446c4bf5339110ab7d5e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (java.awt.RenderingHints.VALUE_ANTIALIAS_OFF.equals(data)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 582 of bug id Chart5
### Patch Diff Hash-SHA-256:

5ee7806032e690829c6d3f9153567219a41bd6d2827f85d2b1fb50e0838c3394

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.util.PaintList) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 583 of bug id Chart5
### Patch Diff Hash-SHA-256:

67ae3f708bbd8028e7bb15827cb2831ae8eedff2a4fb1b386e6d96ac93e3889b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > (org.jfree.data.time.Year.MAXIMUM_YEAR)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 584 of bug id Chart5
### Patch Diff Hash-SHA-256:

58e5cd7c62eac2447e92c1886bc8934f9029d2599c84853f560b8822c9514cd0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x == y) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 585 of bug id Chart5
### Patch Diff Hash-SHA-256:

d6043cb05c9f8d539c38a375d14fe0d79f718541cc25e81b9b08d14d335331d0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.util.Align.LEFT)) == (org.jfree.chart.util.Align.LEFT)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 586 of bug id Chart5
### Patch Diff Hash-SHA-256:

95613368a6c9f9ba5bf416d558ec65150f347b5bedb16bb5a7c7bf045293be0c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.HistogramBin) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 587 of bug id Chart5
### Patch Diff Hash-SHA-256:

cd4b2d613bd77c90bdb39908c614b70bd2783019066813ad0e619665453c0271

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof java.awt.Color) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 588 of bug id Chart5
### Patch Diff Hash-SHA-256:

33543250519f93451b46b839196bfcea5b5735db4e08a39b8f25f1a86225e733

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((org.jfree.data.xy.XYSeries.this.data.size()) > (maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 589 of bug id Chart5
### Patch Diff Hash-SHA-256:

1284b4a2e8a7ff8ffa9a386bb55083761f1ce2ad5895a5f5735ba0d4ded99f79

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.DefaultHighLowDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 590 of bug id Chart5
### Patch Diff Hash-SHA-256:

a95d7b860137a8ad369632b03b06fea67cf3640e9e8bb76e417e4b0ef4d3e3bc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.DefaultXYDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 591 of bug id Chart5
### Patch Diff Hash-SHA-256:

732bc3ed26bf39071c0d12a0c2279eff7b318241f3e3f895105c575cb7c7f019

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.statistics.HistogramDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 592 of bug id Chart5
### Patch Diff Hash-SHA-256:

334ffeb62e2455e9633b3e53df0cf9f6ed3e59bbc6116c8e9559506657932a0d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.AbstractCategoryItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 593 of bug id Chart5
### Patch Diff Hash-SHA-256:

2e28261dbf876bc4e82f529c5d9b2860a416678cb7e34af73a9c12c2dccbea6e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.ColorBlock) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 594 of bug id Chart5
### Patch Diff Hash-SHA-256:

448b5854c1b7a2d29013721bc0d48d1e7d8fbf58bfaa8d88f9454f8227611002

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (org.jfree.data.time.SerialDate.INCLUDE_FIRST)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 595 of bug id Chart5
### Patch Diff Hash-SHA-256:

ed2c400c1069ea52e9f9223eb14ab4b7fda69641aaa5bd6a9c42d3b0b5ddec10

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (data.remove(overwritten)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 596 of bug id Chart5
### Patch Diff Hash-SHA-256:

397e6b3b51b0c2bb80d9fe0b6e33cf3a1645e403c5f6ce4d16d48c99e6b864e7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.XYSplineRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 597 of bug id Chart5
### Patch Diff Hash-SHA-256:

4774d1f42aa3c6e9812b21f3542a0163781c37200c42d81769a7deed1223db26

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.xy.HighLowRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 598 of bug id Chart5
### Patch Diff Hash-SHA-256:

675d86c74307c3a3b581964fb52a13c419317fb9626e1df88fbd887606ffca1e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < 0) || (index > 2)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 599 of bug id Chart5
### Patch Diff Hash-SHA-256:

5835e4f3ba615b6226818d10e4ab016d11fc69b8e646ae18ce9557364d7206d9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index < (org.jfree.data.time.Year.MINIMUM_YEAR)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 600 of bug id Chart5
### Patch Diff Hash-SHA-256:

df1e816c8400994761bfd0179e81c766b7b2bf17c10b43c6ba43c968e5768d6e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.util.Align.TOP)) == (org.jfree.chart.util.Align.TOP)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 601 of bug id Chart5
### Patch Diff Hash-SHA-256:

46c7a1d866a36b5c350f2e5cc98378037d5b6eef245f288ba3e4a41a93235d1e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.chart.renderer.xy.XYAreaRenderer.LINES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 602 of bug id Chart5
### Patch Diff Hash-SHA-256:

4b51101e1a39feb75110ca35c1580f17c8fe5526ad77bcd0ebb110e65ff433c5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((!(autoSort)) && (!(autoSort))) && (!(autoSort))) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 603 of bug id Chart5
### Patch Diff Hash-SHA-256:

468d2865a003a2b0f833add9b38f489a0adf53733ec275924ada72b617ee3ef5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(autoSort)) && (java.awt.RenderingHints.VALUE_ANTIALIAS_OFF.equals(y))) || ((autoSort) && (java.awt.RenderingHints.VALUE_ANTIALIAS_ON.equals(y)))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 604 of bug id Chart5
### Patch Diff Hash-SHA-256:

b776f7cba4e073b7320b77da9fcd9035dd78c46938fd9bc23a339f1a58bbb744

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == 0) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 605 of bug id Chart5
### Patch Diff Hash-SHA-256:

0f5468d5da91bdd306d55f181ab57d06c90b324aa70a74f4d2267b445f801163

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) == index) && (index == index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 606 of bug id Chart5
### Patch Diff Hash-SHA-256:

f24705ddb54df8c5dabe88eecde91a17a5c66521e78e6fe486b91a968cd85d2a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == (maximumItemCount)) && (index == index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 607 of bug id Chart5
### Patch Diff Hash-SHA-256:

6e66dfbd22b25be3fb2cc0150a8a88699e1a7959a4327a6584505667efd28a9a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.MinMaxCategoryRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 608 of bug id Chart5
### Patch Diff Hash-SHA-256:

52595c11ca599eb530adc151abac53af9250d99463b040f98573b74e07909111

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == index) && ((maximumItemCount) == index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 609 of bug id Chart5
### Patch Diff Hash-SHA-256:

ee8560cf0ee78184ee99f69ba2851f765297ca3624bb046d2e44a53825d2048a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < index) && ((overwritten.compareTo(org.jfree.data.xy.XYSeries.this.data.get(index))) == 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 610 of bug id Chart5
### Patch Diff Hash-SHA-256:

71c4d539bdf19c59d9bb1ef2e6e7cfd7d4020a00e4c7e4fdce4b93fd5188ca56

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index >= (org.jfree.data.time.MonthConstants.JANUARY)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 611 of bug id Chart5
### Patch Diff Hash-SHA-256:

402b838150337cdc1341d1ef9c61a61b300dd34e1bc06a5ea15cb0cf7363be77

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.IMAGES)) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 612 of bug id Chart5
### Patch Diff Hash-SHA-256:

1ee495b3ef79e1271f9f80345e8b9acdd4389888a521a66f727554659ee6f5d7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((!(allowDuplicateXValues)) && (!(allowDuplicateXValues))) && (!(allowDuplicateXValues))) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 613 of bug id Chart5
### Patch Diff Hash-SHA-256:

d75bea6e3332eac2f497c9db1a1d1ff871a53c17bc11605d4d5efff3e71e0748

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.XYSeries) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 614 of bug id Chart5
### Patch Diff Hash-SHA-256:

eefdab8ae40499e1df3ef2f29af3512900928bc295800c50add3b130c047081f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.text.TextFragment) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 615 of bug id Chart5
### Patch Diff Hash-SHA-256:

92333d4382fcc9f1a1d123e73284be4649faecf4122a31a62e92e066aefa8173

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < 9999) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 616 of bug id Chart5
### Patch Diff Hash-SHA-256:

4a1dc96352ef3551d743fc7b47ad35d5a016ee1cbc85c47e5a627e28ce348bd4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.ui.StrokeSample) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 617 of bug id Chart5
### Patch Diff Hash-SHA-256:

65cfd241b5cf921504b43dd68b57a2acb44b249029c42764808c76d4c2b4494a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -207,7 +207,7 @@
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
-			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
+			if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_CROSSHAIR_VISIBLE) {
 				org.jfree.data.xy.XYSeries.this.data.remove(0);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 618 of bug id Chart5
### Patch Diff Hash-SHA-256:

1c0c869b5093ae2bea325a74c38bb49bb6a911c3cc2dec911ddef6e43d60c6f3

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = !(allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 619 of bug id Chart5
### Patch Diff Hash-SHA-256:

c93838fec646d7898a07423bd78ea004e7e21a0eb55f1f3f87351512d81cba85

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index != (org.jfree.chart.plot.CompassPlot.NO_LABELS)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 620 of bug id Chart5
### Patch Diff Hash-SHA-256:

094707f382b57efc07bec7fbdba357b70ebd29502dff41569caa25c13b893593

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= (org.jfree.data.time.MonthConstants.JANUARY)) && ((maximumItemCount) <= (org.jfree.data.time.MonthConstants.DECEMBER))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 621 of bug id Chart5
### Patch Diff Hash-SHA-256:

0cbf594c01eb9bc96c8601035a8a091ccfbcf23d147c758fb5786c0ca1bcf5d4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.time.TimeSeriesDataItem) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 622 of bug id Chart5
### Patch Diff Hash-SHA-256:

b4705ebbec37201ddadc968a653c47f24aeab6e449dc5792d3d11f0763ada0a1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= index) && (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 623 of bug id Chart5
### Patch Diff Hash-SHA-256:

8826d16b9da7f56fb0eb681409f40420a0f5ee1756389a8780e6e40d9c293b6a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -207,7 +207,7 @@
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
-			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
+			if (autoSort = org.jfree.chart.axis.ValueAxis.DEFAULT_INVERTED) {
 				org.jfree.data.xy.XYSeries.this.data.remove(0);
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 624 of bug id Chart5
### Patch Diff Hash-SHA-256:

f8e1aa10d9f22e5f529d54aae24d2d6a9d8d3c308fae58660b6e73e8af690826

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > 1900) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 625 of bug id Chart5
### Patch Diff Hash-SHA-256:

2ecbcfb1a6b95082369b152440dcbea234bf6e944b638cc383c3c504c4e6c727

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.chart.plot.CategoryPlot.DEFAULT_CROSSHAIR_VISIBLE) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 626 of bug id Chart5
### Patch Diff Hash-SHA-256:

9781c34b17afa8295f10c36a822b1acaad5c72f97a7bc58b0f062d1dd24d6079

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.StandardXYSeriesLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 627 of bug id Chart5
### Patch Diff Hash-SHA-256:

eabfa2ccceed228863d4a087c835c83187d93547ffaf8cf0d1fa6e1ac4edbb94

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.StandardCategorySeriesLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 628 of bug id Chart5
### Patch Diff Hash-SHA-256:

34413210d1863d7bc02cf853ba578763fc9f60566ea9debb4854ba9eb70536b6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index > index) && (index <= index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 629 of bug id Chart5
### Patch Diff Hash-SHA-256:

51737d92aa86a0940ecbdd38656ad221f3603513ecb6011160dd3fc0432b7307

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= (org.jfree.chart.axis.ValueAxis.MAXIMUM_TICK_COUNT)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 630 of bug id Chart5
### Patch Diff Hash-SHA-256:

bbe72934865ce6c1dabff5b30256f61cd6f29fc092fa0b8654c48310f51b78f0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index != (org.jfree.data.time.Millisecond.FIRST_MILLISECOND_IN_SECOND)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 631 of bug id Chart5
### Patch Diff Hash-SHA-256:

aca09279a8d843e1ec346bbccdc5e98043dc2a5e17abde62aa9f91ae2d9bafd9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(autoSort)) && (java.awt.RenderingHints.VALUE_ANTIALIAS_OFF.equals(data))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 632 of bug id Chart5
### Patch Diff Hash-SHA-256:

42beadf4efa8ec29521406d1e80d4aa165939661a9b562a4fcfbdb71002459a9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((autoSort) && (java.awt.RenderingHints.VALUE_ANTIALIAS_ON.equals(data))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 633 of bug id Chart5
### Patch Diff Hash-SHA-256:

778e7afdccdd4b201b9d8473d3da3d5cd182b25bd07e60192f0b8f8ed18dae93

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.util.Align.FIT_HORIZONTAL)) == (org.jfree.chart.util.Align.FIT_HORIZONTAL)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 634 of bug id Chart5
### Patch Diff Hash-SHA-256:

a3baf4ab76e26a060e28fd7730bf0c6c03b527050156c22dcc57a11cc2dbbbb2

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index > (org.jfree.data.time.MonthConstants.FEBRUARY)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 635 of bug id Chart5
### Patch Diff Hash-SHA-256:

57c9294090691c44f0fb094f30b7fcfcbe23ebcb5362db3bf72e52d8f1ed2337

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < index) && (!(allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 636 of bug id Chart5
### Patch Diff Hash-SHA-256:

fd4b9822897f67b09bd062201bdcd394f191c51ecbe16fa54ddf1ffd24f3f9a5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.chart.renderer.xy.XYAreaRenderer.AREA_AND_SHAPES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 637 of bug id Chart5
### Patch Diff Hash-SHA-256:

e1cac8ac8e982f4a871eb1287ad757d0a46cbcdb3c59d37cee981a951dcb16fd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.entity.ChartEntity) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 638 of bug id Chart5
### Patch Diff Hash-SHA-256:

38074a717fd9f6c8e11a7b7ef3f11d66bed2abadcb0c45bc0a28ef93f3bf3ed9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.AREA_AND_SHAPES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 639 of bug id Chart5
### Patch Diff Hash-SHA-256:

a5b653d1101bbf9b2b15acf2db3916d9d9af6f790fdd613a4f451bca12e5f237

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.WindNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 640 of bug id Chart5
### Patch Diff Hash-SHA-256:

fbebeabf0eaf74f8c7740c34c967ca970617acc311f1d49bba83e01fdd3b601f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.axis.Axis) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 641 of bug id Chart5
### Patch Diff Hash-SHA-256:

4f1af23a04d4ebc4b7c31d99a82aa873c6bd3a7195eb2bb7f1a12799fddd8693

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.AbstractRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 642 of bug id Chart5
### Patch Diff Hash-SHA-256:

279fc94f5c7d39f58b648ed04d52b864d01c4fb67a8ce0038e7bb191fd2ab065

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (java.awt.RenderingHints.VALUE_ANTIALIAS_ON.equals(data)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 643 of bug id Chart5
### Patch Diff Hash-SHA-256:

1e87a3d05e851b0ae172e2bd8ade9b1d812205c6b467bd6e0e52e9e18d3e5f45

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (!(org.jfree.data.xy.XYSeries.this.allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 644 of bug id Chart5
### Patch Diff Hash-SHA-256:

f532767093dcdf23056454589b3165491002d6e3ca49cbe8332a0582e02443b7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((!(allowDuplicateXValues)) && (!(allowDuplicateXValues))) && (allowDuplicateXValues)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 645 of bug id Chart5
### Patch Diff Hash-SHA-256:

9cd0ac084db465d07a4bd13ee77f30f65574084f7e2c0c9c8c391d8938745cda

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.SHAPES)) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 646 of bug id Chart5
### Patch Diff Hash-SHA-256:

6e53d9d5ad5c49666e8eec304eb723f928885b5c5806542cabe1a361d6563db5

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((autoSort) && ((x.doubleValue()) > (x.doubleValue()))) || ((!(autoSort)) && ((x.doubleValue()) < (x.doubleValue())))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 647 of bug id Chart5
### Patch Diff Hash-SHA-256:

ec28df1121cc5e0d353d83861d37e39b6acf07dbdda243977b86419752416aeb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.dial.DialCap) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 648 of bug id Chart5
### Patch Diff Hash-SHA-256:

b5814f16d2aa50da4e317186899b15ca8f670e880f1dceafa2af7272cb25c936

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= 180) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 649 of bug id Chart5
### Patch Diff Hash-SHA-256:

2aabd7dc34c2b7ef31a33aba4f2c1cf7b6957274b9287087d47513c6101276bb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -216,7 +216,7 @@
 	}
 
 	public int indexOf(java.lang.Number x) {
-		if (org.jfree.data.xy.XYSeries.this.autoSort) {
+		if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_DOMAIN_GRIDLINES_VISIBLE) {
 			return java.util.Collections.binarySearch(org.jfree.data.xy.XYSeries.this.data, new org.jfree.data.xy.XYDataItem(x, null));
 		}else {
 			for (int i = 0; i < (org.jfree.data.xy.XYSeries.this.data.size()); i++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 650 of bug id Chart5
### Patch Diff Hash-SHA-256:

b10a35fbe0f7d8413416f6b1f8ce4c40c21cc63c533d12efcbaf62389e4532dc

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.FlowArrangement) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 651 of bug id Chart5
### Patch Diff Hash-SHA-256:

304502faf69a7afdfccc641f953c7ef2c4f824c2612906f1c0fdc50f3887dcc1

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.data.xy.MatrixSeries) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 652 of bug id Chart5
### Patch Diff Hash-SHA-256:

a3a57fa9580e5957aff30b8d05ce33b04c28e13828c5df30f77ad12aae030b86

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.AREA)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 653 of bug id Chart5
### Patch Diff Hash-SHA-256:

4d6f80998b4cc100c0211c625200bf726ca4577b14119deca1960c7df36c4219

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (org.jfree.chart.axis.ValueAxis.DEFAULT_INVERTED) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 654 of bug id Chart5
### Patch Diff Hash-SHA-256:

7cd5bc251b8a6e4d33d36a1cbaa69216e58ace716a6f5dd054857caa93a870b9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.annotations.TextAnnotation) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 655 of bug id Chart5
### Patch Diff Hash-SHA-256:

fe899bd5261cf0f6344d60daa5b7b85fe04ed1f51b83030cb286e7719ccdca6c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -188,7 +188,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(java.lang.Number x, java.lang.Number y) {
-		if (x == null) {
+		if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_DOMAIN_GRIDLINES_VISIBLE) {
 			throw new java.lang.IllegalArgumentException("Null 'x' argument.");
 		}
 		org.jfree.data.xy.XYDataItem overwritten = null;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 656 of bug id Chart5
### Patch Diff Hash-SHA-256:

0afba0a1ba52c10147ad2ccd3c3f7d17297748450a244bbacd6df7ca085172cd

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((!(autoSort)) && ((x.doubleValue()) < (x.doubleValue()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 657 of bug id Chart5
### Patch Diff Hash-SHA-256:

3c81dd9bb2d66ce4298b0391d69c4ca04756bad09c74e170ae7b683cd57ffe7f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.AREA)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 658 of bug id Chart5
### Patch Diff Hash-SHA-256:

53cdfbda227525e588f026541dea4b3a5d2fe32311cd8a00d581a7708819d744

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.PlumNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 659 of bug id Chart5
### Patch Diff Hash-SHA-256:

bfc5f0565b866da0ac510fae13e16f721533963bec118af466de9fe608252cb0

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.LineRenderer3D) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 660 of bug id Chart5
### Patch Diff Hash-SHA-256:

87b7499cae7b5a0e4031934a7a98986c8bafe70fa78f2b51825426f1c1e2086d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index != (org.jfree.chart.plot.CompassPlot.NO_LABELS)) && (index != (org.jfree.chart.plot.CompassPlot.VALUE_LABELS))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 661 of bug id Chart5
### Patch Diff Hash-SHA-256:

79c158d363f153fa7a7a3e5e900bef642c92c92ce798b6f96516a18afa115c52

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -188,7 +188,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(java.lang.Number x, java.lang.Number y) {
-		if (x == null) {
+		if (autoSort = org.jfree.chart.axis.ValueAxis.DEFAULT_INVERTED) {
 			throw new java.lang.IllegalArgumentException("Null 'x' argument.");
 		}
 		org.jfree.data.xy.XYDataItem overwritten = null;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 662 of bug id Chart5
### Patch Diff Hash-SHA-256:

e3715eddb1c34b85b5822cdb1903b865c4f22ae585b15cb1773caa4709809775

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.ShipNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 663 of bug id Chart5
### Patch Diff Hash-SHA-256:

ea8d70e0f464c9263123ad82d270f5967923acf130cba859247b7ef73607950c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (java.awt.RenderingHints.VALUE_ANTIALIAS_ON.equals(x)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 664 of bug id Chart5
### Patch Diff Hash-SHA-256:

9fd75f86da1356cbcc42dd3a46d8f66eb55d28cf1385fc6274a07f6b90123373

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (java.text.BreakIterator.DONE)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 665 of bug id Chart5
### Patch Diff Hash-SHA-256:

c28f1ba959edee493f56c6718d63783c23d88a58533f8a9e3eabb9b63fd9734e

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.BarRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 666 of bug id Chart5
### Patch Diff Hash-SHA-256:

cedd46116187f1092f2688c3e9a53db6f076a24603d8646a35b5d16a87e2d13d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((((!(allowDuplicateXValues)) && (!(autoSort))) && (!(autoSort))) && (autoSort)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 667 of bug id Chart5
### Patch Diff Hash-SHA-256:

1257cd6b0a9c8cf0b1fdb6c0c23791cc39618f6ccd4ada6a52c1344ed20fb954

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((super.equals(data)) && ((data) instanceof org.jfree.chart.needle.MiddlePinNeedle)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 668 of bug id Chart5
### Patch Diff Hash-SHA-256:

72a9aba3d279bd941376b939808a7ddbc1428e297a18467c0c1e448b83e308e9

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (org.jfree.chart.renderer.xy.XYAreaRenderer.AREA_AND_SHAPES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 669 of bug id Chart5
### Patch Diff Hash-SHA-256:

e16fa7fc1967be9cf8874d5da6258f6f36a48bfbe2115792b52ee895dacf409f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.AREA_AND_SHAPES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 670 of bug id Chart5
### Patch Diff Hash-SHA-256:

a8a8a545606af9d03bea9edc413b3bc8e71b8656fba47b169941bab6a849039d

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.labels.HighLowItemLabelGenerator) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 671 of bug id Chart5
### Patch Diff Hash-SHA-256:

6822d4ac4b695a06fda82fce0cc49c444870c30f541af46939b507f3c4b5ea07

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.category.AbstractCategoryItemRenderer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 672 of bug id Chart5
### Patch Diff Hash-SHA-256:

6c0e08bfe0571ab3188666c6e37f278054ca66bf17bbd6b6a733d84431e754c7

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.needle.LongNeedle) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 673 of bug id Chart5
### Patch Diff Hash-SHA-256:

a332eedc6644571657a4c1a2f6d3b943a2e7a33d9f83aed717cab977a347b067

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_CROSSHAIR_VISIBLE) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 674 of bug id Chart5
### Patch Diff Hash-SHA-256:

20d0d3cc8cf0658ae612443b447a943efd6f567a7e3057fc25f568d5d1bf6cd8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.plot.Plot) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 675 of bug id Chart5
### Patch Diff Hash-SHA-256:

b90afdc02803562925bdde9121fe8dd03b0471f9c196787f97d6db6b292527c4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((getItemCount()) > (org.jfree.data.xy.XYSeries.this.maximumItemCount)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 676 of bug id Chart5
### Patch Diff Hash-SHA-256:

0f91f3a243d94623be0cb72d9e3117f25efcf9565abc7b761a43c34e7ef95970

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -216,7 +216,7 @@
 	}
 
 	public int indexOf(java.lang.Number x) {
-		if (org.jfree.data.xy.XYSeries.this.autoSort) {
+		if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_CROSSHAIR_VISIBLE) {
 			return java.util.Collections.binarySearch(org.jfree.data.xy.XYSeries.this.data, new org.jfree.data.xy.XYDataItem(x, null));
 		}else {
 			for (int i = 0; i < (org.jfree.data.xy.XYSeries.this.data.size()); i++) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 677 of bug id Chart5
### Patch Diff Hash-SHA-256:

ade988e200a8cfa72001f4d64d45266e0e724d3ca0aac064cab2301900b53c1c

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index % 4) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 678 of bug id Chart5
### Patch Diff Hash-SHA-256:

d4288bf0e0a9ac06adf222f17337e9545a33dd2b1be646837b4e5337e60ad896

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.data.time.SerialDate.INCLUDE_SECOND)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 679 of bug id Chart5
### Patch Diff Hash-SHA-256:

1b64477bfda007781c289e76fa00f21a898c69c6aaab3b27992a731f033fc1b6

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == (index - 1)) && (index != 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 680 of bug id Chart5
### Patch Diff Hash-SHA-256:

842fe3eca81efba4e4492689389984d360a7cfd21fc934c0eeb84c63ba0aeb7a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (index == (org.jfree.chart.renderer.xy.XYStepAreaRenderer.SHAPES)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 681 of bug id Chart5
### Patch Diff Hash-SHA-256:

a31cde847bc0410571a5b594e8f9dba4cfb49754be0f5f8db15ab841fcffdf26

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (x instanceof org.jfree.data.general.ValueDataset) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 682 of bug id Chart5
### Patch Diff Hash-SHA-256:

23b13206439f93b94f973adf5bd77a163706d88683c954e96817e2b92a0d4961

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == 0) && (index > 0)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 683 of bug id Chart5
### Patch Diff Hash-SHA-256:

1772c7133450758529ba1b898bc92b7b8bfd5a30a9ca4d602d7ff554d851aadb

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < index) && (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 684 of bug id Chart5
### Patch Diff Hash-SHA-256:

67139cc45ad69dec07de842698a08e806d494e1510ca64dcd65bb6762276e0de

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = org.jfree.chart.plot.CategoryPlot.DEFAULT_DOMAIN_GRIDLINES_VISIBLE) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 685 of bug id Chart5
### Patch Diff Hash-SHA-256:

a42c21529c580dca4d2bdda787692c39f4fea7812e29218bff29ed1adcd2bf69

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) < (org.jfree.data.time.Year.MINIMUM_YEAR)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 686 of bug id Chart5
### Patch Diff Hash-SHA-256:

56655b58e0ee2fe2cdb0ffc0bef5a1d59755221d705f5714a466659ce850d683

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) < (org.jfree.data.time.Week.FIRST_WEEK_IN_YEAR)) && ((maximumItemCount) > (org.jfree.data.time.Week.LAST_WEEK_IN_YEAR))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 687 of bug id Chart5
### Patch Diff Hash-SHA-256:

8701119f24c94a67e3e78f37a5b7baff6e80de92d7c647f06b42720f89cfd59b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= 0) && (index < index)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 688 of bug id Chart5
### Patch Diff Hash-SHA-256:

1dcb824a7c44903c91821883bb49497c23bc9dfd529e10458e7e47404ba23f1b

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (autoSort = index == (index - 1)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 689 of bug id Chart5
### Patch Diff Hash-SHA-256:

397932347794ebb10282c2a851e03004312dd9cc72e9a89aedd12fdede945d64

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.GridArrangement) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 690 of bug id Chart5
### Patch Diff Hash-SHA-256:

e68ad17baf42a3827702aaf9bd6c7f1e4af0ecf7aabdbbd53b13494fb8d8b03f

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.renderer.GrayPaintScale) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 691 of bug id Chart5
### Patch Diff Hash-SHA-256:

ba1de66df2d47cab57025458317dec10f4292208ecce1aa14820a5c947df2a90

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index == index) && (index == (maximumItemCount))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 692 of bug id Chart5
### Patch Diff Hash-SHA-256:

5799ef09e43b6ea3c6b14a65059587319fa3e4a5e8fbe7efb175142ae0c73e28

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if (((maximumItemCount) >= (org.jfree.data.time.Hour.FIRST_HOUR_IN_DAY)) && ((maximumItemCount) <= (org.jfree.data.time.Hour.LAST_HOUR_IN_DAY))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 693 of bug id Chart5
### Patch Diff Hash-SHA-256:

f9e0d5e6a991576f9a9ac94e11d13f2394832729e5a1ce17a4b1ced80a1e2ce8

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index >= 0) && (!(org.jfree.data.xy.XYSeries.this.allowDuplicateXValues))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 694 of bug id Chart5
### Patch Diff Hash-SHA-256:

f82721d9f72122e5e87868f858e3f76621f5a53c35a430f85095fcb5d4b6760a

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((data) instanceof org.jfree.chart.block.BlockContainer) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 695 of bug id Chart5
### Patch Diff Hash-SHA-256:

fe5f79a6da616964f2daa17c5d984b04d1a49da0d996f33b1163dc846fbbecd4

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((maximumItemCount) <= (org.jfree.data.time.SerialDate.SERIAL_UPPER_BOUND)) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 696 of bug id Chart5
### Patch Diff Hash-SHA-256:

015ac4df1f0221427e136a634f9f260dc704a8291d63adcc7f2b416fa06d3c52

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index & (org.jfree.chart.renderer.xy.StandardXYItemRenderer.DISCONTINUOUS)) != 0) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 697 of bug id Chart5
### Patch Diff Hash-SHA-256:

59a24f91374be4121bc85b64dd7de8295c0bc19e601a66f0b0d81f5abe9e5180

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -202,7 +202,7 @@
 			}
 			existing.setY(y);
 		}else {
-			if (org.jfree.data.xy.XYSeries.this.autoSort) {
+			if ((index < 0) || (index >= (getItemCount()))) {
 				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 698 of bug id Chart5
### Patch Diff Hash-SHA-256:

0f33ae6c852363cccff33613281fa419f421bde6cc2c04306a26aa58f4d5ce67

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -184,7 +184,7 @@
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(double x, double y) {
-		return addOrUpdate(new java.lang.Double(x), new java.lang.Double(y));
+		return addOrUpdate(new java.lang.Double(y), new java.lang.Double(y));
 	}
 
 	public org.jfree.data.xy.XYDataItem addOrUpdate(java.lang.Number x, java.lang.Number y) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 699 of bug id Chart5
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 700 of bug id Chart5
### Patch Diff Hash-SHA-256:

d07de466b2825eb94c1a1c43cfcba66edc29e874a0565feac0a16e922adb8819

### Patch Diff:
```
--- /original/org/jfree/data/xy/XYSeries.java	
+++ /fixed/org/jfree/data/xy/XYSeries.java	
@@ -203,7 +203,7 @@
 			existing.setY(y);
 		}else {
 			if (org.jfree.data.xy.XYSeries.this.autoSort) {
-				org.jfree.data.xy.XYSeries.this.data.add(((-index) - 1), new org.jfree.data.xy.XYDataItem(x, y));
+				org.jfree.data.xy.XYSeries.this.data.add(data.size(), new org.jfree.data.xy.XYDataItem(x, y));
 			}else {
 				org.jfree.data.xy.XYSeries.this.data.add(new org.jfree.data.xy.XYDataItem(x, y));
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---