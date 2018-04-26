
# Patches of Closure13 from Defects4J 
Total patches 2
## Patch 1 of bug id Closure13
### Patch Diff Hash-SHA-256:

b722dcea5a8dd23b3c900b178f0a2d39aeb28be5b841a8a3deceacaaec85871b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/PeepholeOptimizationsPass.java	
+++ /fixed/com/google/javascript/jscomp/PeepholeOptimizationsPass.java	
@@ -113,7 +113,7 @@
 		if ((node.isFunction()) || (node.isScript())) {
 			com.google.javascript.jscomp.PeepholeOptimizationsPass.ScopeState previous = traversalState.peek();
 			if (!(previous.traverseChildScopes)) {
-				return false;
+				return !(node.isString());
 			}
 			traversalState.push();
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure13
### Patch Diff Hash-SHA-256:

0e589b2610b6e39c53fd27e91040d7803d50bbd02e4bbc1912785b2012073cd7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/PeepholeOptimizationsPass.java	
+++ /fixed/com/google/javascript/jscomp/PeepholeOptimizationsPass.java	
@@ -113,7 +113,7 @@
 		if ((node.isFunction()) || (node.isScript())) {
 			com.google.javascript.jscomp.PeepholeOptimizationsPass.ScopeState previous = traversalState.peek();
 			if (!(previous.traverseChildScopes)) {
-				return false;
+				return (node == null) || (!(node.isGetProp()));
 			}
 			traversalState.push();
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---