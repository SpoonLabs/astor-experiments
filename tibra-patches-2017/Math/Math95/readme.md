
# Patches of Math95 from Defects4J 
Total patches 13
## Patch 1 of bug id Math95
### Patch Diff Hash-SHA-256:

f3061ca0dca943a9054ca8a22aa78b61c0d70ed01da2cc3e5fe6c60b099a1331

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -47,7 +47,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.5 * p;
 		return ret;
 	}
```


---
## Patch 2 of bug id Math95
### Patch Diff Hash-SHA-256:

b749e15a8ca675413833d6a491dac1f4c0ee619c1a78a7bfb7c612793b197165

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return denominatorDegreesOfFreedom;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 3 of bug id Math95
### Patch Diff Hash-SHA-256:

cf671e4bdee59fa48e04d15c78342865c6ebca9b32bf32be67a879680b5e974a

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return p;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 4 of bug id Math95
### Patch Diff Hash-SHA-256:

b9042c6aa4a15860a95cc15a3c6f45bc68f8ce9d133b26b678c85d1295514b3f

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,6 +48,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
+		ret = 0.5;
 		return ret;
 	}
```


---
## Patch 5 of bug id Math95
### Patch Diff Hash-SHA-256:

9d88fba56841db3f5facec94cf61d3cfc276100bcfc2c156ae9371f8998a60d1

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -47,7 +47,7 @@
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

6cfd2b5bceb9c633da8e8406640b2c4233de425c909581f33c0aa4e907d1e608

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return numeratorDegreesOfFreedom;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 7 of bug id Math95
### Patch Diff Hash-SHA-256:

ef32e4f208609e24140b0628da3b608f519ae934146266e7232ce1c24cd40cbb

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -47,7 +47,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 1.0;
 		return ret;
 	}
```


---
## Patch 8 of bug id Math95
### Patch Diff Hash-SHA-256:

5cb36e19762ccce31af5fae903f36e987d6247b3a9aee253d7f0a080af82f459

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return d;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 9 of bug id Math95
### Patch Diff Hash-SHA-256:

b869973be53b4847f208e64dfd46f5a5b5bce2548e7e1859df2f34f2c3853920

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -47,7 +47,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p;
 		return ret;
 	}
```


---
## Patch 10 of bug id Math95
### Patch Diff Hash-SHA-256:

3c2eee40960547de3ee418621b2c267e3f6ca39629db4dafce48f05d67cc5616

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -47,7 +47,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 1.0 - (0.5 * p);
 		return ret;
 	}
```


---
## Patch 11 of bug id Math95
### Patch Diff Hash-SHA-256:

fefecb4aa0cb1ca84054f5ee3b7da8a20f52345fa05a0c8ac00190b98206b346

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 0.5 + ((java.lang.Math.atan((((numeratorDegreesOfFreedom) - (denominatorDegreesOfFreedom)) / (numeratorDegreesOfFreedom)))) / (java.lang.Math.PI));
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 12 of bug id Math95
### Patch Diff Hash-SHA-256:

3f6f5e058052e71a9bee374096d4d499690601b6dc29587e55cb7f20700b5dc5

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 1.0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```


---
## Patch 13 of bug id Math95
### Patch Diff Hash-SHA-256:

2927ebe0cf181cdf6f449d407c775fd56f145b8dd40ab3a01b543d744a725f8e

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -47,7 +47,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.0;
 		return ret;
 	}
```


---