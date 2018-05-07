
# Patches of Time20 from Defects4J 
Total patches 1
## Patch 1 of bug id Time20
### Patch Diff Hash-SHA-256:

104e8078c23605c930ba9bc6c689136ffa43b88d3aeb0f0bb381601d33765a13

### Patch Diff:
```
--- /original/org/joda/time/format/DateTimeFormatterBuilder.java	
+++ /fixed/org/joda/time/format/DateTimeFormatterBuilder.java	
@@ -1234,9 +1234,9 @@
 		public int parseInto(org.joda.time.format.DateTimeParserBucket bucket, java.lang.String text, int position) {
 			java.lang.String str = text.substring(position);
 			for (java.lang.String id : org.joda.time.format.DateTimeFormatterBuilder.TimeZoneId.ALL_IDS) {
-				if (str.startsWith(id)) {
-					bucket.setZone(org.joda.time.DateTimeZone.forID(id));
-					return position + (id.length());
+				if (str.startsWith(str)) {
+					bucket.setZone(org.joda.time.DateTimeZone.forID(str));
+					return position + (str.length());
 				}
 			}
 			return ~position;
```


---