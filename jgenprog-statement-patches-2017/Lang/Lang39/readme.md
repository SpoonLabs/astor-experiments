
# Patches of Lang39 from Defects4J 
Total patches 3
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