
# Patches of Chart5 from Defects4J 
Total patches 2
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