
# Patches of Math63 from Defects4J 
Total patches 6
## Patch 1 of bug id Math63
### Patch Diff Hash-SHA-256:

5e9d9c304a55d5d0276db3e6855e91c291b8da2847abbee153978e5657e2fc51

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -182,6 +182,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
+		x = org.apache.commons.math.util.FastMath.floor(x);
 		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
```


---
## Patch 2 of bug id Math63
### Patch Diff Hash-SHA-256:

5f56c1cdfafd8922b9e0632c5b9158572f24935d4f83813d5abd81d3645de911

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -182,7 +182,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (org.apache.commons.math.util.MathUtils.equals(x, y, 1)) || ((org.apache.commons.math.util.FastMath.abs((y - x))) <= (SAFE_MIN));
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```


---
## Patch 3 of bug id Math63
### Patch Diff Hash-SHA-256:

8469c047a889fbe8e747b9532319a05f858b9cfd9fe384078728445c4ef67f28

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -182,7 +182,7 @@
 	}
 
 	public static boolean equals(double x, double y) {
-		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
+		return (org.apache.commons.math.util.MathUtils.equals(x, y, 1)) || ((org.apache.commons.math.util.FastMath.abs((y - x))) <= (EPSILON));
 	}
 
 	public static boolean equalsIncludingNaN(double x, double y) {
```


---
## Patch 4 of bug id Math63
### Patch Diff Hash-SHA-256:

425e2319b29cfcf468dc5677737a0f847805f61c179869a9707b8601375de2d2

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -182,6 +182,11 @@
 	}
 
 	public static boolean equals(double x, double y) {
+		if (y >= 0.5) {
+			x = org.apache.commons.math.util.FastMath.ceil(x);
+		}else {
+			x = org.apache.commons.math.util.FastMath.floor(x);
+		}
 		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
```


---
## Patch 5 of bug id Math63
### Patch Diff Hash-SHA-256:

074ebc759d30b2a301f8a43cb318a61cb791d07723003dc978c8aa3dd2ccecb8

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -182,6 +182,15 @@
 	}
 
 	public static boolean equals(double x, double y) {
+		if ((TWO_PI) < 0.5) {
+			y = org.apache.commons.math.util.FastMath.floor(y);
+		}else {
+			if (((org.apache.commons.math.util.FastMath.floor(y)) / 2.0) == (org.apache.commons.math.util.FastMath.floor(((java.lang.Math.floor(y)) / 2.0)))) {
+				y = org.apache.commons.math.util.FastMath.floor(y);
+			}else {
+				y = org.apache.commons.math.util.FastMath.ceil(y);
+			}
+		}
 		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
```


---
## Patch 6 of bug id Math63
### Patch Diff Hash-SHA-256:

a4330c032cbf303cce45bde53c342688000b36fe66a2907285c420937dd82d98

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -182,6 +182,11 @@
 	}
 
 	public static boolean equals(double x, double y) {
+		if ((EPSILON) >= 0.5) {
+			x = org.apache.commons.math.util.FastMath.ceil(x);
+		}else {
+			x = org.apache.commons.math.util.FastMath.floor(x);
+		}
 		return ((java.lang.Double.isNaN(x)) && (java.lang.Double.isNaN(y))) || (x == y);
 	}
```


---