
# Patches of Chart24 from Defects4J 
Total patches 3
## Patch 1 of bug id Chart24
### Patch Diff Hash-SHA-256:

5c2c36e9e060b116a454bf8c4f25d10b096f0afb1f1717f64d55ef9c277140bb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/GrayPaintScale.java	
+++ /fixed/org/jfree/chart/renderer/GrayPaintScale.java	
@@ -31,7 +31,7 @@
 	public java.awt.Paint getPaint(double value) {
 		double v = java.lang.Math.max(value, org.jfree.chart.renderer.GrayPaintScale.this.lowerBound);
 		v = java.lang.Math.min(v, org.jfree.chart.renderer.GrayPaintScale.this.upperBound);
-		int g = ((int) (((value - (org.jfree.chart.renderer.GrayPaintScale.this.lowerBound)) / ((org.jfree.chart.renderer.GrayPaintScale.this.upperBound) - (org.jfree.chart.renderer.GrayPaintScale.this.lowerBound))) * 255.0));
+		int g = ((int) (((v - (lowerBound)) / ((upperBound) - (lowerBound))) * 255.0));
 		return new java.awt.Color(g, g, g);
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Chart24
### Patch Diff Hash-SHA-256:

3bcbdaf9d02bd1486c51e8feda5777b3b224c044637b08c65c62bad8db96817a

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/GrayPaintScale.java	
+++ /fixed/org/jfree/chart/renderer/GrayPaintScale.java	
@@ -31,7 +31,7 @@
 	public java.awt.Paint getPaint(double value) {
 		double v = java.lang.Math.max(value, org.jfree.chart.renderer.GrayPaintScale.this.lowerBound);
 		v = java.lang.Math.min(v, org.jfree.chart.renderer.GrayPaintScale.this.upperBound);
-		int g = ((int) (((value - (org.jfree.chart.renderer.GrayPaintScale.this.lowerBound)) / ((org.jfree.chart.renderer.GrayPaintScale.this.upperBound) - (org.jfree.chart.renderer.GrayPaintScale.this.lowerBound))) * 255.0));
+		int g = ((int) (((v - (lowerBound)) / (v - (lowerBound))) * 255.0));
 		return new java.awt.Color(g, g, g);
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Chart24
### Patch Diff Hash-SHA-256:

9d65e8d9465bcb76c46bf3941db40a728e2c13ec1d389fe4ca87d8e98e2f63eb

### Patch Diff:
```
--- /original/org/jfree/chart/renderer/GrayPaintScale.java	
+++ /fixed/org/jfree/chart/renderer/GrayPaintScale.java	
@@ -31,7 +31,7 @@
 	public java.awt.Paint getPaint(double value) {
 		double v = java.lang.Math.max(value, org.jfree.chart.renderer.GrayPaintScale.this.lowerBound);
 		v = java.lang.Math.min(v, org.jfree.chart.renderer.GrayPaintScale.this.upperBound);
-		int g = ((int) (((value - (org.jfree.chart.renderer.GrayPaintScale.this.lowerBound)) / ((org.jfree.chart.renderer.GrayPaintScale.this.upperBound) - (org.jfree.chart.renderer.GrayPaintScale.this.lowerBound))) * 255.0));
+		int g = ((int) ((((lowerBound) - v) / ((lowerBound) - v)) * 255.0));
 		return new java.awt.Color(g, g, g);
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---