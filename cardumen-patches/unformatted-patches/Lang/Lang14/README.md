
# Patches of Lang14 from Defects4J 
Total patches 8
## Patch 1 of bug id Lang14
### Patch Diff Hash-SHA-256:

cb83b9bf2edc4a3ce43b75508114dc342a1446b005caa920bd92b7fa8f2ab4cc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang14
### Patch Diff Hash-SHA-256:

c38efdf50eec31777b7c62d0e1c8c01d7ee98a336a7fcdd61b3ec3b03ede7c4f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1, false);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang14
### Patch Diff Hash-SHA-256:

b8269e0613f9847c6799fc4796eb21a6daaba1e1ceb25fcdce6223919007ae42

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang14
### Patch Diff Hash-SHA-256:

46ecb6c43c89dc6c603a087aa4a89657e09fa356462a5d0f0dad45607c495651

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -234,7 +234,7 @@
 		if ((cs1 == null) || (cs2 == null)) {
 			return false;
 		}
-		return cs1.equals(cs2);
+		return org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2, false);
 	}
 
 	public static boolean equalsIgnoreCase(java.lang.CharSequence str1, java.lang.CharSequence str2) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang14
### Patch Diff Hash-SHA-256:

08d7361031b930ade7b37e580605e523483e43cd42f65a424586e83039b27a96

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2, false)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang14
### Patch Diff Hash-SHA-256:

b481f99ee9e8701b9cd0d05133c191b37057f23552124b991b0473b5d1fd5bbc

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1, false)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang14
### Patch Diff Hash-SHA-256:

ac523ab94e6c92b068da4ae720d4ad380454e478925582a799987c171f94d1b9

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs2, cs1)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang14
### Patch Diff Hash-SHA-256:

99b5cd82aa0ab6578d83df44832f1895ddb4a009e5ea733a6d325fdbb018cc2f

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -228,7 +228,7 @@
 	}
 
 	public static boolean equals(java.lang.CharSequence cs1, java.lang.CharSequence cs2) {
-		if (cs1 == cs2) {
+		if (org.apache.commons.lang3.StringUtils.endsWith(cs1, cs2)) {
 			return true;
 		}
 		if ((cs1 == null) || (cs2 == null)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---