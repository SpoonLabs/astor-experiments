
# Patches of Lang24 from Defects4J 
Total patches 1
## Patch 1 of bug id Lang24
### Patch Diff Hash-SHA-256:

4342b72b40844289f299b639fd2d39e42ea8f170625a980adb61ac8e818af8ed

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -714,6 +714,9 @@
 			if ((!allowSigns) && (((((chars[i]) == 'd') || ((chars[i]) == 'D')) || ((chars[i]) == 'f')) || ((chars[i]) == 'F'))) {
 				return foundDigit;
 			}
+			if (hasDecPoint || hasExp) {
+				return false;
+			}
 			if (((chars[i]) == 'l') || ((chars[i]) == 'L')) {
 				return foundDigit && (!hasExp);
 			}
```


---