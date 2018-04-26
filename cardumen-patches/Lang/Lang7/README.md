
# Patches of Lang7 from Defects4J 
Total patches 8
## Patch 1 of bug id Lang7
### Patch Diff Hash-SHA-256:

422a1e32952078df7c0a2b326dec0b9a934ab49a9b21cf450b8d42d947aa8b7d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang7
### Patch Diff Hash-SHA-256:

cb310fe9bb973751c887b4a93bdd889d786f90501d8454e433b99ac6348062b2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (org.apache.commons.lang3.StringUtils.isEmpty(str)) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang7
### Patch Diff Hash-SHA-256:

f06f711c0283be221901c9b298616bd8ee534e39e6d473ae0cb03f13b7fa3ba6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (DOUBLE_MINUS_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang7
### Patch Diff Hash-SHA-256:

0bb4420c2faf1dfd297173cde4c3900b5654313ae6b72371fc686c06d1b5318a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (FLOAT_ZERO.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Lang7
### Patch Diff Hash-SHA-256:

41c32a545a90330fe051a75426a75aec86e36a1ace1cd65a1ceb7e70c66a826c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (DOUBLE_ZERO.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Lang7
### Patch Diff Hash-SHA-256:

f3735bfce803616b6eb8bf34d0f690b3e1fbd5b82a1f453092d1cd6cfa175c61

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (FLOAT_MINUS_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Lang7
### Patch Diff Hash-SHA-256:

522fe9b9895f93f46cc6817208d2b163c1b3687c6d0bc9b79a037703d17a2d12

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (DOUBLE_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Lang7
### Patch Diff Hash-SHA-256:

79b6cbdf4a5dd1a8c51f9c9fdedcb643b96c7353c373edc9f135826d6d096402

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (FLOAT_ONE.isInfinite()) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---