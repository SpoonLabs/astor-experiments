
# Patches of Math101 from Defects4J 
Total patches 1
## Patch 1 of bug id Math101
### Patch Diff Hash-SHA-256:

c5f4125c33a9c04ac6c55f2b090aa68bb2f3acbe70f51b2e0198f13bc5ccc1d6

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/ComplexFormat.java	
+++ /fixed/org/apache/commons/math/complex/ComplexFormat.java	
@@ -167,7 +167,7 @@
 		}
 		int n = getImaginaryCharacter().length();
 		startIndex = pos.getIndex();
-		int endIndex = startIndex + n;
+		int endIndex = source.length();
 		if ((source.substring(startIndex, endIndex).compareTo(getImaginaryCharacter())) != 0) {
 			pos.setIndex(initialIndex);
 			pos.setErrorIndex(startIndex);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---