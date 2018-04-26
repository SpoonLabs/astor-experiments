
# Patches of Closure55 from Defects4J 
Total patches 1
## Patch 1 of bug id Closure55
### Patch Diff Hash-SHA-256:

69338ff3255cc6fefdda9a3065d5554e96a8a05eb884536ab8e565742ecde951

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/FunctionRewriter.java	
+++ /fixed/com/google/javascript/jscomp/FunctionRewriter.java	
@@ -93,7 +93,7 @@
 					return false;
 				}
 			}
-			return true;
+			return com.google.javascript.jscomp.NodeUtil.mayHaveSideEffects(node);
 		}
 
 		@java.lang.Override
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---