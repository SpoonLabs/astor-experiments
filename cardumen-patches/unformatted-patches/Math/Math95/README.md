
# Patches of Math95 from Defects4J 
Total patches 134
## Patch 1 of bug id Math95
### Patch Diff Hash-SHA-256:

0f4d230d3c6131b0113d60515d2ab02582b7b708894588abc24a92e9ec8e47e7

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 108.0;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math95
### Patch Diff Hash-SHA-256:

9eb8125ca198459e3e3cddfb9759b314c246e9c73fec48afb4358dd6ec1cd858

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return p = p + ((java.lang.Math.random()) * (p - p));
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math95
### Patch Diff Hash-SHA-256:

4c05e58fb2c562472bb56b68016acee24244c0f1d1727cbfbf82f55b0a55aacb

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = ((int) (java.lang.Math.floor(p)));
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math95
### Patch Diff Hash-SHA-256:

dcb7b56bebfcb5c26dfe4561cd504d70c35e0cca305cf625067e80fb0e1bd47f

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return java.lang.Math.sqrt(p);
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math95
### Patch Diff Hash-SHA-256:

facb3618089139609eaff7e39db4238060c4468f5bf91f5ce5b688f211b2104d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 1.0 / (p + p);
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math95
### Patch Diff Hash-SHA-256:

bd2dea81318b07e4528529b7e9510264e71047c7f323cc0bf98d8dd482264c3a

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return (p * p) * p;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math95
### Patch Diff Hash-SHA-256:

ee12a0ce315887fff75ed10f22c82405fc985c7227e4c2a5548f59c5f0e0a013

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = java.lang.Math.floor(p);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math95
### Patch Diff Hash-SHA-256:

26d0441cbbbfb7e67e67c562c9dc74ca3269f7ceed7bb8a9baf28d415b145e11

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = getDomainUpperBound(p);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math95
### Patch Diff Hash-SHA-256:

fb83a12b7bc79ee0d3053f85a9feb008e312d613fbcfd175a258eb616ee801f7

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = getDomainLowerBound(p);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math95
### Patch Diff Hash-SHA-256:

ac90896778225b1ca88c870386e7cd5328b73c66d954f01f7ece58946bf01c32

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return p = (p / ((p - 1) * (p - 2))) * p;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math95
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math95
### Patch Diff Hash-SHA-256:

0b6275f971ff1e2ec971634fd185a91162733016256c4ad8915d27e8eab80f74

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = java.lang.Math.log((1.0 - p));
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math95
### Patch Diff Hash-SHA-256:

666eefc3028525082e74c42a1d28935771e534d482b2f28ad0baa041bbf9ae61

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 39484.0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math95
### Patch Diff Hash-SHA-256:

45554967189de824675f73b110e6ccc1df10f57cf04b6bd36481ec5983248003

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return (2.0 * p) * (p - p);
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math95
### Patch Diff Hash-SHA-256:

1b04127c763d9713c801696034c6115473d37bd1473b9876b3212dbe9352bb50

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return '\n';
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math95
### Patch Diff Hash-SHA-256:

4e9d9ff2b2757041be81d73a04e1e1c90fad083332737b50e97b7d3e36657872

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return (6.0 - (java.lang.Math.sqrt(6.0))) / 120.0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math95
### Patch Diff Hash-SHA-256:

966ad7d2e513ecc7235709ab9c9490cd11547cc377ef9cb51ed5f8642424d8d6

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return java.lang.Math.pow(p, 4.0);
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math95
### Patch Diff Hash-SHA-256:

e7c11f37ad2901effe1aaa0164cfd4c49dc1b59bfc8ea4602f5acb6df07f24b4

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 3.0 / 8.0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math95
### Patch Diff Hash-SHA-256:

4ff4d5cd65fed7c11e0a96c0e5276219cc4327fbdb676d71b794f19ad8ebf1c5

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return p - p;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math95
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math95
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

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math95
### Patch Diff Hash-SHA-256:

fea55e9c912f9bd9fe888a454952bc957a19266598998a93c7016695c0474b2b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return (2.0 + (java.lang.Math.sqrt(2.0))) / 2.0;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math95
### Patch Diff Hash-SHA-256:

49829d1736e81f953e059f32c9bf65235091cd9608f0c153a8611dc655de65d0

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return java.lang.Math.floor(((java.lang.Math.floor(p)) / 2.0));
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math95
### Patch Diff Hash-SHA-256:

4fdcda6ac565cc8db3c6ac37a45b17c3883208d86da98cb7d009fb7f4b7e9b5a

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = getDomainLowerBound(numeratorDegreesOfFreedom);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math95
### Patch Diff Hash-SHA-256:

7d4fc78c6c9b2bf1ea0e1d40df4b2e70a3f79092b7553b843d3b5e137d3b4afc

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -50,7 +50,7 @@
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
 		ret = d / (d - 2.0);
-		return ret;
+		return 2 * p;
 	}
 
 	public void setNumeratorDegreesOfFreedom(double degreesOfFreedom) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math95
### Patch Diff Hash-SHA-256:

e7793ac47c0f45b725f01aa922dc8031ec9a6436125e5ca7ac66caa94f912143

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = p - 2.0;
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math95
### Patch Diff Hash-SHA-256:

6355219b3ab2cafed663543f80ca8ac14fd1180444dae315c2a107c67a838298

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.5 * p;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math95
### Patch Diff Hash-SHA-256:

9d92db07305741ccb57269676cd4da0c30e83c6664fbc4fa4d66d2532fc4c68f

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p * p;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math95
### Patch Diff Hash-SHA-256:

50a8e68515ea7e2f9c40595501c9eb282b71ec3e6a8e1137254d12be02d9d878

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = getDenominatorDegreesOfFreedom();
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math95
### Patch Diff Hash-SHA-256:

50b488a21938f9353e981ef568f4567eb580186c0e26a4a5b392832f37534907

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = getDomainLowerBound(p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math95
### Patch Diff Hash-SHA-256:

73c2a18e48ae6bfd3fab57387e3e966e4329a98519a8073f70765c1a57dc434d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = getNumeratorDegreesOfFreedom();
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math95
### Patch Diff Hash-SHA-256:

ac1ce830d6bc58f0614288a2604bfa5a74ed88c5fc5d6894ebbcc06d950f779f

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = getDomainUpperBound(numeratorDegreesOfFreedom);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math95
### Patch Diff Hash-SHA-256:

b41fd1b1c24796c2073b2380378dae5ee56f0e31d4e2d4c54bc88a2914804783

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = p / (p - 2.0);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math95
### Patch Diff Hash-SHA-256:

94022725197b7496aa1fa1723a4681dd5bb45769d65191d46c943b3f9e6a1674

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * p) / (p + (p * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math95
### Patch Diff Hash-SHA-256:

34f18677381aaa6c57a5393ade880b0bbebfe3654a6940741c7eda1aa35c8823

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = (numeratorDegreesOfFreedom) - 2.0;
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math95
### Patch Diff Hash-SHA-256:

5fdf863f11b01020689991abc254d2eab1f2588694363cd89131d1d475bdc867

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = getDomainLowerBound(numeratorDegreesOfFreedom);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math95
### Patch Diff Hash-SHA-256:

101bee7b0a490e4d3a2229ac193fe0df70b572b9df05389d770254cf56e32fd2

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = getDomainLowerBound(denominatorDegreesOfFreedom);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math95
### Patch Diff Hash-SHA-256:

8778ae12283c60da39a6d30114dc4fb52aa4df74d5ba05aff06b75d919302df8

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = getDomainUpperBound(denominatorDegreesOfFreedom);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math95
### Patch Diff Hash-SHA-256:

f3f352caac138d580c990397bb98753a18727442884b4d38693dc7470c4f9342

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = (denominatorDegreesOfFreedom) - 2.0;
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math95
### Patch Diff Hash-SHA-256:

2ed24abaf50ef5818e4ff088b2eedf2569b0d2e6c44af78b88419036bff7b58c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.5 * (numeratorDegreesOfFreedom);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math95
### Patch Diff Hash-SHA-256:

4934fd06cb94045c8e0afee4e123ed590340d74736ee24a58e95c9bc7ed4f44b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.5 * (denominatorDegreesOfFreedom);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math95
### Patch Diff Hash-SHA-256:

6e04b907cbba43f9c1843ecca4f888bd4b439d0b66a1a50fe027257abbfd328d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = 0.5 * d;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math95
### Patch Diff Hash-SHA-256:

32daf72bbf485dc2117d62cc2638744483a7e36fb62b9410e4f9d5f3371de505

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = getDomainLowerBound(d);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math95
### Patch Diff Hash-SHA-256:

cc71a5964bf803eebb72c0b4a91ab398ffcae874ba5f6991e307bf3c1fd7e19d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * p) / ((numeratorDegreesOfFreedom) + (p * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math95
### Patch Diff Hash-SHA-256:

7de781aab62aad37e2f39e3d490ae5e395cac58629072b3c4b072d94000800fb

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p + (p * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math95
### Patch Diff Hash-SHA-256:

fda311d1fc36ca4b815c066f464071dd07481b6e5c3d03f1901e79ee40186228

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -48,7 +48,7 @@
 
 	protected double getInitialDomain(double p) {
 		double ret;
-		double d = getDenominatorDegreesOfFreedom();
+		double d = getDomainLowerBound(denominatorDegreesOfFreedom);
 		ret = d / (d - 2.0);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math95
### Patch Diff Hash-SHA-256:

8bd85cb69fe9c127de90c002197207c545cf6dab5c37a909ce02c4098185b483

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p * (numeratorDegreesOfFreedom);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math95
### Patch Diff Hash-SHA-256:

ed9fa84740e4c221f85548b73a45706caf22552dc6c4b46a3122defcaef1e104

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p * (denominatorDegreesOfFreedom);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math95
### Patch Diff Hash-SHA-256:

545638b8ca84698dd3d5b72c97c4d6cb8bd46743486826cb8f5e30fd306b0885

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p * d;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math95
### Patch Diff Hash-SHA-256:

d52959ff9775b7a9e223381ab6c8cafd39a9bcd3131dd31523ca64b989fa71f3

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * p) / ((numeratorDegreesOfFreedom) + ((numeratorDegreesOfFreedom) * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math95
### Patch Diff Hash-SHA-256:

cb275aee4dd0bde90f9f6df9fc835feb6f59ebdcdc7fee4e910bc79c13923a34

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) * p;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math95
### Patch Diff Hash-SHA-256:

5918d49de6a36fdb857e67f179a21f76ad06e7b4a1c0185c6a8e24ed07bde32d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) * p;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math95
### Patch Diff Hash-SHA-256:

87b6555b1ac153e368830dc597d0c251629201f925625ce71b0f8eff5a55aced

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) + (p * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math95
### Patch Diff Hash-SHA-256:

cca3191266f11672e6ccaa8bf7cbb75da46c124edb7d316052bc4a173067f624

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) + (p * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math95
### Patch Diff Hash-SHA-256:

f05e657fb7263e0b2580dad9fa811e7db98f93949ee053b02bc3dcfa74f188d8

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d * p;
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math95
### Patch Diff Hash-SHA-256:

e6d9ae907561597b194fd441ec20962d67768a23791fa85a764568ab746a8a06

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d + (p * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math95
### Patch Diff Hash-SHA-256:

ae83e1007957c83d2ea1332dd7c5879ceabd4d6b539e7c7e60bf8b5c96f151a9

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * (numeratorDegreesOfFreedom)) / ((numeratorDegreesOfFreedom) + (p * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math95
### Patch Diff Hash-SHA-256:

ed0730c3b25b1e9b28b15ffb2c5b41efdb45a92085ce306b046e47373723d612

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p + ((numeratorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math95
### Patch Diff Hash-SHA-256:

52a6b5a7776f9a1638a32d257518b644b61c5eeeed447c3bc5cad59520499fe2

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) + ((numeratorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math95
### Patch Diff Hash-SHA-256:

72c14eb8e1dea4fab4971ef47f32f71a03d03a190af93b3d15e3a61a2c18f62a

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * (numeratorDegreesOfFreedom)) / (p + ((numeratorDegreesOfFreedom) * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math95
### Patch Diff Hash-SHA-256:

bdc8a93e0f3d430f1c6d34c01f2a590cd2834eb7b666ec3b8e281b5182b6e20c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) + ((numeratorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math95
### Patch Diff Hash-SHA-256:

51e07ef2be821817a4293aa6e0ccfe7d41bbc34bb5c1c97cc5d11aab695d3964

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d + ((numeratorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math95
### Patch Diff Hash-SHA-256:

2a6bd1857004b5659ff045497643020ff8bcd8dea5206b7e80a70229086976c4

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p + ((denominatorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math95
### Patch Diff Hash-SHA-256:

fd993838003a36def432d3df6c9133230d7f7396cd4ee4f8b2df66f69f079412

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math95
### Patch Diff Hash-SHA-256:

66ca402222ea245ed3f25aa42569dde42d42cc4b5117467e099b539e3fc189ab

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math95
### Patch Diff Hash-SHA-256:

ad8f7f8ddb8ca69ba3c96be4e2fe2a772f5dc0c897a3e2d7768d88d694456f8c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d + ((denominatorDegreesOfFreedom) * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math95
### Patch Diff Hash-SHA-256:

4d38a0f7713d0435b76f57cb911060229556e46a381216aa8d9d8931cf03bb91

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p + (d * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math95
### Patch Diff Hash-SHA-256:

f19de103fc1ba3eb9828e3a47670fd6a241b3b42bce15187c21f54f988435988

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) + (d * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math95
### Patch Diff Hash-SHA-256:

aa0a8a1289cf3839514a8b2dce41d6db137a5673f93d271fdaa8bfcf94023425

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) + (d * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math95
### Patch Diff Hash-SHA-256:

71806171dc4d1ba361ad9e17c70363e027713d64290d5c25b0c109be2913a1ed

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d + (d * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math95
### Patch Diff Hash-SHA-256:

51ebff4e45c9c191669b5d53a28dbdab06a4e69b8f36b2162712c9bdf06d865d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p + (p * (numeratorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math95
### Patch Diff Hash-SHA-256:

2741e94533554c7633f7aa581030c0c422240407639f25336d20ad1b8564eaca

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) + (p * (numeratorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math95
### Patch Diff Hash-SHA-256:

20e4a0af709f3f761dd1dc24f8343bf22c0846e0382b197be5b35f83138bfd9c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) + (p * (numeratorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math95
### Patch Diff Hash-SHA-256:

8434e9feaf84e77fd03c72c5018c395a731d7f3a8d3dd7e135e82d5ca35d4ff5

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d + (p * (numeratorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math95
### Patch Diff Hash-SHA-256:

b5b5f40e875a2d47fe7a7cc6a2a087966736f65f438ef299b63456ca3ca7b59d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p + (p * (denominatorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math95
### Patch Diff Hash-SHA-256:

6ff0848ffbbb8c26d250ef273b53cb95e037377c7c3a69c7d6e77bcc754064dd

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) + (p * (denominatorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math95
### Patch Diff Hash-SHA-256:

f58444faed1bf2c3b0bdf2bd6b52b55a12c914df9a9611ec6d6bc2205f224d2c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) + (p * (denominatorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math95
### Patch Diff Hash-SHA-256:

c13018c6260dc6a1bf5097329239eda1e9408e59e9938bb81284ab49b41b346b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)) / ((denominatorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math95
### Patch Diff Hash-SHA-256:

eda928ecd0453c4b69e0a2eb1c25efd7ca3e3f500115844fdcd7ea22fc889fb1

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * d) / (d + (d * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math95
### Patch Diff Hash-SHA-256:

f303303edf089d72d4a48c90c36276b7072ac9a3b597bb735742969307ba6ae3

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * p) / ((denominatorDegreesOfFreedom) + (p * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math95
### Patch Diff Hash-SHA-256:

99607d8969ca2a9858366fe94860bb4759ba34a2c49f56e817dc5de2909192e4

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * p) / (d + (p * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math95
### Patch Diff Hash-SHA-256:

de60964e01fa4fba6b204be226512313487af78f173d2afa42e7208c63de8b25

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * (numeratorDegreesOfFreedom)) / ((denominatorDegreesOfFreedom) + (p * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math95
### Patch Diff Hash-SHA-256:

2bdcefef435c862e89190d72d751b0285d9232ab04f9582066931399ca357ba8

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * (numeratorDegreesOfFreedom)) / (d + (p * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math95
### Patch Diff Hash-SHA-256:

a0b56fb03c7b329b2c3cf051fca0ec2798c56c8821e5197d6694c534f6410825

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * (denominatorDegreesOfFreedom)) / (p + (p * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math95
### Patch Diff Hash-SHA-256:

1b4aca1fea62b0a37463ff92edb4859c9d93c053dd3193718be51655d1c782f2

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * (denominatorDegreesOfFreedom)) / ((numeratorDegreesOfFreedom) + (p * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math95
### Patch Diff Hash-SHA-256:

014d586183dd442c15fc7097a2b0db31e1a5de634fb115c1a78e9b16ad29e020

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * (denominatorDegreesOfFreedom)) / ((denominatorDegreesOfFreedom) + (p * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math95
### Patch Diff Hash-SHA-256:

b7653add26895e398d9cbf67c8362356b3517660b26134ad424b4b0233b4e0d6

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * (denominatorDegreesOfFreedom)) / (d + (p * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math95
### Patch Diff Hash-SHA-256:

8cf2fba678f4afc7324cdf1a309053fcc57691831d0d6e09974bc8a2cc05d15a

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * d) / (p + (p * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math95
### Patch Diff Hash-SHA-256:

8371023db465c87e6d44cc75b2550fe2ed56a96983ec0d7290395b8e109c5fea

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * d) / ((numeratorDegreesOfFreedom) + (p * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math95
### Patch Diff Hash-SHA-256:

d43c772cc96fcadaf32ec19e078b27eee017fe7f77a359bf022f9fddc26c097d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * d) / ((denominatorDegreesOfFreedom) + (p * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math95
### Patch Diff Hash-SHA-256:

709d8fe7dd2856c8a137bfc134269181673aa0403d534265eaa6664ec821a56d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (p * d) / (d + (p * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math95
### Patch Diff Hash-SHA-256:

25d3885f4bbf240d0b2e532d2f82443c3a77c6ff0100c646c214f930bee9ef9e

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * p) / ((denominatorDegreesOfFreedom) + ((numeratorDegreesOfFreedom) * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math95
### Patch Diff Hash-SHA-256:

7f45fb4a0edb7d152a21840a3c8b53682236f842791256a27524e24e74a887b5

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * p) / (d + ((numeratorDegreesOfFreedom) * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math95
### Patch Diff Hash-SHA-256:

0e3d100929e39f6e067d0ff69318e30a55a0670f57b8ef19c53c78f8aad89de2

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * (numeratorDegreesOfFreedom)) / ((denominatorDegreesOfFreedom) + ((numeratorDegreesOfFreedom) * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math95
### Patch Diff Hash-SHA-256:

61e3c48513a9c82c615fab88b6becaa54d941e96b15a29336dc62d9fbc8ce73b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * (numeratorDegreesOfFreedom)) / (d + ((numeratorDegreesOfFreedom) * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math95
### Patch Diff Hash-SHA-256:

d2276a5bc043afc2df2795250711366395ad8cdab40581fab44b6e1e4925d21a

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * (denominatorDegreesOfFreedom)) / (p + ((numeratorDegreesOfFreedom) * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math95
### Patch Diff Hash-SHA-256:

d88ef9cd497ab8ef55c933bb629f94b71e0f0f5edb5650b047f154817b8d0a84

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * (denominatorDegreesOfFreedom)) / ((numeratorDegreesOfFreedom) + ((numeratorDegreesOfFreedom) * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math95
### Patch Diff Hash-SHA-256:

ad8a41d8b0cab392e645ab07d3fd3453d09ff1af1f34dd3221234cf88795e80d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * d) / (p + ((numeratorDegreesOfFreedom) * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math95
### Patch Diff Hash-SHA-256:

5c1d6ab0fa366b37785c9400f902a67004f7c58da05f5ef76101b31d3f8223e0

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((numeratorDegreesOfFreedom) * d) / ((numeratorDegreesOfFreedom) + ((numeratorDegreesOfFreedom) * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math95
### Patch Diff Hash-SHA-256:

26503d178d723b0737515195968b728d50b08c71dd39a8d35a89e7960461758c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * p) / (p + ((denominatorDegreesOfFreedom) * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math95
### Patch Diff Hash-SHA-256:

aeaea861004452383387967e6a0bbf320f630c17b221de7b0fa473b8f1d98d16

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * p) / ((numeratorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math95
### Patch Diff Hash-SHA-256:

039b250d71505c1872973bec478261f62b70ebc3564f24b60022e1e7b0cad342

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * p) / ((denominatorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math95
### Patch Diff Hash-SHA-256:

957e9594e390d4986ca093e627b8fbdbeebaf95876e6060be59169e7aeb3e592

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * p) / (d + ((denominatorDegreesOfFreedom) * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math95
### Patch Diff Hash-SHA-256:

f7ca28c9ae7d8658d60ed32b27850e367694d0a96c287294919b8c2e687e5dfd

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d + (p * (denominatorDegreesOfFreedom));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math95
### Patch Diff Hash-SHA-256:

98a01eacde96b641204fa9a50fe5e22b743e10698365506beb06db189168e7f4

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * (numeratorDegreesOfFreedom)) / (p + ((denominatorDegreesOfFreedom) * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math95
### Patch Diff Hash-SHA-256:

e05bd88a85037c68986c6a3d7e24b9f9ab505b2e0a1e7a93db05a19baa86e14f

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * (numeratorDegreesOfFreedom)) / ((numeratorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math95
### Patch Diff Hash-SHA-256:

fccabd69768a728015581ada9d06641075c16362475201d22e2496b48c715d4c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)) / (p + ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math95
### Patch Diff Hash-SHA-256:

220f95db72b12d1c4239d375ad1f2fb3e575506b7a0d2762c4bfc5a4f737479b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)) / ((numeratorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math95
### Patch Diff Hash-SHA-256:

43f02b649842b99ba7766d6c02f90841e11c3e78c594ec11d27b2a21749ec3b6

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)) / (d + ((denominatorDegreesOfFreedom) * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Math95
### Patch Diff Hash-SHA-256:

1b30e451c2ad338e6ee7a4aae47e72bffe8978394a9770250bbba48060a162c3

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * d) / (p + ((denominatorDegreesOfFreedom) * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Math95
### Patch Diff Hash-SHA-256:

b3bc555655e02340af312ad7c1fa3849597d138ad339f7f7046b211a878af174

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * d) / ((numeratorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Math95
### Patch Diff Hash-SHA-256:

a73ba6dae58c8438df0783380ad6d13ccbed131ca91dd862a3c807dbbb48d06d

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * d) / ((denominatorDegreesOfFreedom) + ((denominatorDegreesOfFreedom) * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Math95
### Patch Diff Hash-SHA-256:

2b8967a63f90db5d88c0ef40874964ae40bc60897d79823c7ac069175baf9f92

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = ((denominatorDegreesOfFreedom) * d) / (d + ((denominatorDegreesOfFreedom) * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Math95
### Patch Diff Hash-SHA-256:

0f2550c5b8bfa627c377563417cf99a2c74b57b0643506eeabfa83d53a1799f8

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * p) / (p + (d * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Math95
### Patch Diff Hash-SHA-256:

b5553e1476ad1d18efe64fdefef0d829be33afcf1cd107ce8548e015f0b9312b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * p) / ((numeratorDegreesOfFreedom) + (d * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Math95
### Patch Diff Hash-SHA-256:

853be951147cf8605be33dbc388e0b7a97d444e2cd93a9658af1b16ac88393e1

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * p) / ((denominatorDegreesOfFreedom) + (d * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Math95
### Patch Diff Hash-SHA-256:

de6d101127a8e34b11e018c6b00dc1b09e7d62fab60bba665ee4d59c183209a0

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * p) / (d + (d * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Math95
### Patch Diff Hash-SHA-256:

0b4ee1efb6c6e68e7cb466ba5058a1c46d1b5fdb91102ef19e20d48a51467f35

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * (numeratorDegreesOfFreedom)) / (p + (d * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Math95
### Patch Diff Hash-SHA-256:

d86333c9905458a405d915fed771e3792b9d03cde436b3eb97554c78f349586b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * (numeratorDegreesOfFreedom)) / ((numeratorDegreesOfFreedom) + (d * (numeratorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Math95
### Patch Diff Hash-SHA-256:

bb42dd639a4cdddc631ef885b720dd78b7929fb8a9e890fe5f7798b06cd8ecc5

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * (denominatorDegreesOfFreedom)) / (p + (d * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Math95
### Patch Diff Hash-SHA-256:

42ac034eb664d207d360033f8c9f640e704689bd34bde919d1f67ad939751e47

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * (denominatorDegreesOfFreedom)) / ((numeratorDegreesOfFreedom) + (d * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Math95
### Patch Diff Hash-SHA-256:

74918072db7d693d8f346f63be9899da954d06c6e81003373488e93342b2523b

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * (denominatorDegreesOfFreedom)) / ((denominatorDegreesOfFreedom) + (d * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Math95
### Patch Diff Hash-SHA-256:

7af7d7fb9fffb1806851118d167f49cb477fffa9ef9854a02e6b28faffc30400

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * (denominatorDegreesOfFreedom)) / (d + (d * (denominatorDegreesOfFreedom)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Math95
### Patch Diff Hash-SHA-256:

2cd2b5a41a5bb76225d79e01d656a16bf3fa03395f1b5ffa3755e8ec627cefc2

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * d) / (p + (d * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Math95
### Patch Diff Hash-SHA-256:

20bccbd7f3d7b7cfa597a06abfaede17a3002a41e0f166f045265fee5ceab12e

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * d) / ((numeratorDegreesOfFreedom) + (d * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Math95
### Patch Diff Hash-SHA-256:

2c433a7bd374d7b1e12357b7d07c40aea1663214a8c9959f3a17f38fd59b2403

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (d * d) / ((denominatorDegreesOfFreedom) + (d * d));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Math95
### Patch Diff Hash-SHA-256:

ce323dbcc874f8a22ad94fc5edb51858b9329e93022029ffc8a197f51b527cbb

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = p + (p * d);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Math95
### Patch Diff Hash-SHA-256:

fd2a6802ddee19c914e88110bf72eb9663fa829cf31cf04a32f3110d4cba9362

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (numeratorDegreesOfFreedom) + (p * d);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Math95
### Patch Diff Hash-SHA-256:

881f094dba50b60d4a81af157a3b971c5ea76c76af74467143f31ad4f727f72c

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = (denominatorDegreesOfFreedom) + (p * d);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Math95
### Patch Diff Hash-SHA-256:

ffee1bf3f357714871804871e901deb61f7549c639a769255714588cd9211032

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d + (p * d);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Math95
### Patch Diff Hash-SHA-256:

b3447edcc8ca5a323f2e7ff3ad6533e032f6077fb410f006783fa4b677c0a653

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d / (getDenominatorDegreesOfFreedom());
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Math95
### Patch Diff Hash-SHA-256:

e12daf8432435a52f75ac66e08895feec7ef03452bd85252a411529d695836ed

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d / (p * p);
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Math95
### Patch Diff Hash-SHA-256:

7c9a23f2e38832715b73a1c39184ac50a51c253fda53e11e5039bb0805b134b9

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d / (p + (p * p));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Math95
### Patch Diff Hash-SHA-256:

69b5c1022d8764b461d4a95d89c0978eef4165a7e5fb6ec924ebd18b6bdcca67

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/FDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/FDistributionImpl.java	
@@ -49,7 +49,7 @@
 	protected double getInitialDomain(double p) {
 		double ret;
 		double d = getDenominatorDegreesOfFreedom();
-		ret = d / (d - 2.0);
+		ret = d / ((p * p) / (p + (p * p)));
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---