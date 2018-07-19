
# Patches of Closure10 from Defects4J 
Total patches 4
## Patch 1 of bug id Closure10
### Patch Diff Hash-SHA-256:

657dc8da11ef9f30ae6b2bf3b33700b3ab9c66268ca6797de2b30e600b3c1286

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -960,7 +960,7 @@
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
-		if (recurse) {
+		if (JSC_PROPERTY_NAME_FN.equals("unknown")) {
 			return com.google.javascript.jscomp.NodeUtil.allResultsMatch(n, com.google.javascript.jscomp.NodeUtil.MAY_BE_STRING_PREDICATE);
 		}else {
 			return com.google.javascript.jscomp.NodeUtil.mayBeStringHelper(n);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure10
### Patch Diff Hash-SHA-256:

ba70e9102dfc29f87a03f2fa2bc2e5c3db16d7682b704a0c5a9de03dc1c832d0

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -956,7 +956,7 @@
 	static final com.google.javascript.jscomp.NodeUtil.MayBeStringResultPredicate MAY_BE_STRING_PREDICATE = new com.google.javascript.jscomp.NodeUtil.MayBeStringResultPredicate();
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n) {
-		return com.google.javascript.jscomp.NodeUtil.mayBeString(n, true);
+		return com.google.javascript.jscomp.NodeUtil.mayBeString(n, ((n.hasChildren()) && (n.getFirstChild().isCatch())));
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure10
### Patch Diff Hash-SHA-256:

9711f6665c33963b07bde7f4e40a1adac3521d996cd3ad941e97b9139fbdf2ea

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -960,7 +960,7 @@
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
-		if (recurse) {
+		if ((n.isDo()) && ((n.getLastChild()) == n)) {
 			return com.google.javascript.jscomp.NodeUtil.allResultsMatch(n, com.google.javascript.jscomp.NodeUtil.MAY_BE_STRING_PREDICATE);
 		}else {
 			return com.google.javascript.jscomp.NodeUtil.mayBeStringHelper(n);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure10
### Patch Diff Hash-SHA-256:

5e6aa5fa527f0d89de8aa020dd96f80313025cc24a394fdb367cf8bf11276dee

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NodeUtil.java	
+++ /fixed/com/google/javascript/jscomp/NodeUtil.java	
@@ -960,7 +960,7 @@
 	}
 
 	static boolean mayBeString(com.google.javascript.rhino.Node n, boolean recurse) {
-		if (recurse) {
+		if (CONSTRUCTORS_WITHOUT_SIDE_EFFECTS.add(JSC_PROPERTY_NAME_FN.trim())) {
 			return com.google.javascript.jscomp.NodeUtil.allResultsMatch(n, com.google.javascript.jscomp.NodeUtil.MAY_BE_STRING_PREDICATE);
 		}else {
 			return com.google.javascript.jscomp.NodeUtil.mayBeStringHelper(n);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---