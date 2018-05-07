
# Patches of Closure46 from Defects4J 
Total patches 1
## Patch 1 of bug id Closure46
### Patch Diff Hash-SHA-256:

d5a83327ed697ae524d41c176052343afc48825faf8a641f41959b7834bc76f8

### Patch Diff:
```
--- /original/com/google/javascript/rhino/testing/Asserts.java	
+++ /fixed/com/google/javascript/rhino/testing/Asserts.java	
@@ -34,7 +34,6 @@
 	}
 
 	public static void assertTypeEquals(com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
-		com.google.javascript.rhino.testing.Asserts.assertTypeEquals("", a, b);
 	}
 
 	public static void assertTypeEquals(java.lang.String message, com.google.javascript.rhino.jstype.JSType a, com.google.javascript.rhino.jstype.JSType b) {
```


---