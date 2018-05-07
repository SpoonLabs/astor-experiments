
# Patches of Chart24 from Defects4J 
Total patches 1
## Patch 1 of bug id Chart24
### Patch Diff Hash-SHA-256:

d35594c95999f0a002f06a1a611881b72279c8d309e99763100f6bc73f157bbd

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/GrayPaintScale.java	
+++ /fixed/org/jfree/chart/renderer/GrayPaintScale.java	
@@ -29,6 +29,7 @@
 	public java.awt.Paint getPaint(double value) {
 		double v = java.lang.Math.max(value, this.lowerBound);
 		v = java.lang.Math.min(v, this.upperBound);
+		value = v;
 		int g = ((int) (((value - (this.lowerBound)) / ((this.upperBound) - (this.lowerBound))) * 255.0));
 		return new java.awt.Color(g, g, g);
 	}
```


---