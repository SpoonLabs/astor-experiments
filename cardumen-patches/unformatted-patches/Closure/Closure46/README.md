
# Patches of Closure46 from Defects4J 
Total patches 25
## Patch 1 of bug id Closure46
### Patch Diff Hash-SHA-256:

eeebac3db30fddc314864ef0fde5efd8bb8079ac89749a45526ab0aaa64ba00d

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(that instanceof com.google.javascript.rhino.jstype.ArrowType)) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure46
### Patch Diff Hash-SHA-256:

6e1a2ab0daaefcbd5d22201487fe528a34e158c4eaedde80d42fa77af09ea5e6

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure46
### Patch Diff Hash-SHA-256:

114fdc4b22ced87073099be7b6226b4dc8b40a74abfb1bc575062e09bc4f4ebe

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(isNativeObjectType())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure46
### Patch Diff Hash-SHA-256:

ab2167db146ec864fa8c7b0d17ec5a31d5ec6751daff9b011c5578ac66071720

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Closure46
### Patch Diff Hash-SHA-256:

2a8069097c7385c58f62cad27e0e5caa4658529a50053bc1e188042943b169c4

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Closure46
### Patch Diff Hash-SHA-256:

d3e3b2fb83c98f104bf7e95e945f55f1770e98c4b241457b664a4ac17827d5b7

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(isResolved())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Closure46
### Patch Diff Hash-SHA-256:

edb6225bb700662bbe661f5712840dc4c90bf827e1054f82130b4426a50a27f0

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.NOT_A_TYPE.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Closure46
### Patch Diff Hash-SHA-256:

af78d0a07ae551c660d40eab4adb7f22143d04e9947881405391b84f84f7f039

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME.isEmpty())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Closure46
### Patch Diff Hash-SHA-256:

f869ab1ed5c602fd3ab8a50f5c8b45279b18c42cb7c4432f91b33761cb4dc7f0

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Closure46
### Patch Diff Hash-SHA-256:

b7746060b8bc86d8967264990ad5f5ceb6626b185a1ea467781b78f045bbfd3e

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasOwnProperty(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Closure46
### Patch Diff Hash-SHA-256:

c8192d5700996be4abef03673ba792132ce6a22710b002cefbc2cdd36db9ef4d

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasOwnProperty(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Closure46
### Patch Diff Hash-SHA-256:

68bf65381c9a2e8f604be086ef1b401d79a05ce7fb28f0a3722c514914a429a7

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasOwnProperty(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Closure46
### Patch Diff Hash-SHA-256:

c729c52ebc60503aca76cafb21611108ee4ae6d215bae306924dc79727c1f9cc

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(isNoResolvedType())) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Closure46
### Patch Diff Hash-SHA-256:

25bd7d92cf9306a67329440e33ba592fe9877d1cf5669f487f9b8fd3e67f55d0

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!("String".equals(getReferenceName()))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Closure46
### Patch Diff Hash-SHA-256:

21c92725033c36cf3d1165d11da8c3710b198c93c6aae95256fc0aa85b2d158b

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Closure46
### Patch Diff Hash-SHA-256:

6021e6934e089e691a5f65d4a74c09703f1178a193bf157be36de0f3e2fa58f1

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.UNKNOWN_NAME))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Closure46
### Patch Diff Hash-SHA-256:

5282bbcc884b6db3576b9d9981dce990cfa1537feaae9ac16b120301975ae21f

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, a);
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Closure46
### Patch Diff Hash-SHA-256:

a1e8bd1d457e0eb9b147994118d9aa98137e59f2aa29d9251a1da1a4251d203f

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.NOT_A_CLASS))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Closure46
### Patch Diff Hash-SHA-256:

1f108affac50c974f8f92c6f19b0ab45cbf76406b47ffb199c881bd901a08d78

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(hasProperty(com.google.javascript.rhino.jstype.JSType.NOT_A_TYPE))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Closure46
### Patch Diff Hash-SHA-256:

c34dc9135f79869334c205d3a51235962b6a75aba6ea66be8ea208053150e1bf

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.NOT_A_TYPE))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Closure46
### Patch Diff Hash-SHA-256:

9415a2ef0f896fadbaea18a2b3eaab2dce81485162c47911dd51c80d3c553101

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -63,7 +63,7 @@
 
 	@java.lang.Override
 	public com.google.javascript.rhino.jstype.JSType getLeastSupertype(com.google.javascript.rhino.jstype.JSType that) {
-		if (!(that.isRecordType())) {
+		if (!(properties.containsKey(com.google.javascript.rhino.jstype.JSType.EMPTY_TYPE_COMPONENT))) {
 			return super.getLeastSupertype(that);
 		}
 		com.google.javascript.rhino.jstype.RecordTypeBuilder builder = new com.google.javascript.rhino.jstype.RecordTypeBuilder(registry);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Closure46
### Patch Diff Hash-SHA-256:

7a6eb0dac2a5f9791dc18180241b80e65d8fb91c977079dbd3a9b4b7451486a7

### Patch Diff:
```
--- /original/com/google/javascript/rhino/jstype/RecordType.java	
+++ /fixed/com/google/javascript/rhino/jstype/RecordType.java	
@@ -72,7 +72,7 @@
 				builder.addProperty(property, getPropertyType(property), getPropertyNode(property));
 			}
 		}
-		return builder.build();
+		return super.getLeastSupertype(that);
 	}
 
 	com.google.javascript.rhino.jstype.JSType getGreatestSubtypeHelper(com.google.javascript.rhino.jstype.JSType that) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Closure46
### Patch Diff Hash-SHA-256:

a5e48e63c793b581c92f7a0712668ad8a92852c7b0e88164a17f4acf67766296

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(a.isSubtype(a));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Closure46
### Patch Diff Hash-SHA-256:

69c288394a18c689a697e4b563d62cd51833d348a6d06ff047e3a20a9e685b75

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(a.isEquivalentTo(a));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Closure46
### Patch Diff Hash-SHA-256:

982d7bb1e41c660906317f769797f9d8c6126f6477609c970d2242cbdd6e9f8a

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,7 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
+		junit.framework.Assert.assertTrue(b.isEquivalentTo(b));
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---