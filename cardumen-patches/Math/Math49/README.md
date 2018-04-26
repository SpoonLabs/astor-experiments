
# Patches of Math49 from Defects4J 
Total patches 9
## Patch 1 of bug id Math49
### Patch Diff Hash-SHA-256:

555d458b576e8b0571ca8ff77b0c0e7f488339627694364083f415a51288b4a7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -466,7 +466,7 @@
 
 	public void setEntry(int index, double value) {
 		checkIndex(index);
-		if (!(isDefaultValue(value))) {
+		if (!(entries.containsKey(virtualSize))) {
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math49
### Patch Diff Hash-SHA-256:

126ea47d5cb432c41602f7adef8853c712ddf2380dae06b39c903ea9f3d2b581

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -466,7 +466,7 @@
 
 	public void setEntry(int index, double value) {
 		checkIndex(index);
-		if (!(isDefaultValue(value))) {
+		if (!(isDefaultValue(DEFAULT_ZERO_TOLERANCE))) {
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math49
### Patch Diff Hash-SHA-256:

77bf1b55902e8b0f344dabe30032059b4a527f3b787da45bcc858e4ba9432410

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -466,7 +466,7 @@
 
 	public void setEntry(int index, double value) {
 		checkIndex(index);
-		if (!(isDefaultValue(value))) {
+		if (!((entries) instanceof org.apache.commons.math.linear.RealVector)) {
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math49
### Patch Diff Hash-SHA-256:

a0b4a7839648ec16f9ace43b38fa71aaeb2fa488ccc8067f39b9c93da09594a0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -466,7 +466,7 @@
 
 	public void setEntry(int index, double value) {
 		checkIndex(index);
-		if (!(isDefaultValue(value))) {
+		if (!(isDefaultValue(epsilon))) {
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math49
### Patch Diff Hash-SHA-256:

dfe9603e05abdd8bce45a412df357b0146ddfd78329a9a65f4fca7662f3b4dc1

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -223,7 +223,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		index--;
 		return previous;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math49
### Patch Diff Hash-SHA-256:

582d7b853b62e3903025236c361f2583898ce7ac5479256e29e2ae5afb3473d2

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -223,7 +223,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		--index;
 		return previous;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math49
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math49
### Patch Diff Hash-SHA-256:

e880b740dace570dc858be1a0dc0e7db686896498a941ec78e357bdf586a13c3

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -223,7 +223,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		++index;
 		return previous;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math49
### Patch Diff Hash-SHA-256:

aad1582350ac98ac6320d10a3e000e8fb924f60b279c379e24110138b36a7fcf

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -223,7 +223,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		index++;
 		return previous;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---