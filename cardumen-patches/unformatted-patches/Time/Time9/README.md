
# Patches of Time9 from Defects4J 
Total patches 1
## Patch 1 of bug id Time9
### Patch Diff Hash-SHA-256:

723f42bb18c6dd2e7d51c6abc26b55a0c2cd412cb18853891f86c77c7a43d378

### Patch Diff:
```
--- /original/org/joda/time/DateTimeZone.java	
+++ /fixed/org/joda/time/DateTimeZone.java	
@@ -124,7 +124,7 @@
 
 	public static org.joda.time.DateTimeZone forOffsetMillis(int millisOffset) {
 		java.lang.String id = org.joda.time.DateTimeZone.printOffset(millisOffset);
-		return org.joda.time.DateTimeZone.fixedOffsetZone(id, millisOffset);
+		return org.joda.time.DateTimeZone.forID(id);
 	}
 
 	public static org.joda.time.DateTimeZone forTimeZone(java.util.TimeZone zone) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---