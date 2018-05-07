
# Patches of Math95 from Defects4J 
Total patches 13
## Patch 1 of bug id Math95
### Patch Diff Hash-SHA-256:

e9c7ef08b1a07b29c8feb737446b86704c4cfb148718ef2f7fd64068f361676c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 2 of bug id Math95
### Patch Diff Hash-SHA-256:

10b117d1c0f9ad4da536775718f0ca3a2a1af096a9ae119f7e14b86629ecee65

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 1;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 3 of bug id Math95
### Patch Diff Hash-SHA-256:

aea512d986d8563d2f8b7ae1a012c96ffb78d22897ce03bb30e9d5c854f2aa36

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 1.0;
 		return ret;
 	}
```


---
## Patch 4 of bug id Math95
### Patch Diff Hash-SHA-256:

5873cd7e9c7d5e0523cdad5c67b2ace7f42bf2d182591e805c7bee32bd4786d2

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 0.0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 5 of bug id Math95
### Patch Diff Hash-SHA-256:

a352ca28161b3e081a2bc61f2bd9fb43baab8d88d26cac759c5dbdef6824e08e

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.5;
 		return ret;
 	}
```


---
## Patch 6 of bug id Math95
### Patch Diff Hash-SHA-256:

adf3a5fa438c381139815b1b1cbce752a95d1ec43bc296e420cd5d2ffbee7bc5

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 1.0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 7 of bug id Math95
### Patch Diff Hash-SHA-256:

ba3b1004a0da20a92d03b981b3afdc3f302e8ee33927c98fb25fffc647e25cbb

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return denominatorDegreesOfFreedom;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 8 of bug id Math95
### Patch Diff Hash-SHA-256:

01f7905674da5ce8e335632d9251fbbfb9faee0b7c707d1e256b617c3ecc6c82

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return numeratorDegreesOfFreedom;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 9 of bug id Math95
### Patch Diff Hash-SHA-256:

40942ea9b6cc93b4288900d511b079438e6901e630f548086b41bdc45fb8f3d7

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return p;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 10 of bug id Math95
### Patch Diff Hash-SHA-256:

39b632d33d2f70680dd090b89b1fa8cc65ff0ec7604f7cd52326628abfada660

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.0;
 		return ret;
 	}
```


---
## Patch 11 of bug id Math95
### Patch Diff Hash-SHA-256:

ce9a339b450fb94ec7c522f782ecd7356c215b8cbb016c081aec7a9749abf241

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,6 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
+		ret = 0.5;
 		return ret;
 	}
```


---
## Patch 12 of bug id Math95
### Patch Diff Hash-SHA-256:

894273b3d95684ca955d82d06a4af3063a674948d2a50ddb50a9bb2853da338b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,6 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
+		ret = 1.0;
 		return ret;
 	}
```


---
## Patch 13 of bug id Math95
### Patch Diff Hash-SHA-256:

7c21e218a6da3499a11956a42bae6fdd877d5c86720bc88a0a64c769c61b15c3

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,6 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
+		ret = 0.0;
 		return ret;
 	}
```


---