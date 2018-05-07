
# Patches of Lang10 from Defects4J 
Total patches 1
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