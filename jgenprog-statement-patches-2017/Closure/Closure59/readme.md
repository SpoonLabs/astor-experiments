
# Patches of Closure59 from Defects4J 
Total patches 1
## Patch 1 of bug id Closure59
### Patch Diff Hash-SHA-256:

c2fc0156d0ab2bff4ef838e43e6c3ae72bd185018316105d38c26e1cd31c1336

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/WarningLevel.java	
+++ /fixed/com/google/javascript/jscomp/WarningLevel.java	
@@ -34,7 +34,6 @@
 	private static void addVerboseWarnings(com.google.javascript.jscomp.CompilerOptions options) {
 		com.google.javascript.jscomp.WarningLevel.addDefaultWarnings(options);
 		options.checkSuspiciousCode = true;
-		options.checkGlobalThisLevel = com.google.javascript.jscomp.CheckLevel.WARNING;
 		options.checkSymbols = true;
 		options.checkMissingReturn = com.google.javascript.jscomp.CheckLevel.WARNING;
 		options.checkTypes = true;
```


---