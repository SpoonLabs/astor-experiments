
# Patches of Closure133 from Defects4J 
Total patches 1
## Patch 1 of bug id Closure133
### Patch Diff Hash-SHA-256:

15d9a9a00fed5eaa887bcd8d0d54c24bbf75d35ae618d15abbb82f472d12b0e1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/parsing/JsDocInfoParser.java	
+++ /fixed/com/google/javascript/jscomp/parsing/JsDocInfoParser.java	
@@ -919,7 +919,7 @@
 		java.lang.StringBuilder builder = new java.lang.StringBuilder();
 		builder.append(line);
 		state = com.google.javascript.jscomp.parsing.JsDocInfoParser.State.SEARCHING_ANNOTATION;
-		token = next();
+		token = eatTokensUntilEOL();
 		boolean ignoreStar = false;
 		int lineStartChar = -1;
 		do {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---