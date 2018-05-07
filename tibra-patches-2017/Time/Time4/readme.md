
# Patches of Time4 from Defects4J 
Total patches 14
## Patch 1 of bug id Time4
### Patch Diff Hash-SHA-256:

3fc3c311ebadd80e7ab01af4429ab28a0a6128477211feeb7797e611de2397b4

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -66,7 +66,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getMaximumValue();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 2 of bug id Time4
### Patch Diff Hash-SHA-256:

21bf35ce993227aa05dea48bdfb1ee7e33ffb898fcbd1f42f6f38c657bc1e7fd

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue(instant, values)) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 3 of bug id Time4
### Patch Diff Hash-SHA-256:

786220cede3c0507e6155256c3e67c36b79124f5fbd8c9595cecc54a8f5b1721

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -66,7 +66,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 4 of bug id Time4
### Patch Diff Hash-SHA-256:

89faa0e777d0c0cedc98d099ba74103b487f3e3aba63fdb39fb17f726cde0313

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -66,7 +66,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 5 of bug id Time4
### Patch Diff Hash-SHA-256:

5715748db567e37b661ffc3f7550e07b15bc7c4dba763d050ffefc2469e5c5e2

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 2;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 6 of bug id Time4
### Patch Diff Hash-SHA-256:

92aad06ea256c352301c481eba072fd58f0ea635f7970ea7e58ad2d5d69919b5

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue();
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 7 of bug id Time4
### Patch Diff Hash-SHA-256:

637620e44e328470d2f96ab3eb9521e5b59019b4f8dc7ce07763315308f4df0d

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 8 of bug id Time4
### Patch Diff Hash-SHA-256:

fb1d15684c0beb8083def465c71b2394c9ddce86b5987628b8e652c0d235b11a

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 3;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 9 of bug id Time4
### Patch Diff Hash-SHA-256:

2c692725f9716e6fdb87822d5b9e11d5d4df2207b1b9b4fedaf6f53b58b305d5

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return -1;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 10 of bug id Time4
### Patch Diff Hash-SHA-256:

b1048b3727500bcb9e49ec2a04eef58b21b9d32c023ceb5fc2763ccd178ac9d3

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 0;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 11 of bug id Time4
### Patch Diff Hash-SHA-256:

fe8ba495982307f425980e138ea7ece582d60b17a14fa8a17885c5a71e10a07e

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getMaximumValue(instant);
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 12 of bug id Time4
### Patch Diff Hash-SHA-256:

27dbb8aed6ef4a3230c02e4361f06b513e78ef2e695181fd1b87b0d0a0b03f71

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -94,7 +94,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 1;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 13 of bug id Time4
### Patch Diff Hash-SHA-256:

70038cdd4dec5984fcbac944bc79c159586c0d8f625528ce3adff1aa5e6c2fd9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getMaximumValue();
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 14 of bug id Time4
### Patch Diff Hash-SHA-256:

bf9228bcbe2ab1d66f6b2b44259507504a4b4d3745405757423cfe36bc7a8c98

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -78,7 +78,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMaximumValue() {
```


---