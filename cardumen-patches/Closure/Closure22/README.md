
# Patches of Closure22 from Defects4J 
Total patches 141
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