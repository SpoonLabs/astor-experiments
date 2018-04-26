
# Patches of Closure12 from Defects4J 
Total patches 2
## Patch 1 of bug id Closure12
### Patch Diff Hash-SHA-256:

0f4cbce9a094f1a77a5f84fed20bb891956361d7565cf262bda10a176b6364af

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/FlowSensitiveInlineVariables.java	
+++ /fixed/com/google/javascript/jscomp/FlowSensitiveInlineVariables.java	
@@ -32,7 +32,7 @@
 				return true;
 			}
 			for (com.google.javascript.rhino.Node c = n.getFirstChild(); c != null; c = c.getNext()) {
-				if ((!(com.google.javascript.jscomp.ControlFlowGraph.isEnteringNewCfgNode(c))) && (apply(c))) {
+				if ((!(n.isName())) && (apply(c))) {
 					return true;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure12
### Patch Diff Hash-SHA-256:

b45b9965487f07e98b86fa10f9617958fc611cc1ed86f6ca44ab16e79bfc747d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/FlowSensitiveInlineVariables.java	
+++ /fixed/com/google/javascript/jscomp/FlowSensitiveInlineVariables.java	
@@ -32,7 +32,7 @@
 				return true;
 			}
 			for (com.google.javascript.rhino.Node c = n.getFirstChild(); c != null; c = c.getNext()) {
-				if ((!(com.google.javascript.jscomp.ControlFlowGraph.isEnteringNewCfgNode(c))) && (apply(c))) {
+				if ((!(n.isString())) && (apply(c))) {
 					return true;
 				}
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---