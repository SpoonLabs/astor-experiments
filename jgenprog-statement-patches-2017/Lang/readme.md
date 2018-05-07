
## Patch 1 of bug id Lang27
### Patch Diff Hash-SHA-256:

57b341aa84337757ed5ab6d00f4451ff6e5892d87ef69d74dd4d3d9f13993ba2

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,7 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
-				mant = str.substring(0, expPos);
+				mant = str;
 			}else {
 				mant = str;
 			}
```


---
## Patch 2 of bug id Lang27
### Patch Diff Hash-SHA-256:

6a67c43b99a1334d23fa348d469c8c24c2838d563ac7bb0f47922ab7ea39117c

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -165,6 +165,7 @@
 			mant = str.substring(0, decPos);
 		}else {
 			if (expPos > (-1)) {
+				java.lang.Double d = org.apache.commons.lang3.math.NumberUtils.createDouble(str);
 				mant = str.substring(0, expPos);
 			}else {
 				mant = str;
```


---
## Patch 1 of bug id Lang39
### Patch Diff Hash-SHA-256:

afc5bb6b432b0fe4c05e4425b33e73d8b96d1da0133dbfee1d76a6f430d91026

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,12 +1162,6 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
-			if (greater > 0) {
-				increase += 3 * greater;
-			}
-		}
 		increase = java.lang.Math.min(increase, ((text.length()) / 5));
 		java.lang.StringBuilder buf = new java.lang.StringBuilder(((text.length()) + increase));
 		while (textIndex != (-1)) {
```


---
## Patch 2 of bug id Lang39
### Patch Diff Hash-SHA-256:

ad3cdcd2c8e458c2c0eb74eee8d73a26b421c8762914b0301e3f6f03c91e8913

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,10 +1162,18 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
-			if (greater > 0) {
-				increase += 3 * greater;
+		for (int i = 0; i < searchLength; i++) {
+			if ((((noMoreMatchesForReplIndex[i]) || ((searchList[i]) == null)) || ((searchList[i].length()) == 0)) || ((replacementList[i]) == null)) {
+				continue;
+			}
+			tempIndex = text.indexOf(searchList[i]);
+			if (tempIndex == (-1)) {
+				noMoreMatchesForReplIndex[i] = true;
+			}else {
+				if ((textIndex == (-1)) || (tempIndex < textIndex)) {
+					textIndex = tempIndex;
+					replaceIndex = i;
+				}
 			}
 		}
 		increase = java.lang.Math.min(increase, ((text.length()) / 5));
```


---
## Patch 3 of bug id Lang39
### Patch Diff Hash-SHA-256:

af1f006a2f8921493c850b31ae99750fd2724e22b5d74bea4a1e9d7685b24fc0

### Patch Diff:
```
--- /original/org/apache/commons/lang3/StringUtils.java	
+++ /fixed/org/apache/commons/lang3/StringUtils.java	
@@ -1162,10 +1162,18 @@
 		}
 		int start = 0;
 		int increase = 0;
-		for (int i = 0; i < (searchList.length); i++) {
-			int greater = (replacementList[i].length()) - (searchList[i].length());
-			if (greater > 0) {
-				increase += 3 * greater;
+		for (int i = 0; i < searchLength; i++) {
+			if ((((noMoreMatchesForReplIndex[i]) || ((searchList[i]) == null)) || ((searchList[i].length()) == 0)) || ((replacementList[i]) == null)) {
+				continue;
+			}
+			tempIndex = text.indexOf(searchList[i], start);
+			if (tempIndex == (-1)) {
+				noMoreMatchesForReplIndex[i] = true;
+			}else {
+				if ((textIndex == (-1)) || (tempIndex < textIndex)) {
+					textIndex = tempIndex;
+					replaceIndex = i;
+				}
 			}
 		}
 		increase = java.lang.Math.min(increase, ((text.length()) / 5));
```


---
## Patch 1 of bug id Lang24
### Patch Diff Hash-SHA-256:

4342b72b40844289f299b639fd2d39e42ea8f170625a980adb61ac8e818af8ed

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/NumberUtils.java	
+++ /fixed/org/apache/commons/lang3/math/NumberUtils.java	
@@ -714,6 +714,9 @@
 			if ((!allowSigns) && (((((chars[i]) == 'd') || ((chars[i]) == 'D')) || ((chars[i]) == 'f')) || ((chars[i]) == 'F'))) {
 				return foundDigit;
 			}
+			if (hasDecPoint || hasExp) {
+				return false;
+			}
 			if (((chars[i]) == 'l') || ((chars[i]) == 'L')) {
 				return foundDigit && (!hasExp);
 			}
```


---
## Patch 1 of bug id Lang22
### Patch Diff Hash-SHA-256:

418d7e7c2c6f72a4400dc305c39082452b7638221500cd334afab7d44114b789

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -286,7 +286,6 @@
 
 	private static int greatestCommonDivisor(int u, int v) {
 		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
-			return 1;
 		}
 		if (u > 0) {
 			u = -u;
```


---
## Patch 2 of bug id Lang22
### Patch Diff Hash-SHA-256:

d1bd204035cbe4bd9b68460d8b0404a7ee5da33ae938a60663a8b9280f5b8d08

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,9 +285,6 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
-			return 1;
-		}
 		if (u > 0) {
 			u = -u;
 		}
```


---
## Patch 3 of bug id Lang22
### Patch Diff Hash-SHA-256:

c6c9230bc91812007e16e57ca0f90fdf0f2ce6e061794ce7d0f10d5a4856ad32

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,8 +285,8 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
-			return 1;
+		if (u > 0) {
+			u = -u;
 		}
 		if (u > 0) {
 			u = -u;
```


---
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
## Patch 1 of bug id Lang10
### Patch Diff Hash-SHA-256:

1a8d5f1895f17c349543e738c9d3555884c873068aa15fb46e0145702dad45c1

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -154,13 +154,6 @@
 		boolean wasWhite = false;
 		for (int i = 0; i < (value.length()); ++i) {
 			char c = value.charAt(i);
-			if (java.lang.Character.isWhitespace(c)) {
-				if (!wasWhite) {
-					wasWhite = true;
-					regex.append("\\s*+");
-				}
-				continue;
-			}
 			wasWhite = false;
 			switch (c) {
 				case '\'' :
```


---