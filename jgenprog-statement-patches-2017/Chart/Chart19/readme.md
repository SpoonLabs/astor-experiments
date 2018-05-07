
# Patches of Chart19 from Defects4J 
Total patches 1
## Patch 1 of bug id Chart19
### Patch Diff Hash-SHA-256:

0347cb9bfcaf3cd2adb8faabf30c9ac6386a9a433558d5741c3f55d33c2b26b6

### Patch Diff:
```
--- /original/org/jfree/chart/util/AbstractObjectList.java	
+++ /fixed/org/jfree/chart/util/AbstractObjectList.java	
@@ -63,6 +63,9 @@
 				return index;
 			}
 		}
+		if (object == null) {
+			throw new java.lang.IllegalArgumentException("Null 'object' argument.");
+		}
 		return -1;
 	}
```


---