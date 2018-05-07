
# Patches of Closure22 from Defects4J 
Total patches 4
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