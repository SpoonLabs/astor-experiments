
# Patches of Closure40 from Defects4J 
Total patches 4
## Patch 1 of bug id Closure40
### Patch Diff Hash-SHA-256:

71608d5cd506c6458c04c2c6fbc47fc97689092fc1f9f69072f39a8d19cc84c9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, ((nameNode != null) && (n != null)));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Closure40
### Patch Diff Hash-SHA-256:

590041abbb16999ccebb5c5cdf89446cee3d44e692f8c3bb302e963164fc26a9

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, ((n.getFirstChild().getFirstChild()) != null));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Closure40
### Patch Diff Hash-SHA-256:

95f606b94904cde443a89a523e4c97141a2c63b351ad388a8bdceb7d5a8d9ea7

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, (!(n.isDec())));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Closure40
### Patch Diff Hash-SHA-256:

e97e932381aa63097d68168ed4d29ba01463bbc2549c1b23b443ce1fbe14d886

### Patch Diff:
```
--- /original/com/google/javascript/jscomp/NameAnalyzer.java	
+++ /fixed/com/google/javascript/jscomp/NameAnalyzer.java	
@@ -356,7 +356,7 @@
 					com.google.javascript.rhino.Node nameNode = n.getFirstChild();
 					com.google.javascript.jscomp.NameAnalyzer.NameInformation ns = createNameInformation(t, nameNode, n);
 					if ((ns != null) && (ns.onlyAffectsClassDef)) {
-						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, false);
+						com.google.javascript.jscomp.NameAnalyzer.JsName name = getName(ns.name, ((n.getFirstChild().getNext()) != null));
 						if (name != null) {
 							refNodes.add(new com.google.javascript.jscomp.NameAnalyzer.ClassDefiningFunctionNode(name, n, parent, parent.getParent()));
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---