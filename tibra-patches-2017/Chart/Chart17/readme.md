
# Patches of Chart17 from Defects4J 
Total patches 1
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