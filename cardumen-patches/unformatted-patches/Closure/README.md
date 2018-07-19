
## Patch 1 of bug id Closure10
### Patch Diff Hash-SHA-256:

657dc8da11ef9f30ae6b2bf3b33700b3ab9c66268ca6797de2b30e600b3c1286

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -960,7 +960,7 @@
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
-		if (recurse) {
+		if (JSC_PROPERTY_NAME_FN.equals("unknown")) {
 			return com.google.javascript.jscomp.NodeUtil.allResultsMatch(n, com.google.javascript.jscomp.NodeUtil.MAY_BE_STRING_PREDICATE);
 		}else {
 			return com.google.javascript.jscomp.NodeUtil.mayBeStringHelper(n);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure10
### Patch Diff Hash-SHA-256:

ba70e9102dfc29f87a03f2fa2bc2e5c3db16d7682b704a0c5a9de03dc1c832d0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -956,7 +956,7 @@
 	static final com.google.javascript.jscomp.NodeUtil.MayBeStringResultPredicate MAY_BE_STRING_PREDICATE = new com.google.javascript.jscomp.NodeUtil.MayBeStringResultPredicate();
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n) {
-		return com.google.javascript.jscomp.NodeUtil.mayBeString(n, true);
+		return com.google.javascript.jscomp.NodeUtil.mayBeString(n, ((n.hasChildren()) && (n.getFirstChild().isCatch())));
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure10
### Patch Diff Hash-SHA-256:

9711f6665c33963b07bde7f4e40a1adac3521d996cd3ad941e97b9139fbdf2ea

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -960,7 +960,7 @@
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
-		if (recurse) {
+		if ((n.isDo()) && ((n.getLastChild()) == n)) {
 			return com.google.javascript.jscomp.NodeUtil.allResultsMatch(n, com.google.javascript.jscomp.NodeUtil.MAY_BE_STRING_PREDICATE);
 		}else {
 			return com.google.javascript.jscomp.NodeUtil.mayBeStringHelper(n);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure10
### Patch Diff Hash-SHA-256:

5e6aa5fa527f0d89de8aa020dd96f80313025cc24a394fdb367cf8bf11276dee

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -960,7 +960,7 @@
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
-		if (recurse) {
+		if (CONSTRUCTORS_WITHOUT_SIDE_EFFECTS.add(JSC_PROPERTY_NAME_FN.trim())) {
 			return com.google.javascript.jscomp.NodeUtil.allResultsMatch(n, com.google.javascript.jscomp.NodeUtil.MAY_BE_STRING_PREDICATE);
 		}else {
 			return com.google.javascript.jscomp.NodeUtil.mayBeStringHelper(n);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
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
## Patch 1 of bug id Closure21
### Patch Diff Hash-SHA-256:

87a844db4b5db65dda196b5415dfd46a3b7ba8f41af072cbfabb5c26aec1bb99

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((((((((com.google.javascript.jscomp.NodeUtil.isAssignmentOp(n)) && ((n.getFirstChild()) == n)) || ((com.google.javascript.jscomp.NodeUtil.isForIn(n)) && ((n.getFirstChild()) == n))) || (n.isVar())) || ((n.isFunction()) && ((n.getFirstChild()) == n))) || (n.isDec())) || (n.isInc())) || (n.isParamList()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure21
### Patch Diff Hash-SHA-256:

774475bb8899640106f594ed4e8d2feb43c2a5a06994e29cb4effbc9e4c2d7c8

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((PROTECTOR_FN.charAt(2)) == 'r') && ((PROTECTOR_FN.charAt(1)) == 'a')) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure21
### Patch Diff Hash-SHA-256:

89ba6a610f5e9715d123b35eb2a20564a8e55bec66f64423b204122437c80479

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((compiler) == null)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure21
### Patch Diff Hash-SHA-256:

6ec6d002cde31a2ac537512d00bd2a54c49e11946db1deae5c2fa2033fde070d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (parent.isCase()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Closure21
### Patch Diff Hash-SHA-256:

f5b48e20685565ef4c66f05caed6351a0c4a776ba946dae2a5f6c3c7c24bc6fe

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((((!isSimpleOp) && (n.isGetProp())) && (parent.isAssign())) && ("prototype".equals(n.getLastChild().getString()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Closure21
### Patch Diff Hash-SHA-256:

5aafc456527f5b31fed0496d817b0b1aaa3cebea1e44afcaf784ef69db18913c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((((parent.isIf()) || (parent.isWhile())) || (parent.isWith())) || (parent.isSwitch())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Closure21
### Patch Diff Hash-SHA-256:

ba9437f664d316f1ffd427bd934e9beaf161d91f14d28ef036056831439b7ff0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (parent.isGetterDef())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Closure21
### Patch Diff Hash-SHA-256:

50aa6e9ce93f373dbd5f780e2e4abd862ce8518c2cdc0fdfb409eb50a730aa29

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (isResultUsed && (n != null))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Closure21
### Patch Diff Hash-SHA-256:

b548b8c9bab64ddd64da71a7011d0178ff1e36a170462b04268c966cfae27dd2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((com.google.javascript.jscomp.NodeUtil.isLiteralValue(parent, true)) || (parent.isFunction()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Closure21
### Patch Diff Hash-SHA-256:

bd6e0b173042b76064693aa67d45d167a84e76d40b27925355790bd26004aa6a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (compiler.hasHaltingErrors()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Closure21
### Patch Diff Hash-SHA-256:

382b8f7b9c1e5461f3dcd514bc505ccdc04cf8f26328a5da52d0cf72efd1f802

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (n.isName())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Closure21
### Patch Diff Hash-SHA-256:

fc71c4e49d62099f4c3af67b87e02699c431c7038ddd801d7ed1b047cf39c764

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.NodeUtil.mayHaveSideEffects(n)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Closure21
### Patch Diff Hash-SHA-256:

ef4149a5f7f96be503c951044370d601092ca98761c850c96d24960c73071c1d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n != null) && (n.isName())) && (n.getString().equals(parent.getString())))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Closure21
### Patch Diff Hash-SHA-256:

ce8408dc0d265b2f6895649e5e6b7b78229b4d915bcc63c7e9d9447106e31275

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isAssign()) && (parent == (n.getFirstChild())))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Closure21
### Patch Diff Hash-SHA-256:

2d13a9447035bd36c1a705347e4a58f71ca10a3ebb8570dda4360f752668db6f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType == 32)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Closure21
### Patch Diff Hash-SHA-256:

cd0f6def65769bd3bde5bb0067aeddc7fce510e105d16d19e84a342169c64cdb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (PROTECTOR_FN.equals("false"))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Closure21
### Patch Diff Hash-SHA-256:

4c3af5e39fde7172fd57314653bea27ac1784c02778fba2403fe2fbd4dafd07b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.NodeUtil.isExprCall(n)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Closure21
### Patch Diff Hash-SHA-256:

7eddec9c3eea244576d93fa5aa0f659c60188f8f02bf2e90c6902c0df373f13e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((n != null) && ((n.isCall()) || (n.isNew()))) && (n.hasChildren())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Closure21
### Patch Diff Hash-SHA-256:

a1c0218bb0dad4640531d200e510fb65fea161935d1a860af100d2db7675a70b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((((parent.getChildCount()) == 1) && (parent.getFirstChild().isName())) && (parent.getFirstChild().getString().equals("Infinity")))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Closure21
### Patch Diff Hash-SHA-256:

97edc85405d0393c3f3f87486c872df531f01fa39e8283e123869c6aed704ec0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((parent.isCall()) || (parent.isNew())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Closure21
### Patch Diff Hash-SHA-256:

e89230cc5944342cf311f70124aae5ac496b2f400f0daead051a99f60e6e6be3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((PROTECTOR_FN) != null)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Closure21
### Patch Diff Hash-SHA-256:

5d0604119b67ca9dbe51f2d285b0f0b53b3ddf74746fc2bc3bd971691498d404

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((((n.isCall()) || (n.isNew())) || (n.isFunction())) || (n.isName())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Closure21
### Patch Diff Hash-SHA-256:

7cb052a04d0f29b987c88db9dbce7dbaa29e28384c687dcc3c595f20e4e27219

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (parent.isIf())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Closure21
### Patch Diff Hash-SHA-256:

e75c382e29c97573c35a322e7c4d2aa8a616b4f7fe01de7828b48ae7c34c478b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (com.google.javascript.jscomp.NodeUtil.isNumericResult(parent))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Closure21
### Patch Diff Hash-SHA-256:

8f1db4ef383ef159ad29cfd26491897f1e77df7a842ea7ab1e849e0c07430fb1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN) == null)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Closure21
### Patch Diff Hash-SHA-256:

1223c512ba831a630867a06c2df5f03a45769a0d37830ca4d1ad3f8b499a5098

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n.isIf()) || (n.isWhile())) || (n.isWith()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Closure21
### Patch Diff Hash-SHA-256:

230a1e7632aced8163590682a11b3ed9d8e107ae3ba1b64bec371389d04dac36

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(com.google.javascript.jscomp.NodeUtil.isExprAssign(n)))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Closure21
### Patch Diff Hash-SHA-256:

bf41add9152992cf4d7067990b7da0041899cd9b9b49e9cb7f77a0ac281fdc73

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.isPrototypeProperty(parent))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Closure21
### Patch Diff Hash-SHA-256:

11c8b50d601bf9b53a62f7b09b60e536422f48b38f16e50b178a996bf5b010ba

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (com.google.javascript.jscomp.NodeUtil.isValidSimpleName(PROTECTOR_FN))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Closure21
### Patch Diff Hash-SHA-256:

8edda6ca643f9d8faf5292d7c3a87c696236bc701e7e024475ee0bc1c6626dc4

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((parent.isBlock()) || (parent.isScript())) || (com.google.javascript.jscomp.NodeUtil.isStatement(parent)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Closure21
### Patch Diff Hash-SHA-256:

131bf5ec47a07680bc70ea8be7c403b33632d8ac9025843d0d854da752379de1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((PROTECTOR_FN.equals("call")) || (PROTECTOR_FN.equals("apply"))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Closure21
### Patch Diff Hash-SHA-256:

2ed54972f92ca7d87bd2e70eded9cc62b30545eb795cf59f754fbfff00d38c61

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (((n == null) || (com.google.javascript.jscomp.NodeUtil.isLiteralValue(n, true))) || (n.isFunction()))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Closure21
### Patch Diff Hash-SHA-256:

1c3cb1542d93ab59ae807e42f9bd8badf3dd51472bc6473c72a5e268e13477f5

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(com.google.javascript.jscomp.NodeUtil.mayBeString(parent)))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Closure21
### Patch Diff Hash-SHA-256:

3e4bc8ff44d0b565e41faaf28bb92d31ee8f74d2d642218914a70b277bf0a5af

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((((n.isVar()) || (n.isExprResult())) || (n.isReturn())) || (n.isThrow())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Closure21
### Patch Diff Hash-SHA-256:

c90c3708c7bdb39c0208004a27db90f18e8223e00b072ac08642d56b1428d134

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.ControlFlowAnalysis.isContinueStructure(parent)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Closure21
### Patch Diff Hash-SHA-256:

a37612c22024f998905ba9cae8fc2842e6a7931eac0e8884ffb626d6ca11ec3b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isGetProp()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Closure21
### Patch Diff Hash-SHA-256:

c9b0667f176249f6fb72665ecb91915235d816cadbfebcecd138d4e3aa5e306b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (("goog.inherits".equals(parent.getFirstChild().getQualifiedName())) && (parent.getLastChild().isQualifiedName()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Closure21
### Patch Diff Hash-SHA-256:

b1195a0953538c30523d9badae5f6a05a375a662f920af37b8da8e6ffb95b67d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isSwitch()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Closure21
### Patch Diff Hash-SHA-256:

5dca5746c9440227630f6a85e5a68c2c6f9d7b032434164ac8d7d7b86a06108b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (parent.isOnlyModifiesThisCall()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Closure21
### Patch Diff Hash-SHA-256:

71854b5f5188dfca48c86c1598ee688eb50244bd56c93e8cd5254b2ae176cb0e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isAssign()) || (n.isName()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Closure21
### Patch Diff Hash-SHA-256:

f2f05a57377e3e9151979ed029c71f38ab24b11c7924e21180d574d90ecd2dc6

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((parent != null) && (parent.isFunction())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Closure21
### Patch Diff Hash-SHA-256:

66e02c4789a9c3058da41f8945b763a84c9ba22839e5cdca275214eb7b3d7d1f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((parent.isTypeOf()) && (parent.isString()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Closure21
### Patch Diff Hash-SHA-256:

6016471b7f3d066e071cd5832d955b78d38afa62efba5a5587baabafd1a7a86b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (parent.isNumber()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Closure21
### Patch Diff Hash-SHA-256:

1790d7038dfee6d2714ab59e8957e2eea9fad465698c4f53f6077325e2ea5ea3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n.getJSDocInfo()) != null) && (n.getJSDocInfo().isJavaDispatch()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Closure21
### Patch Diff Hash-SHA-256:

48d47ae7805a45f7c438fbb9d5aedb32e02efd6614571f9a0e9ad0e6c2bbf15d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((parent == (parent.getFirstChild())) && ((parent.getChildCount()) == 2))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Closure21
### Patch Diff Hash-SHA-256:

f1bda55d2bec0ae155d232c3d3e3106d18fcfded94deac202cef5e017b00826e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((parent != null) && (parent == null))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Closure21
### Patch Diff Hash-SHA-256:

624be40790140b70a5224d53cb098745352b639606572eb78a36d6b65eabcc0e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.getFirstChild()) != null) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Closure21
### Patch Diff Hash-SHA-256:

90022f83aad9752c27f0256679f14c10a685c2eca6e1eeaa2fb10fc5123f79e2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((parent.isObjectLit()) || (parent.isQualifiedName())))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Closure21
### Patch Diff Hash-SHA-256:

9d202f60590cc28cbdd69557f92690dc64f5033cfd7ce1368cc4eb94cb7edaf3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ("goog$object$create".equals(PROTECTOR_FN)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Closure21
### Patch Diff Hash-SHA-256:

d14c3905b33b93f1f8c93d28d82f45e74404e59b77a520f86109b72b9870a1c4

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isAssign()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Closure21
### Patch Diff Hash-SHA-256:

a30da5bdd26433d3b331236af43fe12868b33170727af126342dd88ed411de08

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((!(parent.isVar())) || (parent.hasOneChild()))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Closure21
### Patch Diff Hash-SHA-256:

74c6a67646f09a4bb7547506ffab68c94eea278c3d4caec7a2b9ada6fd6af523

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((com.google.javascript.jscomp.NodeUtil.isAssignmentOp(parent)) || (parent.isFunction()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Closure21
### Patch Diff Hash-SHA-256:

95f9138cedbbad418ae27d2cf85ac813c547acb781df760a99336968efafe2a7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.indexOf('.')) > 0)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Closure21
### Patch Diff Hash-SHA-256:

22b821456621523170ef7cdb40e0e9fbb91985dfaf0ed51f0dacec53bd1ce374

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((parent.isString()) || (parent.isString()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Closure21
### Patch Diff Hash-SHA-256:

343d7d136f16077ea94cc40ed4c211bd93d252c3f9ec3723857371fdcdaffd9f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isGetProp()) && (n.getFirstChild().isThis()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Closure21
### Patch Diff Hash-SHA-256:

82979b2175e4766f3478c09d1fe7235e296c4be7eb8108e5bd275f59a3833ceb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(com.google.javascript.jscomp.NodeUtil.isStatementBlock(n)))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Closure21
### Patch Diff Hash-SHA-256:

8e4b484f8d66e85cda90e125cac01f00d8bec10c444ce1449bd13debf58d483f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType < (problemNodes.size()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Closure21
### Patch Diff Hash-SHA-256:

3717413db501ae593c6f801e080120f2d630550aa8667d111a7e64b40f6a6d0c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n != null) && (n.isTrue()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Closure21
### Patch Diff Hash-SHA-256:

7561699b5c9b5324f5bc23db5ec6378ab6f4eb30799027d1f705efe70d275d58

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ("new".equals(PROTECTOR_FN)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Closure21
### Patch Diff Hash-SHA-256:

20faf2b0c2beed056ff1ca73d10b7fbc70ef461a8faf327fe39c93a41775c75f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((((PROTECTOR_FN.length()) > 3) && (((PROTECTOR_FN.charAt(0)) == '-') || ((PROTECTOR_FN.charAt(0)) == '+'))) && ((PROTECTOR_FN.charAt(1)) == '0')) && (((PROTECTOR_FN.charAt(2)) == 'x') || ((PROTECTOR_FN.charAt(2)) == 'X')))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Closure21
### Patch Diff Hash-SHA-256:

12d4a31855865afd4cd49da122e64c6444504303f52bd67f0ab7d67064bb79bf

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isNumber()) && (parent.isNumber())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Closure21
### Patch Diff Hash-SHA-256:

04b0ce0bd8aae8525f15a9d8930309b1499e9a9c31c6456a3c64a134fb1a6d91

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (!(com.google.javascript.jscomp.NodeUtil.evaluatesToLocalValue(parent)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Closure21
### Patch Diff Hash-SHA-256:

ab4e2544c559ca830208b539603ae0583191b3dabf6b96fa434d35fe67d05338

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((parent == null) || (com.google.javascript.jscomp.NodeUtil.isLiteralValue(parent, true))) || (parent.isFunction())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Closure21
### Patch Diff Hash-SHA-256:

fc31455c262180938a54958b6ca9fe151dcf470c98b43f9800f2a813089628c2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.NodeUtil.isObjectLitKey(n, parent)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Closure21
### Patch Diff Hash-SHA-256:

5d18a8aa794359fd69b8c9979b726af7b5ab3001d2acf402c2fe714c1e6fc2bc

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.indexOf(PROTECTOR_FN.charAt(0))) == (-1))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Closure21
### Patch Diff Hash-SHA-256:

2d4bc32471e6a37614bc2a6376e3f862c4af18ac30ec44e2facf1538bd8e732e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.isStatementBlock(n))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Closure21
### Patch Diff Hash-SHA-256:

924db176c5f0fb9a355b7dd03d7deec26a963268eb8c8daf19162144a8e0427d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (' ' <= ancestorType)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Closure21
### Patch Diff Hash-SHA-256:

e2e05fe72938122aea47c8ea970abc779e6f77ab225b832c705096aac14b8f8b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((((((com.google.javascript.jscomp.NodeUtil.isAssignmentOp(n)) && ((n.getFirstChild()) == n)) || ((com.google.javascript.jscomp.NodeUtil.isForIn(n)) && ((n.getFirstChild()) == n))) || (n.isVar())) || ((n.isFunction()) && ((n.getFirstChild()) == n))) || (n.isDec())) || (n.isInc()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Closure21
### Patch Diff Hash-SHA-256:

ced804cd98227da4fd2607c7bf21086b96eba1403a92484424cdc96d95206fd6

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.isUndefined(n))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Closure21
### Patch Diff Hash-SHA-256:

ccdf31169710cee9af56d3e21fc936b05cbc90f48fde1798f0de5cb6a489f215

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (PROTECTOR_FN.regionMatches(false, (ancestorType + 1), PROTECTOR_FN, 0, PROTECTOR_FN.length()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Closure21
### Patch Diff Hash-SHA-256:

f13a5c67418c0fda771fd29c9d49042a9103e5114ba02f2bf776664c429bcf31

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ("default".equalsIgnoreCase(PROTECTOR_FN))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Closure21
### Patch Diff Hash-SHA-256:

88d79f9f2eed3ea9805ab76f0707a21a8c12e1e8dba0a163b7f0d3af459730fb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isBlock()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Closure21
### Patch Diff Hash-SHA-256:

874a9ef0bf6060758f1bcd706d7de17f524aff1ffeec6be06a9136dff05c3ff5

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((parent.isGetProp()) && (parent.isUnscopedQualifiedName())) && (com.google.javascript.jscomp.NodeUtil.isLValue(parent)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Closure21
### Patch Diff Hash-SHA-256:

ff052d3c288a1d34e8088f9ab6b0bc6e9212b7201fdc11f55610ea4383162178

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType == (-1))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Closure21
### Patch Diff Hash-SHA-256:

dbd9e6d6e1b13499a97bd047e8250cb28a2dbe9857ef9eeb0f3957016c362758

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n == null) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Closure21
### Patch Diff Hash-SHA-256:

e2a0d920e37c8c897993bd56e85d22e72f942cc4c0aa175b741bf97eb1dab269

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (isResultUsed = n.hasOneChild())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Closure21
### Patch Diff Hash-SHA-256:

4d8d4526af0029c97ad6c25a28cc0058be2176f219ac61b97395247d02979652

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((n.isName()) && (!(com.google.javascript.jscomp.NodeUtil.isConstantName(n)))) && (parent.isVar())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Closure21
### Patch Diff Hash-SHA-256:

63f29a69fdc547888b2a613bd69d7c9d928a28b94ea363ba75a609e9f06da0ce

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((PROTECTOR_FN.length()) == 0) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Closure21
### Patch Diff Hash-SHA-256:

4be9f2a179537d050adf3f31c79c5bb69c232563675dffac37ef9c4323a50c34

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType < ancestorType)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Closure21
### Patch Diff Hash-SHA-256:

188b84cb77d06d291c3e1324567208b96eb49d5f0bae29d80a9200b20facdc59

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isScript()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Closure21
### Patch Diff Hash-SHA-256:

082c4f5855a83f2d914e28b2c63dc60564bb148d51d732e9bd0b3f026b5cef8e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (n == null)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Closure21
### Patch Diff Hash-SHA-256:

469c71778318e951128ae3fb466768d7bee3e6d34a77a269bba8f869534fa8ee

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isName()) && (PROTECTOR_FN.equals(n.getString()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Closure21
### Patch Diff Hash-SHA-256:

3febcfcbb8347a8ff8e3ed9ada26c7c207a971e1602c970a89ec1fd214f03002

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((PROTECTOR_FN.charAt(0)) == 'd') {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Closure21
### Patch Diff Hash-SHA-256:

079bb869d7e4b2ca5b89c26ca6a7b1876f65b09d84790f4dadafc1978f426662

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.charAt(2)) == 't')
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Closure21
### Patch Diff Hash-SHA-256:

1ec0d3fb15118d08d903bc5f3650484712c5c2578e487fa0bcb019e371218ea5

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.ControlFlowAnalysis.isContinueStructure(n))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Closure21
### Patch Diff Hash-SHA-256:

3997db9c59559f590f0ac4e677559e72526850be1744fda1e51c855a33b05fa3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((level) != (level))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Closure21
### Patch Diff Hash-SHA-256:

278a11b1403ed3f66c17bab1dc1c762995094770ec6c372472601851405be953

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ("provide".equals(PROTECTOR_FN))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Closure21
### Patch Diff Hash-SHA-256:

fad0d43c47b4014776ca5a475db97c338329a3c5e5e8d0293e03103dcb03e29d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (isSimpleOp = isSimpleOp) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Closure21
### Patch Diff Hash-SHA-256:

ad6ef9000c895e0a8406ed96954256298fa034655c5b6f9de9523b1536b95e79

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.charAt(1)) == 'o')
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Closure21
### Patch Diff Hash-SHA-256:

8fa73311c85495a4c4b681869613ae8697fa6eb805787942a7f607cf7f3e3cbc

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (PROTECTOR_FN.isEmpty()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Closure21
### Patch Diff Hash-SHA-256:

67c6ea5d2a3438d6cbf3482c477351be96bfba3fd0407dd5b600c9d8fa2609aa

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((n != null) && (n.isString())) && (",".equals(n.getString()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Closure21
### Patch Diff Hash-SHA-256:

bfd1701afecbde512412f70dfeab5f9bfa6147702c01aa994b443e5420043aeb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Closure21
### Patch Diff Hash-SHA-256:

579c17cda6834665f09f4e3f1bbbbf4d31295f01265531c70a3d92ae17032bef

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isVar()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Closure21
### Patch Diff Hash-SHA-256:

9b74badf9903fae3e4548f37c7072a490bf043e35ab98cdbce45360e6d718205

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (n != null)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Closure21
### Patch Diff Hash-SHA-256:

60ea6b1870fb50d96f7e9dd024da8d780df5295077d413a24c63f119e6f13428

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (!(protectSideEffectFreeCode)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Closure21
### Patch Diff Hash-SHA-256:

1ccd98a9531485bbd29a84e88b33fdfe2bcc130c2fa4c474593d4a4585679449

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (!(problemNodes.isEmpty()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Closure21
### Patch Diff Hash-SHA-256:

725e901f86107f9128a5f08cf7c253ac362d2ad9f7b9aabe133de474dd3d7ca0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((ancestorType == ancestorType) && (ancestorType >= ancestorType))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Closure21
### Patch Diff Hash-SHA-256:

e64af01fcaffde8a7f7f02c4f4d2861197ad2229feea34b296c1628454a7b7c2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (PROTECTOR_FN.equals("gc")) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Closure21
### Patch Diff Hash-SHA-256:

80fb56c4e2c2d61f13ff17899c4d7e21409119b1797d3096d1bd74b72492f92c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (n.hasOneChild())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Closure21
### Patch Diff Hash-SHA-256:

561b45a918ca4dc562ec4659880cfee4dab4bac71f4073708c31728f62b663fc

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isString()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Closure21
### Patch Diff Hash-SHA-256:

b1f0f2f261011b98948dc1a830d3fbb24fec662843e02f995086444edc4d9bb8

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (isSimpleOp = false)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Closure21
### Patch Diff Hash-SHA-256:

ccdeb44967d03f6b97ad37530629bebbeee3eb1ad941ca2e8f2da598527fde36

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (ancestorType != (-1))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Closure21
### Patch Diff Hash-SHA-256:

8672ceb706663b614e8f0ca1c085784b26349b02199040aa1e4d54fc5cb4f999

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isName()) && ("eval".equals(n.getString())))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Closure21
### Patch Diff Hash-SHA-256:

07adc7d2b4696fc58c1a0bdc385e2e5e3a51f1c9becf8befb5cbe34759ffd513

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((n.isVar()) || (com.google.javascript.jscomp.NodeUtil.isFunctionDeclaration(n))))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Closure21
### Patch Diff Hash-SHA-256:

3b0b947adcd09335121071ecb0eb313751194b4e31274d6e2c18f7cc917e2959

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((((n.getChildCount()) == 1) && (n.getFirstChild().isName())) && (n.getFirstChild().getString().equals("Infinity"))))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Closure21
### Patch Diff Hash-SHA-256:

109bb2ccf105634e18411aafbd95bdb52f4d1fa25a6213c00102000fedb207e2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.charAt(1)) == '0')
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Closure21
### Patch Diff Hash-SHA-256:

cea5e105a1140d6baca69f83753687c27c20dde3b053ecfb1dda9454538cd4ac

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (ancestorType > 0)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Closure21
### Patch Diff Hash-SHA-256:

288fa30b9bc7545eafd0ca5f8122d90f45396659d1fbdc5eb186036b057b8a72

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isGetProp()) && (n == (n.getLastChild()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Closure21
### Patch Diff Hash-SHA-256:

a9317ff8b118e4c980b3f8bebfe1daad1a7bf32a26e12be68b940bc3c098e761

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (ancestorType != (com.google.javascript.rhino.Token.BLOCK))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Closure21
### Patch Diff Hash-SHA-256:

d91dd6cd35725cf864ff1dd0e382f657ef10a28241b027d731f52230cfe03245

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((!(n.isFunction())) && (((n == null) || (com.google.javascript.jscomp.NodeUtil.isControlStructure(n))) || (com.google.javascript.jscomp.NodeUtil.isStatementBlock(n)))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Closure21
### Patch Diff Hash-SHA-256:

98c8cac7d907e22bf84682cfe30ea799f76cceba428cdde666ce7071cf986365

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((n.getLastChild()) != n)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Closure21
### Patch Diff Hash-SHA-256:

9db46ba9d663e337dfcf79f3ce0f35e2b6122ead6cfcc04cb9e23d5e297d3729

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((com.google.javascript.jscomp.NodeUtil.isStatementBlock(n)) || (com.google.javascript.jscomp.NodeUtil.isSwitchCase(n))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Closure21
### Patch Diff Hash-SHA-256:

e0aa88742263f641a15f188c211dfae15db82d440042cf7a7f7bf20254b3b382

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n == (n.getFirstChild())) && ((n.getChildCount()) == 2)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Closure21
### Patch Diff Hash-SHA-256:

ba365de370fba7eee65a3b2aa61b4ed50766f804c6a56fcfffac500d08e8642d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n == null) || ((n.getParent()) == null))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Closure21
### Patch Diff Hash-SHA-256:

8eb0d520dbf9299aaa05ec69294e65ab89f70e606f8207720de4210ef45af8bd

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType == 0)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Closure21
### Patch Diff Hash-SHA-256:

3cac685a2c36c1e6ee64459f5edf681d11371b5a3979d393a8d2e28d6b59fe68

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((problemNodes.size()) > 1) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Closure21
### Patch Diff Hash-SHA-256:

3dbe3a749aa4a5ba98ef7feed6449a7e0adcf36dfc2d257e56b89af495e81be1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (((com.google.javascript.rhino.TokenStream.isJSIdentifier(PROTECTOR_FN)) && (!(com.google.javascript.rhino.TokenStream.isKeyword(PROTECTOR_FN)))) && (com.google.javascript.jscomp.NodeUtil.isLatin(PROTECTOR_FN)))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Closure21
### Patch Diff Hash-SHA-256:

f0e1db8eae9db8e2371598318a5a0b9b1dd0eb20468a01967bb045eb0c09102b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((n != null) && (!(n.isScript())))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Closure21
### Patch Diff Hash-SHA-256:

bf53f2382bb357291221611be0bd5686d96743486b5c8e056ab44a0c4c21bff4

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((n.getSourceFileName()) != null)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Closure21
### Patch Diff Hash-SHA-256:

81ac35312ba3e061d5ee066fc78e3e352cbd176588d7bd29e0bc2a226dcced7a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (n != (n.getFirstChild()))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Closure21
### Patch Diff Hash-SHA-256:

5548c0c5a1ea892815302d4387e1e633356fc7712c66ea4377468929bf6045be

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((PROTECTOR_FN.charAt(0)) == '-') || ((PROTECTOR_FN.charAt(0)) == '+')) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Closure21
### Patch Diff Hash-SHA-256:

273f3bd9e8284d303c74bdd6a80a457217e72f37be1258fb9473f0840a8c53ab

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((com.google.javascript.rhino.TokenStream.isJSIdentifier(PROTECTOR_FN)) && (!(com.google.javascript.rhino.TokenStream.isKeyword(PROTECTOR_FN))))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Closure21
### Patch Diff Hash-SHA-256:

9fb701631057f10dbd8de895ee2bb2a892edbcca35a39490cc3792b8f105f46c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n.isAssign()) && ((n.getFirstChild()) == n)) || (n.isVar()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Closure21
### Patch Diff Hash-SHA-256:

bd468d18c7d6e8613c7d79dadc19a724cb594c5ffbafed3a03e7e701775955d5

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n.isName()) || (n.isGetProp())) || (n.isGetElem()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Closure21
### Patch Diff Hash-SHA-256:

0405c698d5eb7c6723f095d6acc89c736b66a14c3a7d56dbef980978958d080e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isFunction()) || (n.hasOneChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Closure21
### Patch Diff Hash-SHA-256:

04401dd661187ff597183f5535087ca54fe6c09fcf2bb7cbeb2511f798cefa6e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (n == (n.getFirstChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Closure21
### Patch Diff Hash-SHA-256:

f85e00ebba93b49aa4ebc9c81f00ff4f5249501b19a614e87fbc47aafb9e8cc9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((PROTECTOR_FN.charAt(0)) == '-') || ((PROTECTOR_FN.charAt(0)) == '+'))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Closure21
### Patch Diff Hash-SHA-256:

2b5b0666cfe06d731fbec0c34ed30f598f5c248c6cea9fdf9125c14cf6e4ff8a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isNull()) || (com.google.javascript.jscomp.NodeUtil.isUndefined(n)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Closure21
### Patch Diff Hash-SHA-256:

cf707388d962ea44089aac318404918ed19949e1274c61c84b0bba6a7eab928e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (((PROTECTOR_FN) != null) && ((PROTECTOR_FN.length()) > 0))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Closure21
### Patch Diff Hash-SHA-256:

53e81094f035a75e33ed7589805c9dbd5537a59dbaa14273024ed03332ae3f6e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isEmpty()) || (n.isComma())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Closure21
### Patch Diff Hash-SHA-256:

8e2a82677010c8f9ae60bb62933fd7a648ddd414a4218256cefb88eabd49fe60

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n != null) && (n.isAssign()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Closure21
### Patch Diff Hash-SHA-256:

f41de707bd92dbcf5d42b08e8cade59a67311d560a78b41079e45fcafda27081

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,7 +61,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isExprResult()) && (n.getFirstChild().isAssign()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Closure21
### Patch Diff Hash-SHA-256:

3fb380067fdb484a221c3033ea9e2497497d85744b2ff2614568396a93fbcd4b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((n.isHook()) && ((n.getFirstChild()) != n)) || (n.isOr())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Closure21
### Patch Diff Hash-SHA-256:

642c8cb1ec0dcf208ac37cd9686d37b05346664a107ee18124da575c8f324ac6

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -55,7 +55,7 @@
 			if (isResultUsed) {
 				return ;
 			}
-			if (n == (parent.getLastChild())) {
+			if (((PROTECTOR_FN.charAt(2)) == 'x') || ((PROTECTOR_FN.charAt(2)) == 'X')) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Closure21
### Patch Diff Hash-SHA-256:

426dbfee69ec319f7ae1d49c67556e9b89fccfdfed3c1179f379a0c0206f4525

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -58,7 +58,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((parent.getLastChild()) != parent)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Closure22
### Patch Diff Hash-SHA-256:

ffae62794e51cd0a608e7e083f2cbac819ad13c30c747f6608a0a51eca1f2b78

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((n.isBlock()) && (!(n.hasChildren()))))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure22
### Patch Diff Hash-SHA-256:

53bffb09b943d6b9cb082c04f1b839df82d4051a1310c0f638d3ccf1e7483abd

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isCatch()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure22
### Patch Diff Hash-SHA-256:

6d61f8013a4fc575f638016292ad76f83c73b74cf39ecf9ce6065183879ed1f1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((PROTECTOR_FN.equals("ECMASCRIPT3")) || (PROTECTOR_FN.equals("ES3"))) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure22
### Patch Diff Hash-SHA-256:

fd5354999d62f927ecc01b8480c27276e48543937a977de43cd588ac0e17b5e7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType == '{'))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Closure22
### Patch Diff Hash-SHA-256:

d5c027d1f3a976a43297684f0348ce8e86d2e6e95ba94de0f9ce56810e0a39ff

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (((problemNodes) == null) || ((problemNodes.size()) <= ancestorType))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Closure22
### Patch Diff Hash-SHA-256:

7086c19fe84b468ec318adf504588a293276e61e99156d72510f4040e4ccb072

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (gramps.isFunction()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Closure22
### Patch Diff Hash-SHA-256:

5aec8fa50fb054bf9ca0c311f56cbe4764a4268b46fa60df5e3ee8603db42c0c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((parent.isVar()) || (com.google.javascript.jscomp.NodeUtil.isFunctionDeclaration(parent))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Closure22
### Patch Diff Hash-SHA-256:

d264b5e59aa6307bae0a22576e4ba55030d098b1106c2ad28a8769343be6b24b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((((((com.google.javascript.jscomp.NodeUtil.isAssignmentOp(n)) && ((n.getFirstChild()) == parent)) || (n.isVar())) || (n.isInc())) || (n.isDec())) || (n.isParamList())) || (n.isCatch())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Closure22
### Patch Diff Hash-SHA-256:

68fafc2b636b2a78dddcd23af2bb6409c82a853df6dbef1c1706e971ae5b02a9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((PROTECTOR_FN.charAt(2)) == 't') && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Closure22
### Patch Diff Hash-SHA-256:

4d2829f1e6cea2e3db4b601fd1f663425f764d09351af4d0d7d15ec652b5500d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((gramps.isName()) && (!(com.google.javascript.jscomp.NodeUtil.isConstantName(gramps)))) && (parent.isVar())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Closure22
### Patch Diff Hash-SHA-256:

2a1634bd54afbe85a494bac8e86d3545382f92680836e3de4a58f1e8c76dc4cf

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (PROTECTOR_FN.contains("%outname%")) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Closure22
### Patch Diff Hash-SHA-256:

e28f11031bc81e81efc3d9e85270b66bf3fe132eee0b3b855aa567390b69a47e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.NodeUtil.isEmptyFunctionExpression(n)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Closure22
### Patch Diff Hash-SHA-256:

8c4da0afd4573bf8726c5fe71d71a8fe208fc3693907cc3d3c00f46136bbb778

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (java.lang.Character.isJavaIdentifierStart(PROTECTOR_FN.charAt(0)))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Closure22
### Patch Diff Hash-SHA-256:

cf7b0af1cd2562992d4208559cef33dc7042cdab682862be5e4dfcff0bae59d8

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((parent.isGetProp()) && (parent.getLastChild().getString().startsWith("on")))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Closure22
### Patch Diff Hash-SHA-256:

aa82163dc2ebeb1fa4b3e85371b431d76d779e8aeca67585427cc01fb362ac7b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.isStatementBlock(gramps))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Closure22
### Patch Diff Hash-SHA-256:

4a549ff88498d7156e13f085fa76a094ae43c1bee846947dbbd461a80511ba84

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((PROTECTOR_FN) != null)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Closure22
### Patch Diff Hash-SHA-256:

1b6c5967de9c9d99d11ceb37646f8e9d5b106968233e0260ae1cb6349b7d038d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(com.google.javascript.jscomp.NodeUtil.isBooleanResult(parent)))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Closure22
### Patch Diff Hash-SHA-256:

b39414b685fe1b0bdd0250e88ff1a2a75c3f6f5e099b37e9bf400b0d5deb84fa

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (ancestorType > 4)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Closure22
### Patch Diff Hash-SHA-256:

95671bfd2f8e01486f4c69bf47800147046c51ea93802265e4cdb28af0b0a1b1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((gramps.isAnd()) || (gramps.isOr()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Closure22
### Patch Diff Hash-SHA-256:

528ea70c38a931be9b6e26f331e137ed8a99f3b802e3c7f138fd5821273a1acc

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((n.isString()) && (com.google.javascript.jscomp.NodeUtil.isExprAssign(n))) && (com.google.javascript.jscomp.NodeUtil.isVarOrSimpleAssignLhs(gramps, n))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Closure22
### Patch Diff Hash-SHA-256:

51ffa5979f5f155607f57a09143a6e0935e96bfc250571ee929fa1c7e49574f9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((problemNodes) != null)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Closure22
### Patch Diff Hash-SHA-256:

832d9eef1145ef17df472c902679aa40879d9291679bacdc27b851d4660e40bb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((!(com.google.javascript.jscomp.NodeUtil.isNumericResult(n))) && (!(com.google.javascript.jscomp.NodeUtil.isBooleanResult(n))))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Closure22
### Patch Diff Hash-SHA-256:

d703bb70288526e41c96103188557cea64ef629dea66d63e8d1d661c401c8268

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((gramps != null) && (gramps.isThis()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Closure22
### Patch Diff Hash-SHA-256:

ab34619ae53dbbe1e67fb9f3299030f2d5ca383c1cb5424243b26ef9222f86f3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType == (-1)) || (ancestorType == (-1)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Closure22
### Patch Diff Hash-SHA-256:

0a3bcf5e791d206aa242e2656d93b51d10bcec593ac3005307e5d76bfb15b96c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((problemNodes.size()) > 0) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Closure22
### Patch Diff Hash-SHA-256:

b81f2744a5d25a313d21b4c7dbf4f9ff75ebacbd71435f1bc0cbd1e5eb7da0cf

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (parent.isVar()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Closure22
### Patch Diff Hash-SHA-256:

acb22a358db30825fac76df03d2b263ab481da7391c327d1b94318e40383ec2e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.NodeUtil.isGetOrSetKey(n.getParent())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Closure22
### Patch Diff Hash-SHA-256:

8a789a4fbf2483d5a98c74f6c963a5e3fb6d726333f8a55d9e17ff10565e31a2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((protectSideEffectFreeCode) && (!(protectSideEffectFreeCode))) && (protectSideEffectFreeCode)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Closure22
### Patch Diff Hash-SHA-256:

31827a965573afe7bc3d69e68eda42ded9e7d4cffb941b3899e47fd72be1902b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((n.getFirstChild()) != gramps)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Closure22
### Patch Diff Hash-SHA-256:

95040178fd9732a563da724255c85abe29c0221d7d3364dc47c17b917cec0794

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (null == (PROTECTOR_FN))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Closure22
### Patch Diff Hash-SHA-256:

e028eef9fd5b8c9211c20b9d9ce156e84602fedb6cff937c4dd319713fdd79cd

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((0 <= ancestorType) && (ancestorType < 0))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Closure22
### Patch Diff Hash-SHA-256:

cb4a73f6b4d73080745b41478560689b098ffad54966d710c0ec09cbc4950095

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.isNullOrUndefined(parent))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Closure22
### Patch Diff Hash-SHA-256:

a0200c9edd29390d398ca5668e786ffeb0e13f33f482da16425d3a41997b9f41

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType == '{')
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Closure22
### Patch Diff Hash-SHA-256:

801c032eaa58353cc51f2a7ef25f3c23d78594d597d9a6e06b3df8faff86cf10

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (PROTECTOR_FN.substring(0, 2).equalsIgnoreCase("0x")) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Closure22
### Patch Diff Hash-SHA-256:

1710ee571e05adf4accaccd0c58b3c23a064ee158c60555e6dad94797e9f486e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((protectSideEffectFreeCode) && (!(protectSideEffectFreeCode))) && (protectSideEffectFreeCode))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Closure22
### Patch Diff Hash-SHA-256:

456413c2b9345000fea2dac1060a08d46c06076a610b99963f17a99490b06c2a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isVar()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Closure22
### Patch Diff Hash-SHA-256:

87ea36542860e84aae8925b1d73b8fd743ad45d02069a0c16d35a6abcefde6b3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isVar()) || (((n.isAssign()) && ((n.getFirstChild()) == gramps)) && (n.getParent().isExprResult()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Closure22
### Patch Diff Hash-SHA-256:

184459bf93b963d0b05e3217438f0588d800400b893171da6c07db5d3aab8993

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((PROTECTOR_FN.indexOf('')) != (-1)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Closure22
### Patch Diff Hash-SHA-256:

3826de19036651dc2f80d0f27188bc705e846b475114116223b8c3d0e6fe6bf4

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((gramps != null) && (gramps.isParamList())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Closure22
### Patch Diff Hash-SHA-256:

80058f153053d513e17cbb3c22bce4282c96076d52eb34cd59cb47e0908ba1e6

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((t.getScopeDepth()) >= 2) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Closure22
### Patch Diff Hash-SHA-256:

974e9e0dd685781f3fa1af42798a7ff621cec8312232ad06eb152f10f98ec13a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((gramps.isCall()) && (gramps.isExprResult())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Closure22
### Patch Diff Hash-SHA-256:

1a618a89505719b328680f5123796f6d17daecec02446904aa69bc051d0bc54d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((gramps.isVar()) && (parent.hasChildren())) && (parent.getFirstChild().isQualifiedName())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Closure22
### Patch Diff Hash-SHA-256:

787fed1e1bbe1c3fae57de40d681436be791a3f4441b85301cf0b54b3619a2a7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(((parent.isGetProp()) || (parent.isGetElem())) || (parent.isName())))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Closure22
### Patch Diff Hash-SHA-256:

71a794dc2b960efa074d75d298ad24882f7c1a7051d2e325f23dfca7650a56d0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.ControlFlowAnalysis.isContinueStructure(n)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Closure22
### Patch Diff Hash-SHA-256:

2f09375806955ec1dd165ca470acb3ee68dddd6b4ff2ee97497f1d760b8b17c7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((parent.isBlock()) && (gramps != null))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Closure22
### Patch Diff Hash-SHA-256:

082351ba3942a5309bc9bb1845268b1186168e61719e37beb62cea4a7c26703a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (((!(n.isFunction())) || ((com.google.javascript.jscomp.NodeUtil.getFunctionName(n)) != null)) || (com.google.javascript.jscomp.NodeUtil.getFunctionParameters(n).hasChildren()))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Closure22
### Patch Diff Hash-SHA-256:

cb9075993bb9fcc1d21653badf97cac70d77e2ccd5c8d284aee2f17215a0bc8a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((gramps.getFirstChild().getNext()) == n) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Closure22
### Patch Diff Hash-SHA-256:

b91e2de8775fc398a9170b7eec5bb0addeb28ac8eb28c6b61b1f0f217c543a5d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((compiler) == null)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Closure22
### Patch Diff Hash-SHA-256:

4ace8ccb38e9afe13549ae396f3987ea6b53aadfd315a6ea05f1db689ec35d66

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (('0' <= ancestorType) && (ancestorType <= '9'))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Closure22
### Patch Diff Hash-SHA-256:

d825adb70d023b9fe4ebbd02927cb76823c854e378d7ad895dc56316ae0303bb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (parent.isLabel()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Closure22
### Patch Diff Hash-SHA-256:

6d0fd93a2ffa27017e29c2a903dd097fe81f395b83365f21c0897f4a49f9cac3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((gramps.getFirstChild().getNext()) == n)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Closure22
### Patch Diff Hash-SHA-256:

d4fbbc1458c70f3c623fa3929621da28eafdb533fc9116903e5e6b80b92e377a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(parent.isAdd()))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Closure22
### Patch Diff Hash-SHA-256:

efdb76f1836a58c90626213f787392c6a87bdcbbf6ee91d1199cdb70f1559494

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(com.google.javascript.jscomp.NodeUtil.mayBeString(gramps.getLastChild())))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Closure22
### Patch Diff Hash-SHA-256:

8e51618c6edafead5b602795a710ab505516afd808c6b9537a346c4d12438bbb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType < (PROTECTOR_FN.length()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Closure22
### Patch Diff Hash-SHA-256:

a6d931c40f80ec02749d5f230765061709a2fdf6ddcdb09e3f7f9fbd3612b1d0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(PROTECTOR_FN.endsWith(".prototype")))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Closure22
### Patch Diff Hash-SHA-256:

819830c29f933ed91ca3b7aac9d6c0b084d432ba4499acf98ef998b951434da2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.isVarDeclaration(gramps))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Closure22
### Patch Diff Hash-SHA-256:

e22a5707581fcc7463365f357017999ade7cfdda2f1e7a7de87e6c4d1b69dda5

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (PROTECTOR_FN.equals("prototype")) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Closure22
### Patch Diff Hash-SHA-256:

a372d9905f5e4a1c6854e9a20fbce427de03a3813cf59e2d726ba93d6fa4e36a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isOptionalArg()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Closure22
### Patch Diff Hash-SHA-256:

d4e8b6711a385cebdbb28b75ae0eb58429adfecfabc2dd492a492de3deb6ff40

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (PROTECTOR_FN.isEmpty())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Closure22
### Patch Diff Hash-SHA-256:

6083ddf3d927e3786b60bb231876e7723d25637d27a34776086acfb6612b2d5f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(parent.isNew()))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Closure22
### Patch Diff Hash-SHA-256:

3ff47495736996d13140bfe15e8ff584a4e4e0b48a489ee9bc69698efa07b631

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((PROTECTOR_FN.length()) > 0)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Closure22
### Patch Diff Hash-SHA-256:

c2cf06aa6cca57f24e26ef705b12da4039c06742ec4088a5c55abb20fe835f0c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((com.google.javascript.jscomp.NodeUtil.isAssignmentOp(gramps)) || (gramps.isFunction()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Closure22
### Patch Diff Hash-SHA-256:

36ea91e473d9e9e2359f6a0747c0f07c11ac47ccb1e9e8f59d5c21aa3f666519

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((gramps.isTry()) && (com.google.javascript.jscomp.NodeUtil.hasFinally(gramps))) && ((gramps.getLastChild()) != gramps))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Closure22
### Patch Diff Hash-SHA-256:

d51c949105def7f54ddc1ba1d7864b5707d18abcf9afb678236bea38940edca2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((problemNodes.size()) == 1) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Closure22
### Patch Diff Hash-SHA-256:

1d9c5804270be754e1b67343c884276c1458000c88e39942c24e232211f43044

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n.getChildCount()) == 3) && (!(n.getFirstChild().getNext().getNext().hasChildren())))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Closure22
### Patch Diff Hash-SHA-256:

91fc6800e4a500547589eedbc4947db5e70cf9d7b5dfd05cc697c14b1b004d30

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.equals("jit")) || (PROTECTOR_FN.equalsIgnoreCase("all")))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Closure22
### Patch Diff Hash-SHA-256:

ba556a2f6f10b4c4b9beccdab32f2596a4777c0a3df846f2cefd940995046d14

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (parent.isEmpty()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Closure22
### Patch Diff Hash-SHA-256:

c9cec83016aa8defed60b1130beaaec6ca40dcb45443619f2cba6e1d24a7145f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((PROTECTOR_FN.charAt(0)) == '-') || ((PROTECTOR_FN.charAt(0)) == '+'))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Closure22
### Patch Diff Hash-SHA-256:

7cf9e7577a85c8e44aafd1e77683230b0db254836d295d6910f529ad249e70a3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (!(problemNodes.isEmpty()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Closure22
### Patch Diff Hash-SHA-256:

5c9d4df236c9f1cb2e008832f8cc4543cff231c3fb2d938361a854bd98699a42

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.NodeUtil.canBeSideEffected(n)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Closure22
### Patch Diff Hash-SHA-256:

37c3088af1ff32b53bd6e0e28adac76dc183caaa50e7f8b7912028bc272da8c7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((!(n.isName())) || (!(n.getString().equals(com.google.javascript.jscomp.LiveVariablesAnalysis.ARGUMENT_ARRAY_ALIAS))))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Closure22
### Patch Diff Hash-SHA-256:

aa13dbc813a8aa39a6c77586da338e0e756dc07f08232beacd96f84ec5aa2f57

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((problemNodes.size()) > 1)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Closure22
### Patch Diff Hash-SHA-256:

d85e891a1827cdf9de719ba7e865f0dbfde4a18aa2d4a7dcb8aaf53e01f7bdb9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.getParent().getParent()) == null) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Closure22
### Patch Diff Hash-SHA-256:

20e7a8ebad8329a77928a620a52ab18ed962d8f884cb238d56b9afd66400979a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (n.isObjectLit())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Closure22
### Patch Diff Hash-SHA-256:

f5f43c49ffb71a11a88ae545fa38feacefb4074eabb2fbb62ae26d6c0b1b5297

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (((ancestorType == ancestorType) && (ancestorType >= ancestorType)) || (ancestorType > ancestorType))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Closure22
### Patch Diff Hash-SHA-256:

685a21954d66e4c334aadc7cfc4d2226784b364d580f6083576893f498ff70ba

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (n.isAssign())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Closure22
### Patch Diff Hash-SHA-256:

0290c108c19507fa692001c8c6181844e992e855cad6e10baad7c64071609ada

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ("prototype".equals(PROTECTOR_FN))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Closure22
### Patch Diff Hash-SHA-256:

6ede7ebf714874ba32dc3f70aec2c07ab6ce8eb66358a4c1add7da194aab0604

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (n.isExprResult())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Closure22
### Patch Diff Hash-SHA-256:

9ace128d7afc50ba5aaa9a8b73c0ae0c1ef02770a9ef83aad346ea3258123f37

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (!(PROTECTOR_FN.equals(PROTECTOR_FN)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Closure22
### Patch Diff Hash-SHA-256:

1fd0a125432843c44c08c1ab603dffeccbf847fdf1ec511fe334b2b9a7adc3ab

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((parent.isFor()) && ((parent.getFirstChild()) == n)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Closure22
### Patch Diff Hash-SHA-256:

89a6985befca8f7e4aa460361eb6af79e866e2e0d997c5e576c498bb8bba8d37

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (parent.isCase())
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Closure22
### Patch Diff Hash-SHA-256:

d2fd0286851c011ab2086be821b43663aecfc26f1c0d1e039b8734f26f9e4cf0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n != null) && (n.isReturn())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Closure22
### Patch Diff Hash-SHA-256:

7ccdb79392c7364f0886b647d0066542feeca8380e0f82aa4743a659cf391227

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.mayBeString(n))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Closure22
### Patch Diff Hash-SHA-256:

e055c995c8ad99c4c52bc537eef750355f51d518f5c8b92ff2110e0ff5b7ee99

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (!(n.isString()))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Closure22
### Patch Diff Hash-SHA-256:

5779417ec6b5ee3b3e77ce4c8e2f1ce0234bfc0c713621f69fab420f959c860c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isAssign()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Closure22
### Patch Diff Hash-SHA-256:

852f24342cc2e967b1608536c9b8597b889205527ba74e5c6404ef21a97c5adb

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((((problemNodes.size()) == 1) && (((n.getNext()) == null) || (n.getNext().isFunction()))) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Closure22
### Patch Diff Hash-SHA-256:

c10d4ef1ebe2afe090d9c5e735cef5b2bca04793efc1a0bf202ec5902f396f41

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (!(protectSideEffectFreeCode))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Closure22
### Patch Diff Hash-SHA-256:

e912baf69b269a2f3afe05aedf7240a135d7114065f1c28982c651aac9e143e4

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.isGetProp()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Closure22
### Patch Diff Hash-SHA-256:

96e074f1c0149ba721bbd13a8c177763224e75f3166526af18a3a6f4667bd603

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((PROTECTOR_FN) == null) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Closure22
### Patch Diff Hash-SHA-256:

06179452848235b34cf897ed20fd19dac651fd8d6e6d7cf26b221fdf401b5b3c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((protectSideEffectFreeCode) && (!(protectSideEffectFreeCode)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Closure22
### Patch Diff Hash-SHA-256:

929b8d7d5edd837c07bfcc9722c9218be855ec0c5026347f59f0d1cbb648b35d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n != n) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Closure22
### Patch Diff Hash-SHA-256:

6996e5c9dbe2a2fc9c99e09c7dcddb79500051a7357f820d88506f93f909dbcd

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n.hasOneChild()) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Closure22
### Patch Diff Hash-SHA-256:

3d8ac9c137503dc46a1969fc0ddb81b227f0e946188b57ec850cda4ec7f364df

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((null == n) || (n.isString())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Closure22
### Patch Diff Hash-SHA-256:

07dd633acdf3400f107438c2c23a221954ef9c367b9711d98e35b06530859f5a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (ancestorType != (com.google.javascript.rhino.Token.TRUE))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Closure22
### Patch Diff Hash-SHA-256:

8391ecf45e1d1855b27665f4c7cd508d2637d4af5480ad1986086b20bc0b42e9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n != null) && (n.equals(null)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Closure22
### Patch Diff Hash-SHA-256:

1aaa7562472db8d17358648b4edcd33fb971da45f394de1c4678125166434d9e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((n == null) || (!(n.isThis())))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Closure22
### Patch Diff Hash-SHA-256:

135b4c29761b7fb9d09b8aab117f58eb19042683fa68b9d3c1f35bdf93ef53a2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType == (com.google.javascript.rhino.Token.BLOCK))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Closure22
### Patch Diff Hash-SHA-256:

ab1dfa21bf9a6d2766a9e87e55662a839ab52eb392a09de84df1c08f025969d3

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (com.google.javascript.jscomp.NodeUtil.isSwitchCase(n))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Closure22
### Patch Diff Hash-SHA-256:

d6bd1dae35d57fb76d1b58055a59f11d2d8262b91bcd3f8f15b8541c978e8ecf

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (((problemNodes) == null) || ((problemNodes.size()) == 0))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Closure22
### Patch Diff Hash-SHA-256:

e66bf5cf50ac3725bb4cba4bc3a88dba9f8164206525beff13b7c3834984d3ef

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (com.google.javascript.jscomp.NodeUtil.isSimpleOperator(n)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Closure22
### Patch Diff Hash-SHA-256:

1c7caf6d6eae96eeb47b8909d397afeebd68c2cd5e5a6231392ad875ac0c37fa

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n != null) && (n.isVar())) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Closure22
### Patch Diff Hash-SHA-256:

b4cf1c99651a5baa6e591a22333d04bb7c1e1de86d5cfa3fb75732f9df080040

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((com.google.javascript.jscomp.NodeUtil.isFunctionDeclaration(n)) || ((n.isFunction()) && (n.getParent().isName()))) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Closure22
### Patch Diff Hash-SHA-256:

01226daf633637e34e934f47b60787646f4c2c2f9960fa42e1c622c966d5d0f7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((!(protectSideEffectFreeCode)) && ((protectSideEffectFreeCode) || (!(com.google.javascript.jscomp.NodeUtil.mayHaveSideEffects(n, t.getCompiler()))))))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Closure22
### Patch Diff Hash-SHA-256:

4095e0245b995298abf66f53d15eafa2d9002d38114d21a67d00678904f65bb5

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((((PROTECTOR_FN.length()) > 3) && (((PROTECTOR_FN.charAt(0)) == '-') || ((PROTECTOR_FN.charAt(0)) == '+'))) && ((PROTECTOR_FN.charAt(1)) == '0')) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Closure22
### Patch Diff Hash-SHA-256:

a4c8ad04b80fb9b6d6880e4b4b7557d6c2924d19df4e35d48c44a0984307fa5f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((com.google.javascript.jscomp.NodeUtil.isFunctionExpression(n)) && (com.google.javascript.jscomp.NodeUtil.isEmptyBlock(n.getLastChild()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Closure22
### Patch Diff Hash-SHA-256:

8a2aa2c3a6d6207c4529f609d0bdd395cd08700a8160b9fbab9f01af242aee17

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if (n != null)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Closure22
### Patch Diff Hash-SHA-256:

74b52ca62d68789dd78cd6466e1927c1c4e37dcd5a020ab9ed52706ae07d2a79

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((((com.google.javascript.jscomp.NodeUtil.isAssignmentOp(n)) && ((n.getFirstChild()) == n)) || ((com.google.javascript.jscomp.NodeUtil.isForIn(n)) && ((n.getFirstChild()) == n))) || (n.isVar())) || ((n.isFunction()) && ((n.getFirstChild()) == n))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Closure22
### Patch Diff Hash-SHA-256:

b7edbbe74fde6f0356086da49bc79787fa32e8f9c49ef6e9742b55e35e681f95

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isString()) && ("toString".equals(n.getString()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Closure22
### Patch Diff Hash-SHA-256:

64afe1d8d658dc7dc947839aa0eef920be5de748ad7ec9c0d8b19400ffcc0eb1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n != null) && (n.isScript()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Closure22
### Patch Diff Hash-SHA-256:

6a98b7c337aaed9189bc504ef032bb0f6a5b43452bf22618420e2255dc3e3544

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isString()) || (n.isRegExp()))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Closure22
### Patch Diff Hash-SHA-256:

72cdb82bc2c0c35619a66f004b7e7ad47343e7a152bab07a4e89e849089b027f

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (ancestorType == 0)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Closure22
### Patch Diff Hash-SHA-256:

8e77562eb206030267999833c2d0ed42306e5eb48544fdc0466ceb6e4c868619

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.charAt(0)) == '+')
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Closure22
### Patch Diff Hash-SHA-256:

5b118c3440ae612db9624e84648591eecf1b71f558b6cbb40c13b39ca52f9018

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Closure22
### Patch Diff Hash-SHA-256:

600ea1b0eb607e9c52ad3e8f746b24562ad45222af0765e23f1c1a2c34c88fc7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isName()) || (n.isThis())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Closure22
### Patch Diff Hash-SHA-256:

b8baa273f6aaa9eb7f57b00d24b1738d91c72585a1809178aac4b856918d067d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((PROTECTOR_FN.charAt(1)) == 'x')
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Closure22
### Patch Diff Hash-SHA-256:

7fcadf3489c928105ad3a7215e7fdebfb941785d7257f181e82c27dbcd44ece5

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((!(com.google.javascript.jscomp.NodeUtil.isNumericResult(n))) && (!(com.google.javascript.jscomp.NodeUtil.isBooleanResult(n)))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Closure22
### Patch Diff Hash-SHA-256:

4b4bf198503c63ace35fa4aedd9d1f772b070467ec76f774e1147934e26669a2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (n == (n.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Closure22
### Patch Diff Hash-SHA-256:

80b548fa90b3182eb31d6c6963f3b941e89708eea5d0121405aaf4b9828b9586

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.getChildCount()) == 3) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Closure22
### Patch Diff Hash-SHA-256:

e9cf24176e5ee33943418adbb833c58d82197430bcd0de3dcc5f15761e77bf4e

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n.isString()) && (com.google.javascript.jscomp.NodeUtil.isExprAssign(n))) && (com.google.javascript.jscomp.NodeUtil.isVarOrSimpleAssignLhs(n, n)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Closure22
### Patch Diff Hash-SHA-256:

19237bd7634486eaa6ad62db8ed65c8dcdd4606b63a9db00d9d618effbd80872

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((ancestorType = PROTECTOR_FN.indexOf('\n', (ancestorType + 1))) >= 0)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Closure22
### Patch Diff Hash-SHA-256:

66f9cf1cafc47dad8ff23eee94da10ffe91619939223a9beb591d81f96b86901

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.getType()) == (com.google.javascript.rhino.Token.COMMA)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Closure22
### Patch Diff Hash-SHA-256:

3efc80fedf16b3070969070ed5643c354dc5eac698d480c91b0c64ac4a39b4a2

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n == (n.getFirstChild())) && ((n.getChildCount()) == 2)) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Closure22
### Patch Diff Hash-SHA-256:

ce25708d4b314d3c972583fa3ed586ab8395f631f47319be93e0ce908dc6686c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((!(n.isEmpty())) && (!(com.google.javascript.jscomp.NodeUtil.isLiteralValue(n, protectSideEffectFreeCode)))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Closure22
### Patch Diff Hash-SHA-256:

fafc460ac6027637ba6f34f70ad74c4badac5274711d898c289929fb369097a1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.getChildCount()) == 2) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Closure22
### Patch Diff Hash-SHA-256:

caf6b8268828f50cb513c3743a949b724977ba34342b32a081d4db0dd273193a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.getJSDocInfo()) != null)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Closure22
### Patch Diff Hash-SHA-256:

56d578b62f8e44eab236c2afd954e94372e80e270d81d06acb5cd0e2a287bcac

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((((((com.google.javascript.jscomp.NodeUtil.isAssignmentOp(n)) && ((n.getFirstChild()) == n)) || ((com.google.javascript.jscomp.NodeUtil.isForIn(n)) && ((n.getFirstChild()) == n))) || (n.isVar())) || ((n.isFunction()) && ((n.getFirstChild()) == n))) || (n.isDec())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Closure22
### Patch Diff Hash-SHA-256:

5d54873d8a0aae308d7e0530ae902aee0026d838a89f5d8d231589e767fbd2e7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((PROTECTOR_FN) == null) || (PROTECTOR_FN.isEmpty())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Closure22
### Patch Diff Hash-SHA-256:

aa8b078af01035a4c1cce311d411bc86a538f51a228089bdf7920f1f2c58f3e1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((((n.isHook()) && ((n.getFirstChild()) != n)) || (n.isOr())) || (n.isAnd())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Closure22
### Patch Diff Hash-SHA-256:

8c4ae5cd434d9c1bec2155f5f8ab5625de58e052f06c38077f738c75cd17b1f1

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isLabel()) && (n == (n.getLastChild()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Closure22
### Patch Diff Hash-SHA-256:

90399f040225f218462ec648a7a730c022c3c6ee1e83db837bec3db328eb58bf

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.getParent()) == null)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Closure22
### Patch Diff Hash-SHA-256:

811174206c149d21e911c7c597718b476b410161ef02dcf72d1de284a1ff8b98

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((n == null) || (com.google.javascript.jscomp.NodeUtil.isControlStructure(n))) || (com.google.javascript.jscomp.NodeUtil.isStatementBlock(n))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Closure22
### Patch Diff Hash-SHA-256:

ae1951cc9eb13ff6bbe95670fff56ff1fd2e1bcc65c50457c42a92e0071d373b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((PROTECTOR_FN.endsWith(".")) || (PROTECTOR_FN.startsWith("."))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Closure22
### Patch Diff Hash-SHA-256:

f1a9046a9ec772e770d1d0f2d01e53be9ae497121059a957e2a9f598d1e7e440

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if (((compiler) != null) && (!(compiler.hasRegExpGlobalReferences()))) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Closure22
### Patch Diff Hash-SHA-256:

131af67019a95277d94e553127cef52a1480ab8035df824494de6b080fa599cf

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -53,7 +53,7 @@
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
+					if ((n.getLastChild()) != n)
 						continue;
 					
 					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Closure22
### Patch Diff Hash-SHA-256:

72be4a9be06ddd059221f82449eebfd030aebd8003c42f0f416c93eac5b84b2d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n.isName()) || (n.isGetProp())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Closure22
### Patch Diff Hash-SHA-256:

fd066be518614719cffd8d30ceace2fac1edc5b4baffeeda1af063934e77636c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((n != null) && (n.isVar())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Closure22
### Patch Diff Hash-SHA-256:

377a4e093d1caf325cdf9349872a4a42c08458e411135af9205093ecbe9bb20b

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (((n.isTry()) && ((n.getChildCount()) == 3)) && (n == (n.getLastChild())))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Closure22
### Patch Diff Hash-SHA-256:

b6586642e25a309c3c2cd4dcbbd0b0380dbd9ebbf659a7ebbe8d2728d1acb30d

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,7 +50,7 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
+			if ((PROTECTOR_FN.length()) == 0) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
 					int ancestorType = an.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Closure22
### Patch Diff Hash-SHA-256:

d3cf29fc4467d2d4cd0ba544ea888b3e44b23cb0f8c9401894cd055b1223e526

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if ((n.isVar()) || (com.google.javascript.jscomp.NodeUtil.isFunctionDeclaration(n)))
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Closure22
### Patch Diff Hash-SHA-256:

f7b3d5eb283e47814e4f576e251624f9dbc8d708473c424b2217576b5c81599c

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -52,7 +52,7 @@
 			}
 			if (n == (parent.getLastChild())) {
 				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
-					int ancestorType = an.getType();
+					int ancestorType = parent.getType();
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Closure22
### Patch Diff Hash-SHA-256:

3d405adbc6ef8444830fa749ee152d13a5e01348b3ca603395b0bd05b9ccb9ee

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,7 +56,7 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
+					if (n == null)
 						return ;
 					else
 						break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Closure33
### Patch Diff Hash-SHA-256:

c90783904b11c7250128a879f27d3817b45ea7ad667ede70b6ccdbb0c5536910

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
+++ /fixed/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
@@ -409,7 +409,7 @@
 		if (constraintObj.isRecordType()) {
 			for (java.lang.String prop : constraintObj.getOwnPropertyNames()) {
 				com.google.javascript.rhino.jstype.JSType propType = constraintObj.getPropertyType(prop);
-				if (!(isPropertyTypeDeclared(prop))) {
+				if (!(isNativeObjectType())) {
 					com.google.javascript.rhino.jstype.JSType typeToInfer = propType;
 					if (!(hasProperty(prop))) {
 						typeToInfer = getNativeType(com.google.javascript.rhino.jstype.JSTypeNative.VOID_TYPE).getLeastSupertype(propType);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure33
### Patch Diff Hash-SHA-256:

b83c3382f3a3d675e81a7e76d809d596383fa07ed5a25292180f9019cae11dac

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
+++ /fixed/com/google/javascript/rhino/jstype/PrototypeObjectType.java	
@@ -411,7 +411,7 @@
 				com.google.javascript.rhino.jstype.JSType propType = constraintObj.getPropertyType(prop);
 				if (!(isPropertyTypeDeclared(prop))) {
 					com.google.javascript.rhino.jstype.JSType typeToInfer = propType;
-					if (!(hasProperty(prop))) {
+					if (!(hasCachedValues())) {
 						typeToInfer = getNativeType(com.google.javascript.rhino.jstype.JSTypeNative.VOID_TYPE).getLeastSupertype(propType);
 					}
 					defineInferredProperty(prop, typeToInfer, null);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
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
## Patch 1 of bug id Closure46
### Patch Diff Hash-SHA-256:

eeebac3db30fddc314864ef0fde5efd8bb8079ac89749a45526ab0aaa64ba00d

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(that instanceof com.google.javascript.rhino.jstype.ArrowType)) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure46
### Patch Diff Hash-SHA-256:

6e1a2ab0daaefcbd5d22201487fe528a34e158c4eaedde80d42fa77af09ea5e6

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure46
### Patch Diff Hash-SHA-256:

114fdc4b22ced87073099be7b6226b4dc8b40a74abfb1bc575062e09bc4f4ebe

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(isNativeObjectType())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure46
### Patch Diff Hash-SHA-256:

ab2167db146ec864fa8c7b0d17ec5a31d5ec6751daff9b011c5578ac66071720

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Closure46
### Patch Diff Hash-SHA-256:

2a8069097c7385c58f62cad27e0e5caa4658529a50053bc1e188042943b169c4

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Closure46
### Patch Diff Hash-SHA-256:

d3e3b2fb83c98f104bf7e95e945f55f1770e98c4b241457b664a4ac17827d5b7

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(isResolved())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Closure46
### Patch Diff Hash-SHA-256:

edb6225bb700662bbe661f5712840dc4c90bf827e1054f82130b4426a50a27f0

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.NOT_A_TYPE.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Closure46
### Patch Diff Hash-SHA-256:

af78d0a07ae551c660d40eab4adb7f22143d04e9947881405391b84f84f7f039

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Closure46
### Patch Diff Hash-SHA-256:

f869ab1ed5c602fd3ab8a50f5c8b45279b18c42cb7c4432f91b33761cb4dc7f0

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Closure46
### Patch Diff Hash-SHA-256:

b7746060b8bc86d8967264990ad5f5ceb6626b185a1ea467781b78f045bbfd3e

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasOwnProperty(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Closure46
### Patch Diff Hash-SHA-256:

c8192d5700996be4abef03673ba792132ce6a22710b002cefbc2cdd36db9ef4d

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasOwnProperty(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Closure46
### Patch Diff Hash-SHA-256:

68bf65381c9a2e8f604be086ef1b401d79a05ce7fb28f0a3722c514914a429a7

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasOwnProperty(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Closure46
### Patch Diff Hash-SHA-256:

c729c52ebc60503aca76cafb21611108ee4ae6d215bae306924dc79727c1f9cc

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(isNoResolvedType())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Closure46
### Patch Diff Hash-SHA-256:

25bd7d92cf9306a67329440e33ba592fe9877d1cf5669f487f9b8fd3e67f55d0

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!("String".equals(getReferenceName()))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Closure46
### Patch Diff Hash-SHA-256:

21c92725033c36cf3d1165d11da8c3710b198c93c6aae95256fc0aa85b2d158b

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Closure46
### Patch Diff Hash-SHA-256:

6021e6934e089e691a5f65d4a74c09703f1178a193bf157be36de0f3e2fa58f1

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Closure46
### Patch Diff Hash-SHA-256:

5282bbcc884b6db3576b9d9981dce990cfa1537feaae9ac16b120301975ae21f

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, a);
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Closure46
### Patch Diff Hash-SHA-256:

a1e8bd1d457e0eb9b147994118d9aa98137e59f2aa29d9251a1da1a4251d203f

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Closure46
### Patch Diff Hash-SHA-256:

1f108affac50c974f8f92c6f19b0ab45cbf76406b47ffb199c881bd901a08d78

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.NOT_A_TYPE))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Closure46
### Patch Diff Hash-SHA-256:

c34dc9135f79869334c205d3a51235962b6a75aba6ea66be8ea208053150e1bf

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.NOT_A_TYPE))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Closure46
### Patch Diff Hash-SHA-256:

9415a2ef0f896fadbaea18a2b3eaab2dce81485162c47911dd51c80d3c553101

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Closure46
### Patch Diff Hash-SHA-256:

7a6eb0dac2a5f9791dc18180241b80e65d8fb91c977079dbd3a9b4b7451486a7

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -72,7 +72,7 @@
 				builder.addProperty(property, getPropertyType(property), getPropertyNode(property));
 			}
 		}
-		return builder.build();
+		return super.getLeastSupertype(that);
 	}
 
 	com.google.javascript.rhino.jstype.JSType getGreatestSubtypeHelper(com.google.javascript.rhino.jstype.JSType that) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Closure46
### Patch Diff Hash-SHA-256:

a5e48e63c793b581c92f7a0712668ad8a92852c7b0e88164a17f4acf67766296

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(a.isSubtype(a));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Closure46
### Patch Diff Hash-SHA-256:

69c288394a18c689a697e4b563d62cd51833d348a6d06ff047e3a20a9e685b75

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(a.isEquivalentTo(a));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Closure46
### Patch Diff Hash-SHA-256:

982d7bb1e41c660906317f769797f9d8c6126f6477609c970d2242cbdd6e9f8a

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(b.isEquivalentTo(b));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 1 of bug id Closure7
### Patch Diff Hash-SHA-256:

638bdcaba8fbaa48127d1fc02728db3dbcb94355cc146b6de4ef888385e4c909

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/type/ChainableReverseAbstractInterpreter.java	
+++ /fixed/com/google/javascript/jscomp/type/ChainableReverseAbstractInterpreter.java	
@@ -452,7 +452,7 @@
 
 		@java.lang.Override
 		public com.google.javascript.rhino.jstype.JSType caseObjectType(com.google.javascript.rhino.jstype.ObjectType type) {
-			if (value.equals("function")) {
+			if (matchesExpectation("function")) {
 				com.google.javascript.rhino.jstype.JSType ctorType = getNativeType(com.google.javascript.rhino.jstype.JSTypeNative.U2U_CONSTRUCTOR_TYPE);
 				return (resultEqualsValue) && (ctorType.isSubtype(type)) ? ctorType : null;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure7
### Patch Diff Hash-SHA-256:

e4930e70055f9bb3e87e97bdb372adfd9a6546a14c23f3855ae40dbaf04b14ed

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -33,7 +33,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(((("Both types must be null, or both must be non-null " + b) + ",") + a), ((b == null) == (a == null)));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
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
## Patch 1 of bug id Closure40
### Patch Diff Hash-SHA-256:

71608d5cd506c6458c04c2c6fbc47fc97689092fc1f9f69072f39a8d19cc84c9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, ((nameNode != null) && (n != null)));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure40
### Patch Diff Hash-SHA-256:

590041abbb16999ccebb5c5cdf89446cee3d44e692f8c3bb302e963164fc26a9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, ((n.getFirstChild().getFirstChild()) != null));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure40
### Patch Diff Hash-SHA-256:

95f606b94904cde443a89a523e4c97141a2c63b351ad388a8bdceb7d5a8d9ea7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, (!(n.isDec())));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure40
### Patch Diff Hash-SHA-256:

e97e932381aa63097d68168ed4d29ba01463bbc2549c1b23b443ce1fbe14d886

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, ((n.getFirstChild().getNext()) != null));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
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