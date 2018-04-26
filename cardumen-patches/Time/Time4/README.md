
# Patches of Time4 from Defects4J 
Total patches 7
## Patch 1 of bug id Time4
### Patch Diff Hash-SHA-256:

44af7f629737761f0c7a5fb00984946fccf7717ff498a41a10ce47fa16a8e172

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return -1;
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Time4
### Patch Diff Hash-SHA-256:

5e6183f8b1b74ed58a48978416abab380733ae4b7de4313012ebf4fee4a87f97

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return (getMinimumValue(instant, values)) + 1;
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Time4
### Patch Diff Hash-SHA-256:

3057246c793ee2b3aebd0a497f58ff6b45eb6757ed5cd32dd2810e6d08b493cf

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return instant.size();
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Time4
### Patch Diff Hash-SHA-256:

0af836cf2f409b449c0a4e20c1d525484fc69bc69e1972e20be1a8e2e4f36500

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return (getMinimumValue()) + 1;
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Time4
### Patch Diff Hash-SHA-256:

cb0d3b11799ce47cee9c2b58cc2e7d240ce770833dbc2c9bdfece596e75e07b9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return (instant.size()) + 1;
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Time4
### Patch Diff Hash-SHA-256:

39d14886e62a201127daeea4c0ab4f0c652390cb323081d444b55a7e4235a020

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue();
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Time4
### Patch Diff Hash-SHA-256:

3aa83f82f2c6e1bc51fc1936a358fef5301b9790b82c57323600e3cdb75f55fc

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue(instant, values);
 	}
 
 	public long roundFloor(long instant) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---