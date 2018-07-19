
# Patches of Math79 from Defects4J 
Total patches 6
## Patch 1 of bug id Math79
### Patch Diff Hash-SHA-256:

af6ece183b16162d40fd1dd2445a13b1db606b160a6a51fb8e1e630f3f2f5c1d

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -72,7 +72,7 @@
 		org.apache.commons.math.stat.clustering.Cluster<T> minCluster = null;
 		for (final org.apache.commons.math.stat.clustering.Cluster<T> c : clusters) {
 			final double distance = point.distanceFrom(c.getCenter());
-			if (distance < minDistance) {
+			if (minDistance > 10.0) {
 				minDistance = distance;
 				minCluster = c;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math79
### Patch Diff Hash-SHA-256:

32857d4077b7cb18d70b45ccb3c948317d8a8b4b150bcf4d932e7fa30e81464f

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -72,7 +72,7 @@
 		org.apache.commons.math.stat.clustering.Cluster<T> minCluster = null;
 		for (final org.apache.commons.math.stat.clustering.Cluster<T> c : clusters) {
 			final double distance = point.distanceFrom(c.getCenter());
-			if (distance < minDistance) {
+			if ((minDistance > distance) || (java.lang.Double.isNaN(distance))) {
 				minDistance = distance;
 				minCluster = c;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math79
### Patch Diff Hash-SHA-256:

49f40574bf8ac3e86ad32b2545d02254242cc705e5f66470bb79e7f30d9e7a5e

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -72,7 +72,7 @@
 		org.apache.commons.math.stat.clustering.Cluster<T> minCluster = null;
 		for (final org.apache.commons.math.stat.clustering.Cluster<T> c : clusters) {
 			final double distance = point.distanceFrom(c.getCenter());
-			if (distance < minDistance) {
+			if ((java.lang.Double.isNaN(distance)) || ((java.lang.Math.abs((distance - minDistance))) > distance)) {
 				minDistance = distance;
 				minCluster = c;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math79
### Patch Diff Hash-SHA-256:

2c7a5da76529a4b86c368821f97db2e4b8988bbe7dc14f2ed2d994da4cc2280d

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -72,7 +72,7 @@
 		org.apache.commons.math.stat.clustering.Cluster<T> minCluster = null;
 		for (final org.apache.commons.math.stat.clustering.Cluster<T> c : clusters) {
 			final double distance = point.distanceFrom(c.getCenter());
-			if (distance < minDistance) {
+			if ((org.apache.commons.math.util.MathUtils.compareTo(minDistance, 0, distance)) > 0) {
 				minDistance = distance;
 				minCluster = c;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math79
### Patch Diff Hash-SHA-256:

7b2b0e88bd24e0255230cf841af15623ea2da474c290080da63829850624290a

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -72,7 +72,7 @@
 		org.apache.commons.math.stat.clustering.Cluster<T> minCluster = null;
 		for (final org.apache.commons.math.stat.clustering.Cluster<T> c : clusters) {
 			final double distance = point.distanceFrom(c.getCenter());
-			if (distance < minDistance) {
+			if ((java.lang.Double.isNaN(distance)) || (((java.lang.Math.abs((distance - distance))) <= minDistance) && ((java.lang.Math.abs((distance - minDistance))) <= minDistance))) {
 				minDistance = distance;
 				minCluster = c;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math79
### Patch Diff Hash-SHA-256:

5b59fbc27e4fbb96dcfc660cf6ceaf44efdcad5a23bd9c363d2eedeec372723b

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -72,7 +72,7 @@
 		org.apache.commons.math.stat.clustering.Cluster<T> minCluster = null;
 		for (final org.apache.commons.math.stat.clustering.Cluster<T> c : clusters) {
 			final double distance = point.distanceFrom(c.getCenter());
-			if (distance < minDistance) {
+			if ((java.lang.Double.isNaN(distance)) || (((java.lang.Math.abs((distance - minDistance))) <= minDistance) && ((java.lang.Math.abs((distance - distance))) <= minDistance))) {
 				minDistance = distance;
 				minCluster = c;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---