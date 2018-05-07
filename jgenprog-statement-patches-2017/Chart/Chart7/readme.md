
# Patches of Chart7 from Defects4J 
Total patches 2
## Patch 1 of bug id Chart7
### Patch Diff Hash-SHA-256:

d540be86b958421e69c8bb811e5659cc4382a9976e03abd080fcf55220801c1d

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -257,7 +257,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex;
+		return org.jfree.data.time.TimePeriodValues.this.maxStartIndex;
 	}
 
 	public int getMinEndIndex() {
```


---
## Patch 2 of bug id Chart7
### Patch Diff Hash-SHA-256:

7886030f1bb5dba0f59e2f9b299afeb5d27fae884de7f07b7765463e1a379b0c

### Patch Diff:
```
--- /original/org/jfree/data/time/TimePeriodValues.java	
+++ /fixed/org/jfree/data/time/TimePeriodValues.java	
@@ -257,7 +257,7 @@
 	}
 
 	public int getMaxMiddleIndex() {
-		return org.jfree.data.time.TimePeriodValues.this.maxMiddleIndex;
+		return org.jfree.data.time.TimePeriodValues.this.maxEndIndex;
 	}
 
 	public int getMinEndIndex() {
```


---