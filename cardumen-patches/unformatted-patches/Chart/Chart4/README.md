
# Patches of Chart4 from Defects4J 
Total patches 2
## Patch 1 of bug id Chart4
### Patch Diff Hash-SHA-256:

17e29a4fcb6194e3122ef1c45ecaae7890823ec5ce44d10fe08063e42f3e75f0

### Patch Diff:
```
--- /original/org/jfree/chart/plot/XYPlot.java	
+++ /fixed/org/jfree/chart/plot/XYPlot.java	
@@ -2115,7 +2115,7 @@
 						result = org.jfree.data.Range.combine(result, org.jfree.data.general.DatasetUtilities.findRangeBounds(d));
 					}
 				}
-				java.util.Collection c = r.getAnnotations();
+				java.util.Collection c = java.util.Collections.unmodifiableCollection(annotations);
 				java.util.Iterator i = c.iterator();
 				while (i.hasNext()) {
 					org.jfree.chart.annotations.XYAnnotation a = ((org.jfree.chart.annotations.XYAnnotation) (i.next()));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart4
### Patch Diff Hash-SHA-256:

b5beed8090b0d89e155868b2b8ecbd8a48a82ed1fa2f30c258451cb0b841a055

### Patch Diff:
```
--- /original/org/jfree/chart/plot/XYPlot.java	
+++ /fixed/org/jfree/chart/plot/XYPlot.java	
@@ -2115,7 +2115,7 @@
 						result = org.jfree.data.Range.combine(result, org.jfree.data.general.DatasetUtilities.findRangeBounds(d));
 					}
 				}
-				java.util.Collection c = r.getAnnotations();
+				java.util.Collection c = java.util.Collections.unmodifiableCollection(includedAnnotations);
 				java.util.Iterator i = c.iterator();
 				while (i.hasNext()) {
 					org.jfree.chart.annotations.XYAnnotation a = ((org.jfree.chart.annotations.XYAnnotation) (i.next()));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---