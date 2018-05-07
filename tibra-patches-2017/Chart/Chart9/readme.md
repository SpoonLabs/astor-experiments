
# Patches of Chart9 from Defects4J 
Total patches 1
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