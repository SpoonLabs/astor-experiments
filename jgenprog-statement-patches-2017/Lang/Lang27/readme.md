
# Patches of Lang27 from Defects4J 
Total patches 2
## Patch 1 of bug id Lang27
### Patch Diff Hash-SHA-256:

57b341aa84337757ed5ab6d00f4451ff6e5892d87ef69d74dd4d3d9f13993ba2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str;
 			}else {
 				mant = str;
 			}
```


---
## Patch 2 of bug id Lang27
### Patch Diff Hash-SHA-256:

6a67c43b99a1334d23fa348d469c8c24c2838d563ac7bb0f47922ab7ea39117c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,6 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
+				java.lang.Double d = org.apache.commons.lang3.math.NumberUtils.createDouble(str);
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```


---