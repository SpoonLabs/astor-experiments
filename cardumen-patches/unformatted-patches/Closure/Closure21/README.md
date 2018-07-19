
# Patches of Closure21 from Defects4J 
Total patches 135
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