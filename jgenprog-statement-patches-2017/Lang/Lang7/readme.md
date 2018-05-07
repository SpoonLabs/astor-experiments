
# Patches of Lang7 from Defects4J 
Total patches 8
## Patch 1 of bug id Lang7
### Patch Diff Hash-SHA-256:

e6362af5c4ff46c90c67cb80a463655ec80131917928bd1f3aa1662189bc575c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -142,7 +142,7 @@
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
 		if (str.startsWith("--")) {
-			return null;
+			return java.lang.Long.parseLong(str);
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
 			int hexDigits = (str.length()) - 2;
```


---
## Patch 2 of bug id Lang7
### Patch Diff Hash-SHA-256:

83e056c783f49265bdf7c68ccd85fc2da918ab79ef2f5eb2b966d37e184b3204

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,8 +141,8 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
-			return null;
+		if (str == null) {
+			throw new java.lang.IllegalArgumentException("The string must not be null");
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
 			int hexDigits = (str.length()) - 2;
```


---
## Patch 3 of bug id Lang7
### Patch Diff Hash-SHA-256:

40816b21450ff34c5e610bdda0648023c0b01e6a56db002797ad0aa1f275dcc5

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,9 +141,6 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
-			return null;
-		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
 			int hexDigits = (str.length()) - 2;
 			if (str.startsWith("-")) {
```


---
## Patch 4 of bug id Lang7
### Patch Diff Hash-SHA-256:

40747169bb1c9f1a12c805bb481cae1c5b214429f8cc59ff8d82d2037b77ef1d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -142,7 +142,7 @@
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
 		if (str.startsWith("--")) {
-			return null;
+			return java.lang.Byte.parseByte(str);
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
 			int hexDigits = (str.length()) - 2;
```


---
## Patch 5 of bug id Lang7
### Patch Diff Hash-SHA-256:

138b69b3f3d0661e6489a3ae6bb4ff64fe16bd68e0ab3d320386f298453acaf0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -142,7 +142,7 @@
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
 		if (str.startsWith("--")) {
-			return null;
+			return org.apache.commons.lang3.math.Fraction.getFraction(java.lang.Integer.parseInt(str), 1);
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
 			int hexDigits = (str.length()) - 2;
```


---
## Patch 6 of bug id Lang7
### Patch Diff Hash-SHA-256:

e6b3070851186e8cd258c7c915275e723c4c3f78559c3b5ad7d1b577f53672e4

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -142,7 +142,6 @@
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
 		if (str.startsWith("--")) {
-			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
 			int hexDigits = (str.length()) - 2;
```


---
## Patch 7 of bug id Lang7
### Patch Diff Hash-SHA-256:

316e6139adcfc21103fd51f2a0dafc85e181dc0204bc7eaf7170a28c7a4da80a

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,8 +141,15 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
-			return null;
+		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
+			int hexDigits = (str.length()) - 2;
+			if (str.startsWith("-")) {
+				hexDigits--;
+			}
+			if (hexDigits > 8) {
+				return org.apache.commons.lang3.math.NumberUtils.createLong(str);
+			}
+			return org.apache.commons.lang3.math.NumberUtils.createInteger(str);
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
 			int hexDigits = (str.length()) - 2;
```


---
## Patch 8 of bug id Lang7
### Patch Diff Hash-SHA-256:

c75d83175cf8220a92dba9182bb8e260939a99d5e36b6cca2a13e5e8b9328627

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -141,7 +141,7 @@
 		if (org.apache.commons.lang3.StringUtils.isBlank(str)) {
 			throw new java.lang.NumberFormatException("A blank string is not a valid number");
 		}
-		if (str.startsWith("--")) {
+		if (str == null) {
 			return null;
 		}
 		if ((((str.startsWith("0x")) || (str.startsWith("-0x"))) || (str.startsWith("0X"))) || (str.startsWith("-0X"))) {
```


---