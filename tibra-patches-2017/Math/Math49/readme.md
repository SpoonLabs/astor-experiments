
# Patches of Math49 from Defects4J 
Total patches 4
## Patch 1 of bug id Math49
### Patch Diff Hash-SHA-256:

aebefb9394579092b1f95a8507c131b9279f7c046c28f0dfd96c75091d42f7f9

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -278,7 +278,6 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
 		return previous;
 	}
```


---
## Patch 2 of bug id Math49
### Patch Diff Hash-SHA-256:

755c1effb32a0d407df84b2dd04b1ab2fdafef8ed77dd9f99c102b6653d9266d

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -278,7 +278,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		++index;
 		return previous;
 	}
```


---
## Patch 3 of bug id Math49
### Patch Diff Hash-SHA-256:

3af34054432f20208c7fec718ea3a6942d2d3086ae6ca728ae8e3c1b20393f3f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -515,7 +515,7 @@
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
-				entries.remove(index);
+				entries.put(index, value);
 			}
 
 	}
```


---
## Patch 4 of bug id Math49
### Patch Diff Hash-SHA-256:

ac2b647531dd4d03c79b7e8a36f83708b1a6e7e0882c861fb3a1c46edb4ba881

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -278,7 +278,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		index++;
 		return previous;
 	}
```


---