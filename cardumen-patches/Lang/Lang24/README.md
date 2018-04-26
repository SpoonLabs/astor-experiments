
# Patches of Lang24 from Defects4J 
Total patches 2
## Patch 1 of bug id Lang24
### Patch Diff Hash-SHA-256:

8a1b0f0b8536705f69a30260c54f6f3170ac5cc8f01aa05b82d1bd99a39818d4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -715,7 +715,7 @@
 				return foundDigit;
 			}
 			if (((chars[i]) == 'l') || ((chars[i]) == 'L')) {
-				return foundDigit && (!hasExp);
+				return (!hasDecPoint) && (!hasExp);
 			}
 			return false;
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang24
### Patch Diff Hash-SHA-256:

40950540b1d13b6e7f6da1144d2dc2a154ef25df01eaa96e61d1f1cb38e797ca

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -714,7 +714,7 @@
 			if ((!allowSigns) && (((((chars[i]) == 'd') || ((chars[i]) == 'D')) || ((chars[i]) == 'f')) || ((chars[i]) == 'F'))) {
 				return foundDigit;
 			}
-			if (((chars[i]) == 'l') || ((chars[i]) == 'L')) {
+			if (i == 5) {
 				return foundDigit && (!hasExp);
 			}
 			return false;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---