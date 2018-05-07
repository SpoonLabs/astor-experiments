
# Patches of Time4 from Defects4J 
Total patches 14
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


---
## Patch 2 of bug id Time4
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


---
## Patch 3 of bug id Time4
### Patch Diff Hash-SHA-256:

3afc4c551ca48ae568373aba5c4d7e81f3c801adb02492ae83d09804a8e759cc

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -68,7 +68,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 4 of bug id Time4
### Patch Diff Hash-SHA-256:

c034e250e18944d0b6ff2af620b6dcfd3024302f975c7a17a9f218a53288b0cd

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getMaximumValue(instant);
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 5 of bug id Time4
### Patch Diff Hash-SHA-256:

1cc1190c0cef991831efaee3323146660d25c8c0182b4d58ef420e496bfa6622

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return getName().hashCode();
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 6 of bug id Time4
### Patch Diff Hash-SHA-256:

8118454a071b78e3f2b1da736e08cbbe7879e3c5cf533ca7091ed0321d509fc6

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -68,7 +68,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return getMaximumValue();
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 7 of bug id Time4
### Patch Diff Hash-SHA-256:

1f5effa5f09d78256465bb9f22243d08f3509daaa56d838d587bc7a8147b0aff

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 2;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 8 of bug id Time4
### Patch Diff Hash-SHA-256:

0263232ac42aa4c7642f7c424581fd02b440285400e80a7d7736f608d4a8e46c

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 9 of bug id Time4
### Patch Diff Hash-SHA-256:

86e1a24b4a2cd3860fc6e29047441ca4698f7d4d6c5534acc1eff2254648c3c9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return getMinimumValue(instant);
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 10 of bug id Time4
### Patch Diff Hash-SHA-256:

d07d5698c4833dd44f926199225c756d9e82e5a8d9ba531d3da47ce98aaa0be9

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -68,7 +68,7 @@
 	}
 
 	public int getMinimumValue() {
-		return 1;
+		return (getWrappedField().getMaximumValue()) + 1;
 	}
 
 	public int getMinimumValue(long instant) {
```


---
## Patch 11 of bug id Time4
### Patch Diff Hash-SHA-256:

7673cd2cebb4752874b8c3602dff03cb05c08c22d05d17988d0e35c7dbda42e4

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
 	}
 
 	public int getMinimumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return 1;
+		return (getWrappedField().getMaximumValue(instant, values)) + 1;
 	}
 
 	public int getMaximumValue() {
```


---
## Patch 12 of bug id Time4
### Patch Diff Hash-SHA-256:

a8319a39022c41e33c5007ecefeeb781075b4c620b252412fb3adaca304b9bba

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 0;
 	}
 
 	public long roundFloor(long instant) {
```


---
## Patch 13 of bug id Time4
### Patch Diff Hash-SHA-256:

ac1c6f0c7f0cc1052fdbfc61a45da060fe53cf126b20404cf5c3a8fdf9867c8e

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -80,7 +80,7 @@
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

ea84ecde253b80587f1e2d239ce7dfce96398fef1ad0cef5cd15f4b42920ab1a

### Patch Diff:
```
--- /original/org/joda/time/field/ZeroIsMaxDateTimeField.java	
+++ /fixed/org/joda/time/field/ZeroIsMaxDateTimeField.java	
@@ -96,7 +96,7 @@
 	}
 
 	public int getMaximumValue(org.joda.time.ReadablePartial instant, int[] values) {
-		return (getWrappedField().getMaximumValue(instant, values)) + 1;
+		return 1;
 	}
 
 	public long roundFloor(long instant) {
```


---