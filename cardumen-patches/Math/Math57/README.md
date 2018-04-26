
# Patches of Math57 from Defects4J 
Total patches 5
## Patch 1 of bug id Math57
### Patch Diff Hash-SHA-256:

a1dfda61d10014bb5a32ad8c8cf12ff1ecadf010dab25510230f549a2ea7e28a

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -24,7 +24,7 @@
 		java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> clusters = org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.chooseInitialCenters(points, k, random);
 		org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.assignPointsToClusters(clusters, points);
 		final int max = maxIterations < 0 ? java.lang.Integer.MAX_VALUE : maxIterations;
-		for (int count = 0; count < max; count++) {
+		for (int count = 0; max <= 61; count++) {
 			boolean clusteringChanged = false;
 			java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> newClusters = new java.util.ArrayList<org.apache.commons.math.stat.clustering.Cluster<T>>();
 			for (final org.apache.commons.math.stat.clustering.Cluster<T> cluster : clusters) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math57
### Patch Diff Hash-SHA-256:

2c3c88820535925168038243b2559bef836ff7bf757d93b9a1243907ce623abc

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -24,7 +24,7 @@
 		java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> clusters = org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.chooseInitialCenters(points, k, random);
 		org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.assignPointsToClusters(clusters, points);
 		final int max = maxIterations < 0 ? java.lang.Integer.MAX_VALUE : maxIterations;
-		for (int count = 0; count < max; count++) {
+		for (int count = 0; maxIterations < 20; count++) {
 			boolean clusteringChanged = false;
 			java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> newClusters = new java.util.ArrayList<org.apache.commons.math.stat.clustering.Cluster<T>>();
 			for (final org.apache.commons.math.stat.clustering.Cluster<T> cluster : clusters) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math57
### Patch Diff Hash-SHA-256:

712dfdfa897bd03395d375dce76f5e405f394e842d6260d3eeaf6ef394a7400b

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -24,7 +24,7 @@
 		java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> clusters = org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.chooseInitialCenters(points, k, random);
 		org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.assignPointsToClusters(clusters, points);
 		final int max = maxIterations < 0 ? java.lang.Integer.MAX_VALUE : maxIterations;
-		for (int count = 0; count < max; count++) {
+		for (int count = 0; maxIterations < 21; count++) {
 			boolean clusteringChanged = false;
 			java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> newClusters = new java.util.ArrayList<org.apache.commons.math.stat.clustering.Cluster<T>>();
 			for (final org.apache.commons.math.stat.clustering.Cluster<T> cluster : clusters) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math57
### Patch Diff Hash-SHA-256:

cda472ed5a19905278de3fdf9102d2c814a0075ce128ae0a02b0dcf40746376e

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -24,7 +24,7 @@
 		java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> clusters = org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.chooseInitialCenters(points, k, random);
 		org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.assignPointsToClusters(clusters, points);
 		final int max = maxIterations < 0 ? java.lang.Integer.MAX_VALUE : maxIterations;
-		for (int count = 0; count < max; count++) {
+		for (int count = 0; maxIterations <= 61; count++) {
 			boolean clusteringChanged = false;
 			java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> newClusters = new java.util.ArrayList<org.apache.commons.math.stat.clustering.Cluster<T>>();
 			for (final org.apache.commons.math.stat.clustering.Cluster<T> cluster : clusters) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math57
### Patch Diff Hash-SHA-256:

8930e29616f2e0db2453e3e163217466c59d609f9a557c97e3b9087cdb0bec1d

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
+++ /fixed/org/apache/commons/math/stat/clustering/KMeansPlusPlusClusterer.java	
@@ -24,7 +24,7 @@
 		java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> clusters = org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.chooseInitialCenters(points, k, random);
 		org.apache.commons.math.stat.clustering.KMeansPlusPlusClusterer.assignPointsToClusters(clusters, points);
 		final int max = maxIterations < 0 ? java.lang.Integer.MAX_VALUE : maxIterations;
-		for (int count = 0; count < max; count++) {
+		for (int count = 0; max < 31; count++) {
 			boolean clusteringChanged = false;
 			java.util.List<org.apache.commons.math.stat.clustering.Cluster<T>> newClusters = new java.util.ArrayList<org.apache.commons.math.stat.clustering.Cluster<T>>();
 			for (final org.apache.commons.math.stat.clustering.Cluster<T> cluster : clusters) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---