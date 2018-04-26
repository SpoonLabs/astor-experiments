
# Patches of Closure45 from Defects4J 
Total patches 10
## Patch 1 of bug id Closure45
### Patch Diff Hash-SHA-256:

9c05d781dfba0b6c1638bab15cd4e986ca39a6e7be5e47ad4a25c0897065c49d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!((modifyCallSites) || (var.getParentNode().isExprResult()))) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure45
### Patch Diff Hash-SHA-256:

2991b660c859b5d4ba3873fdf7e3f0de362ea3bdbbe2eedcaeaa9199d645e996

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!((maybeUnreferenced) instanceof com.google.javascript.jscomp.JsMessage)) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure45
### Patch Diff Hash-SHA-256:

a693e11611990b8a0d9ccd210242d868afc1feaec4f886dfe64b6fc62ba634d4

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!(var.isDefine())) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure45
### Patch Diff Hash-SHA-256:

e809b8e104f276faf3ab7bc19ffb285a2392a3d93f60ffc7ef2922cc69335a24

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!(referenced.contains("this"))) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Closure45
### Patch Diff Hash-SHA-256:

efbf73527f88025cfd906b821ea46e58f0ec871aa08faca035e7dbec395086f1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!((continuations) instanceof com.google.javascript.jscomp.Scope.Arguments)) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Closure45
### Patch Diff Hash-SHA-256:

26d31f89bc5a855df531a52c5a026db4764f8775666a527c8a119a546ade7fae

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!(var.isBleedingFunction())) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Closure45
### Patch Diff Hash-SHA-256:

b2c04b35860567677fee1233dd392afebcc242ef0bd361f24529a79d2cc2321d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!(modifyCallSites)) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Closure45
### Patch Diff Hash-SHA-256:

23a560bb87b1d4ecae2c9c3ba4c79f4fb4012de1996d7bf5a0f3c894e27d6ebb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!assignedToUnknownValue) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Closure45
### Patch Diff Hash-SHA-256:

3c981721062cc915260d233726940583d1ec38c1124d373453a5a2fd1235ceb4

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!(referenced.contains(var))) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Closure45
### Patch Diff Hash-SHA-256:

5d50b54f32aef30b99718d2b683d97a5defe28b9b5e55fafd5d7aeee352ace90

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/RemoveUnusedVars.java	
+++ /fixed/com/google/javascript/jscomp/RemoveUnusedVars.java	
@@ -401,7 +401,7 @@
 						if (assign.isPropertyAssign) {
 							hasPropertyAssign = true;
 						}else
-							if (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(assign.assignNode.getLastChild(), true))) {
+							if (!(var.isExtern())) {
 								assignedToUnknownValue = true;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---