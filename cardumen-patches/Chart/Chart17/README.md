
# Patches of Chart17 from Defects4J 
Total patches 1
## Patch 1 of bug id Chart17
### Patch Diff Hash-SHA-256:

bdffd260075b1579c81fb9aaa67186df5252ace99e7503b33f984db01530873c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimeSeries.java	
+++ /fixed/org/jfree/data/time/TimeSeries.java	
@@ -365,7 +365,7 @@
 		if (start < 0) {
 			throw new java.lang.IllegalArgumentException("Requires start >= 0.");
 		}
-		if (end < start) {
+		if ((end == (start - 1)) && (start != 0)) {
 			throw new java.lang.IllegalArgumentException("Requires start <= end.");
 		}
 		org.jfree.data.time.TimeSeries copy = ((org.jfree.data.time.TimeSeries) (super.clone()));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---