
# Patches of Closure21 from Defects4J 
Total patches 2
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