
## Patch 1 of bug id Closure46
### Patch Diff Hash-SHA-256:

d5a83327ed697ae524d41c176052343afc48825faf8a641f41959b7834bc76f8

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,6 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```


---
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
## Patch 1 of bug id Closure21
### Patch Diff Hash-SHA-256:

bcd9bd29a59fd7ae10db70141be8997935d074b6daa82b41a033e6695e538d03

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -61,11 +61,6 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
-						return ;
-					else
-						break;
-					
 				}
 			}
 		}else
```


---
## Patch 2 of bug id Closure21
### Patch Diff Hash-SHA-256:

521bf61e64f025019cbf4e478bb9cf29101ae44b3c4a54d60d3d2d9600191d91

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,17 +56,6 @@
 				return ;
 			}
 			if (n == (parent.getLastChild())) {
-				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
-					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
-						continue;
-					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
-						return ;
-					else
-						break;
-					
-				}
 			}
 		}else
 			if (((parent.getType()) != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((parent.getType()) != (com.google.javascript.rhino.Token.BLOCK))) {
```


---
## Patch 1 of bug id Closure22
### Patch Diff Hash-SHA-256:

b43840801c2df5f6eb3951aacb3980fad1b5b493fe64fe126b43bc223d603046

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -51,17 +51,6 @@
 				}
 			}
 			if (n == (parent.getLastChild())) {
-				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
-					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
-						continue;
-					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
-						return ;
-					else
-						break;
-					
-				}
 			}
 		}else
 			if (((parent.getType()) != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((parent.getType()) != (com.google.javascript.rhino.Token.BLOCK))) {
```


---
## Patch 2 of bug id Closure22
### Patch Diff Hash-SHA-256:

25dd17032ebf307ba20526bfef1ce5403c624c1277b87c52fd6cb02fbad0632a

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,9 +56,8 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
-						return ;
-					else
+					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK))) {
+					}else
 						break;
 					
 				}
```


---
## Patch 3 of bug id Closure22
### Patch Diff Hash-SHA-256:

28c0cc0424ac6aaa82c8ba601222ec7bed88a29ddec416d2ab7432858fcd43aa

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -50,19 +50,6 @@
 					return ;
 				}
 			}
-			if (n == (parent.getLastChild())) {
-				for (com.google.javascript.rhino.Node an : parent.getAncestors()) {
-					int ancestorType = an.getType();
-					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
-						continue;
-					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
-						return ;
-					else
-						break;
-					
-				}
-			}
 		}else
 			if (((parent.getType()) != (com.google.javascript.rhino.Token.EXPR_RESULT)) && ((parent.getType()) != (com.google.javascript.rhino.Token.BLOCK))) {
 				if ((((parent.getType()) == (com.google.javascript.rhino.Token.FOR)) && ((parent.getChildCount()) == 4)) && ((n == (parent.getFirstChild())) || (n == (parent.getFirstChild().getNext().getNext())))) {
```


---
## Patch 4 of bug id Closure22
### Patch Diff Hash-SHA-256:

68c8ce7ee5cdd3641573f79d7dd4bc33c71c9b2845d0c337de11c1fd46089d56

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/CheckSideEffects.java	
+++ /fixed/com/google/javascript/jscomp/CheckSideEffects.java	
@@ -56,11 +56,6 @@
 					if (ancestorType == (com.google.javascript.rhino.Token.COMMA))
 						continue;
 					
-					if ((ancestorType != (com.google.javascript.rhino.Token.EXPR_RESULT)) && (ancestorType != (com.google.javascript.rhino.Token.BLOCK)))
-						return ;
-					else
-						break;
-					
 				}
 			}
 		}else
```


---