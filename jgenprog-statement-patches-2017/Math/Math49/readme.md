
# Patches of Math49 from Defects4J 
Total patches 8
## Patch 1 of bug id Math49
### Patch Diff Hash-SHA-256:

ef67153ab8a5618e4fb8f920af151ac6f3899b88f924f81a7a3a09145172ca53

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -223,7 +223,6 @@
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

9c6cb84af8a7e0ae8a0a894856c8fce54573851a9499ccc0fb606d573a288687

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -470,7 +470,7 @@
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
-				entries.remove(index);
+				entries.put(index, value);
 			}
 		
 	}
```


---
## Patch 3 of bug id Math49
### Patch Diff Hash-SHA-256:

c7ca96e91f0b9036105508f4e9327cd67c30f8f013bb55d4da2116f9bca46519

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -196,6 +196,7 @@
 	public double remove(final int key) {
 		final int hash = org.apache.commons.math.util.OpenIntToDoubleHashMap.hashOf(key);
 		int index = hash & (mask);
+		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		if (containsKey(key, index)) {
 			return doRemove(index);
 		}
```


---
## Patch 4 of bug id Math49
### Patch Diff Hash-SHA-256:

d95b6c56c9fb66876fdc6548ecba63d4782e62b37ece10215962edde9324b18c

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -220,6 +220,7 @@
 	private double doRemove(int index) {
 		keys[index] = 0;
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
+		int count = 1;
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
```


---
## Patch 5 of bug id Math49
### Patch Diff Hash-SHA-256:

18a7df84cd9c925a5af217108d6bf5167425e275a1fbfcbe89a8bf05e0320d1f

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -220,6 +220,7 @@
 	private double doRemove(int index) {
 		keys[index] = 0;
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
+		int count = 0;
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
```


---
## Patch 6 of bug id Math49
### Patch Diff Hash-SHA-256:

aeffbecaa2ed75f8b92b473752a4fa3ef1134cf066ac4c732c53e6abb3b675ed

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -222,6 +222,7 @@
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		final double previous = values[index];
 		values[index] = missingEntries;
+		int count = 0;
 		--(size);
 		++(count);
 		return previous;
```


---
## Patch 7 of bug id Math49
### Patch Diff Hash-SHA-256:

8faee62433f22224c415e7b84ffbec70c305f0d00eba3ce81354741040c7f866

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -222,6 +222,7 @@
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		final double previous = values[index];
 		values[index] = missingEntries;
+		int count = 1;
 		--(size);
 		++(count);
 		return previous;
```


---
## Patch 8 of bug id Math49
### Patch Diff Hash-SHA-256:

06cc04624ac7ff97e8bc22cacd9b206739f27364f69ac97642c87205f4ca5e9c

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -221,6 +221,7 @@
 		keys[index] = 0;
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		final double previous = values[index];
+		int count = 0;
 		values[index] = missingEntries;
 		--(size);
 		++(count);
```


---