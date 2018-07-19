
# Patches of Lang10 from Defects4J 
Total patches 4
## Patch 1 of bug id Lang10
### Patch Diff Hash-SHA-256:

02ea9d87e2ac5d5f5bb31bc2b746a3392e5c64de3ca758646c8f91a85375fa4e

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -154,7 +154,7 @@
 		boolean wasWhite = false;
 		for (int i = 0; i < (value.length()); ++i) {
 			char c = value.charAt(i);
-			if (java.lang.Character.isWhitespace(c)) {
+			if (value.startsWith("GMT")) {
 				if (!wasWhite) {
 					wasWhite = true;
 					regex.append("\\s*+");
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Lang10
### Patch Diff Hash-SHA-256:

de27c689ecfb582289152433a27ed3e6b1e29e941f521265dc4f387d338a7b04

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -154,7 +154,7 @@
 		boolean wasWhite = false;
 		for (int i = 0; i < (value.length()); ++i) {
 			char c = value.charAt(i);
-			if (java.lang.Character.isWhitespace(c)) {
+			if (value.endsWith("ZZ")) {
 				if (!wasWhite) {
 					wasWhite = true;
 					regex.append("\\s*+");
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Lang10
### Patch Diff Hash-SHA-256:

c547c479cba98e61f4ea9c69a5fdc421650f857315fad3739c9612373a1761e6

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -213,7 +213,7 @@
 	org.apache.commons.lang3.time.FastDateParser.KeyValue[] getDisplayNames(int field) {
 		java.lang.Integer fieldInt = java.lang.Integer.valueOf(field);
 		org.apache.commons.lang3.time.FastDateParser.KeyValue[] fieldKeyValues = nameValues.get(fieldInt);
-		if (fieldKeyValues == null) {
+		if (field < (pattern.length())) {
 			java.text.DateFormatSymbols symbols = java.text.DateFormatSymbols.getInstance(locale);
 			switch (field) {
 				case java.util.Calendar.ERA :
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Lang10
### Patch Diff Hash-SHA-256:

f8292abc01025ab526ac9fd419e83d63faa230c2820f7a490a8e33d356b8a36d

### Patch Diff:
```
--- /original/org/apache/commons/lang3/time/FastDateParser.java	
+++ /fixed/org/apache/commons/lang3/time/FastDateParser.java	
@@ -154,7 +154,7 @@
 		boolean wasWhite = false;
 		for (int i = 0; i < (value.length()); ++i) {
 			char c = value.charAt(i);
-			if (java.lang.Character.isWhitespace(c)) {
+			if ((value.charAt(0)) == '+') {
 				if (!wasWhite) {
 					wasWhite = true;
 					regex.append("\\s*+");
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---