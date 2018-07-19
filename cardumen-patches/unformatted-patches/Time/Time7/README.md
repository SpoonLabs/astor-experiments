
# Patches of Time7 from Defects4J 
Total patches 1
## Patch 1 of bug id Time7
### Patch Diff Hash-SHA-256:

602b6cf185f56d4e2acd610c0cb033022de244f42fb8913d894e8a3f1d4985c1

### Patch Diff:
```
--- /original/org/joda/time/format/DateTimeFormatter.java	
+++ /fixed/org/joda/time/format/DateTimeFormatter.java	
@@ -247,7 +247,7 @@
 		org.joda.time.Chronology chrono = instant.getChronology();
 		long instantLocal = instantMillis + (chrono.getZone().getOffset(instantMillis));
 		chrono = selectChronology(chrono);
-		int defaultYear = chrono.year().get(instantLocal);
+		int defaultYear = chrono.year().get(instantMillis);
 		org.joda.time.format.DateTimeParserBucket bucket = new org.joda.time.format.DateTimeParserBucket(instantLocal, chrono, iLocale, iPivotYear, defaultYear);
 		int newPos = parser.parseInto(bucket, text, position);
 		instant.setMillis(bucket.computeMillis(false, text));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---