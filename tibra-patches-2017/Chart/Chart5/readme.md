
# Patches of Chart5 from Defects4J 
Total patches 13
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