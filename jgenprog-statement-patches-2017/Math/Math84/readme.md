
# Patches of Math84 from Defects4J 
Total patches 2
## Patch 1 of bug id Math84
### Patch Diff Hash-SHA-256:

11910d49650c4fafe58680b5770ce5911f336e4f55628d184dc4493e26e3779b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -37,6 +37,7 @@
 			if ((comparator.compare(contracted, best)) < 0) {
 				return ;
 			}
+			break;
 		} 
 	}
```


---
## Patch 2 of bug id Math84
### Patch Diff Hash-SHA-256:

908cd73d5b487afe1ffc2157c6c65a7006519be92610cc81f64b307816be9d5f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -37,6 +37,7 @@
 			if ((comparator.compare(contracted, best)) < 0) {
 				return ;
 			}
+			return ;
 		} 
 	}
```


---