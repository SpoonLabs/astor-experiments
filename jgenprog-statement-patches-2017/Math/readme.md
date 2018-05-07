
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
## Patch 1 of bug id Math50
### Patch Diff Hash-SHA-256:

0e36c4afa2725aed0c377f1c761e7c8ea90c7e2217956160050e9d120c811416

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -77,10 +77,9 @@
 						f0 *= f1 / (f1 + fx);
 						break;
 					case REGULA_FALSI :
-						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+						if (x == x1)
 							f0 = computeObjectiveValue(x0);
-						}
+						
 						break;
 					default :
 						throw new org.apache.commons.math.exception.MathInternalError();
```


---
## Patch 2 of bug id Math50
### Patch Diff Hash-SHA-256:

1839b7b93dca08afa17912996ef7e5ab743717da949e94518f6b4b8cdac4967f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
-							f0 = computeObjectiveValue(x0);
+							f0 = f1;
 						}
 						break;
 					default :
```


---
## Patch 3 of bug id Math50
### Patch Diff Hash-SHA-256:

235eff4d38de9ee26a6eb718fd54c4e09825e9f4279a2f2d627e9d6149da9f60

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f0 = computeObjectiveValue(x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 4 of bug id Math50
### Patch Diff Hash-SHA-256:

a21a14e9d89fb2611402a59b8fc982c1128e71e2bbc1068de284239e51e1f390

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f0 = f1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 5 of bug id Math50
### Patch Diff Hash-SHA-256:

a6dfb0319a393b5b7311e9ea361dd1f0303aef359c05243043a8f42d041befb2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							final double y = computeObjectiveValue(x);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 6 of bug id Math50
### Patch Diff Hash-SHA-256:

8242067c57ca7f370af44a57c6986c05abf6e571fd2687a2f9f56eece0c763fa

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							inverted = !inverted;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 7 of bug id Math50
### Patch Diff Hash-SHA-256:

8d6f3c7f458c318ef6897634316750a9061fa0340b70ef585aef7335c2b74307

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f1 = fx;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 8 of bug id Math50
### Patch Diff Hash-SHA-256:

0aac1d53d21216b07193d88179bf1beb3a0fb85b110a2cd8e95f63efcc0202ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,7 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = x;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 9 of bug id Math50
### Patch Diff Hash-SHA-256:

4d153fbce4592fe8acb76b06e0e35990c377ee0b86f90383789d961f35aa43d8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							double y0 = computeObjectiveValue(x0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 10 of bug id Math50
### Patch Diff Hash-SHA-256:

3c8b92a5a25e598b027e36be8e4bd25e99debf6005aca765a5085a574c1fe08f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							f0 = f1;
 						}
 						break;
 					default :
```


---
## Patch 11 of bug id Math50
### Patch Diff Hash-SHA-256:

5f59021bfdd27d7eea61558a7ccb77f66fdb0600f61d92690c2d2cec4442ceb3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							double y1 = computeObjectiveValue(x1);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 12 of bug id Math50
### Patch Diff Hash-SHA-256:

0f94c673d0e1599e0a0099b45d4ecbe4249658c95947cdd298786dc07c7061c0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							incrementEvaluationCount();
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 13 of bug id Math50
### Patch Diff Hash-SHA-256:

35644789c52bd3906348ecb13cdab05e9c71f955b3ca08863990ecb7e3b17dce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							f0 = computeObjectiveValue(x0);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 14 of bug id Math50
### Patch Diff Hash-SHA-256:

7658e2e34584088babde33cd83d8599ca4fdf14a4864bad86fe0d72f0f01fc67

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							final double y = computeObjectiveValue(x);
 						}
 						break;
 					default :
```


---
## Patch 15 of bug id Math50
### Patch Diff Hash-SHA-256:

a70cbcd9957596299d998f713b8d6b2db702d493375b5ac4bdcd234de33fccaf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,6 +78,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							final double y = computeObjectiveValue(x);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 16 of bug id Math50
### Patch Diff Hash-SHA-256:

e2f2bbff5878acadd7c7201706a601fea11074c4d9a4b5dfda73f9625f8b4fdb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							incrementEvaluationCount();
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 17 of bug id Math50
### Patch Diff Hash-SHA-256:

b923587be4af317c2532f1d4774b7f8d9b034194083b0e9d9d6a515b58d54470

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							double y1 = computeObjectiveValue(x1);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 18 of bug id Math50
### Patch Diff Hash-SHA-256:

38ac2a0749b9d6cd1484ce513e991ba6b940e395b3725ca67fe6433d53321cb1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							double y1 = computeObjectiveValue(x1);
 						}
 						break;
 					default :
```


---
## Patch 19 of bug id Math50
### Patch Diff Hash-SHA-256:

ebaf53bd64407317e617b5fb61da46198d2c6b33cef68ada48347b709f490939

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							incrementEvaluationCount();
 						}
 						break;
 					default :
```


---
## Patch 20 of bug id Math50
### Patch Diff Hash-SHA-256:

33e35d8baf2e608aea49fe586558e4e0db2973f304f20f6db64832ffd3973c64

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							f0 = computeObjectiveValue(x0);
 						}
 						break;
 					default :
```


---
## Patch 21 of bug id Math50
### Patch Diff Hash-SHA-256:

c48236c4a7214d92a041b453f97b7d3ebc85c9641fb8a941c538f625fe2e31dc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
+							double y0 = computeObjectiveValue(x0);
 						}
 						break;
 					default :
```


---
## Patch 1 of bug id Math73
### Patch Diff Hash-SHA-256:

fc6c66cb7d6c2e485e64f163c8911a7742ece23857ed1d1b1856ce836075092a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,6 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		verifyBracketing(min, max, f);
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 2 of bug id Math73
### Patch Diff Hash-SHA-256:

be03ce6fb61e671dbfb2ce3eace729e5b33a09da0ed19b28f0070374f95223d7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 3 of bug id Math73
### Patch Diff Hash-SHA-256:

6169208900ea8e481adc32c24cf95dc7119811bbcc84ef9f7d54fd018dbe71c2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 4 of bug id Math73
### Patch Diff Hash-SHA-256:

26b8bde6fbf8002ffa55f9f86953c519f981199de2368fa080319e90b477075d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -51,7 +51,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 5 of bug id Math73
### Patch Diff Hash-SHA-256:

7b1e9239dd73db3794bb8324f3279016517036278d867c0da428aeea5193956f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -43,6 +43,7 @@
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
+		verifyBracketing(min, max, f);
 		double yMax = f.value(max);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
```


---
## Patch 6 of bug id Math73
### Patch Diff Hash-SHA-256:

9e3b4de696e3bed2ce1edf50eede88d55538cb64591452bd888aa6ef34fcb732

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,7 @@
 			setResult(initial, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
```


---
## Patch 7 of bug id Math73
### Patch Diff Hash-SHA-256:

d1c2d4467e868c9c0bee6551a6541dd6b3965e0ddaf2fe188f0b616b7a14584a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -40,6 +40,7 @@
 			setResult(yMin, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
```


---
## Patch 8 of bug id Math73
### Patch Diff Hash-SHA-256:

f03e6f3977a1fdb8ac8f0f7fa8654494bb41876ab650fc8a34cfe749a8aac086

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 			return result;
 		}
 		double yMin = f.value(min);
+		verifyBracketing(min, max, f);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
 			return result;
```


---
## Patch 9 of bug id Math73
### Patch Diff Hash-SHA-256:

103006e353c2d1eb1b89b5f52e3615bd813cbd346cd88dbd52b48455e2bc3188

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -48,6 +48,7 @@
 			setResult(yMax, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
```


---
## Patch 10 of bug id Math73
### Patch Diff Hash-SHA-256:

ad5f0297dd7deacf74ea2306bdb57264cac8c62e6a80cfd6450d2435967596ac

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -44,6 +44,7 @@
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
 		double yMax = f.value(max);
+		verifyBracketing(min, max, f);
 		if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 			setResult(yMax, 0);
 			return result;
```


---
## Patch 1 of bug id Math80
### Patch Diff Hash-SHA-256:

f7fd691ed8a5f28b01abbbc4965cf6cc5b88550660bf69713a9ddedc18528b61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,14 +675,6 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
-				}
-				j -= 4;
-			}
 			return true;
 		}
 		return false;
```


---
## Patch 2 of bug id Math80
### Patch Diff Hash-SHA-256:

6d19107d8952a93b879f252c91aae4f926497135b1d70231ecdc2dcb78fa5cfa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		computeGershgorinCircles();
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 3 of bug id Math80
### Patch Diff Hash-SHA-256:

cc823888e33a6f4f47b668e50841bf47cad3399079fc0834b004d5c259611c54

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,7 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
+		java.util.Arrays.sort(realEigenvalues);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 4 of bug id Math80
### Patch Diff Hash-SHA-256:

c67dda0966d287f5ff411e53e1d7215e2e6260c4e2f42cbd1e7acf94854d99f4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					tType = -6;
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 5 of bug id Math80
### Patch Diff Hash-SHA-256:

ce2e7d8a91da07b69523c58b11716ae1cefdbd8507d0b37b301bb7a75670f1cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,6 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 6 of bug id Math80
### Patch Diff Hash-SHA-256:

f104c914d6933c19d6f0b522638711bf3be8abc18e6265d40c391c1591fc4291

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -479,7 +479,6 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 7 of bug id Math80
### Patch Diff Hash-SHA-256:

5c222e09fd8e36abe5b45d5a029b2d3fbcdc14d1a6c2e06a15e4aad499845d16

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -675,14 +675,9 @@
 	private boolean flipIfWarranted(final int n, final int step) {
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
-				}
+			for (int i = 0; i < j; i += 4)
 				j -= 4;
-			}
+			
 			return true;
 		}
 		return false;
```


---
## Patch 8 of bug id Math80
### Patch Diff Hash-SHA-256:

5dd480a64c61709ba3645717b9a4bbcbc0c43bd904c8138fd7a5e61981921abe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,18 +673,6 @@
 	}
 
 	private boolean flipIfWarranted(final int n, final int step) {
-		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
-			int j = (4 * n) - 1;
-			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
-				}
-				j -= 4;
-			}
-			return true;
-		}
 		return false;
 	}
```


---
## Patch 9 of bug id Math80
### Patch Diff Hash-SHA-256:

6809ec87e9dd886ba8f1a9a0bce1062b0bfd74689318abb80c2e1948f140e97f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -724,6 +724,7 @@
 			if ((range < absoluteTolerance) || (range < (relativeTolerance * (java.lang.Math.max(java.lang.Math.abs(left), java.lang.Math.abs(right)))))) {
 				break;
 			}
+			pingPong = 1 - (pingPong);
 			final double middle = 0.5 * (left + right);
 			if ((countEigenValues(middle, index, n)) >= n) {
 				right = middle;
```


---
## Patch 10 of bug id Math80
### Patch Diff Hash-SHA-256:

d7d8b14fb8b8ca2705464dd71ccf756f4d062840223942024b290dc6ff07749c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					tau = -(dMin);
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 11 of bug id Math80
### Patch Diff Hash-SHA-256:

6356e805517704d8a401608d47e9e1eabd39e69a5fea3d1f1d5d6b0f5c16b207

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -471,6 +471,7 @@
 
 	private void processGeneralBlock(final int n) throws org.apache.commons.math.linear.InvalidMatrixException {
 		double sumOffDiag = 0;
+		pingPong = 1 - (pingPong);
 		for (int i = 0; i < (n - 1); ++i) {
 			final int fourI = 4 * i;
 			final double ei = work[(fourI + 2)];
```


---
## Patch 12 of bug id Math80
### Patch Diff Hash-SHA-256:

13995790ea607ff3de352d96b101018bac7eba6bc6a82c9b32eb2fab35339ccc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -717,6 +717,7 @@
 			}
 		}
 		lower = java.lang.Math.max(lower, (left - ((100 * (org.apache.commons.math.util.MathUtils.EPSILON)) * (java.lang.Math.abs(left)))));
+		pingPong = 1 - (pingPong);
 		left = lower - margin;
 		right = upper + margin;
 		for (int i = 0; i < maxIter; ++i) {
```


---
## Patch 13 of bug id Math80
### Patch Diff Hash-SHA-256:

3f0797eb48f29a15106c1caad9eb3374822b80bcbd37ba46b2078f0bcfbbb8d6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					cachedV = org.apache.commons.math.linear.MatrixUtils.createRealMatrix(n, n);
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 14 of bug id Math80
### Patch Diff Hash-SHA-256:

3c3c3168fecdcdc8b4818c6c548429fef1ab8124609969870115edaa0a8f740a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -678,7 +678,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					dMin1 = 0;
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 1 of bug id Math74
### Patch Diff Hash-SHA-256:

9d7e5ad75c19c4e91c90412ab28e4324d7e590ffd3354bd4a3b331f4775281d7

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -36,7 +36,7 @@
 		interpolator.reinitialize(stepStart, stepSize, scaled, nordsieck);
 		interpolator.storeTime(stepStart);
 		double hNew = stepSize;
-		interpolator.rescale(hNew);
+		setMaxGrowth(10.0);
 		boolean lastStep = false;
 		while (!lastStep) {
 			interpolator.shift();
```


---
## Patch 2 of bug id Math74
### Patch Diff Hash-SHA-256:

44935a0836f605bbf0f7765093098fe84f54a923942b6feeedc4b7bf2359c480

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -62,6 +62,7 @@
 					}
 					updateHighOrderDerivativesPhase2(predictedScaled, correctedScaled, nordsieckTmp);
 					interpolatorTmp.reinitialize(stepEnd, stepSize, correctedScaled, nordsieckTmp);
+					setMaxGrowth(10.0);
 					interpolatorTmp.storeTime(stepStart);
 					interpolatorTmp.shift();
 					interpolatorTmp.storeTime(stepEnd);
```


---
## Patch 3 of bug id Math74
### Patch Diff Hash-SHA-256:

b2637b4e5b1d87008bab2b1016421f0bccfa1b734e41385c4897396897e6a592

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -45,6 +45,7 @@
 				stepSize = hNew;
 				final double stepEnd = (stepStart) + (stepSize);
 				interpolator.setInterpolatedTime(stepEnd);
+				setMaxGrowth(10.0);
 				java.lang.System.arraycopy(interpolator.getInterpolatedState(), 0, yTmp, 0, y0.length);
 				computeDerivatives(stepEnd, yTmp, yDot);
 				final double[] predictedScaled = new double[y0.length];
```


---
## Patch 4 of bug id Math74
### Patch Diff Hash-SHA-256:

dc6aabf8b641977cc7340ab41a7b9d7ef84944cbe0b8dd844b73e3f61ea4948c

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -19,6 +19,7 @@
 		setEquations(equations);
 		resetEvaluations();
 		final boolean forward = t > t0;
+		setMaxGrowth(10.0);
 		if (y != y0) {
 			java.lang.System.arraycopy(y0, 0, y, 0, n);
 		}
```


---
## Patch 5 of bug id Math74
### Patch Diff Hash-SHA-256:

81c539ff9ba5ba7d2c1f0728f48482c5de634f92a3f93cbd41431a41a1ee0070

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -78,6 +78,7 @@
 						nordsieck = nordsieckTmp;
 						interpolator.reinitialize(stepEnd, stepSize, scaled, nordsieck);
 						loop = false;
+						setMaxGrowth(10.0);
 					}
 				}else {
 					final double factor = computeStepGrowShrinkFactor(error);
```


---
## Patch 1 of bug id Math81
### Patch Diff Hash-SHA-256:

a1bac6da6277eac3862ca9ba3585943010e166be1ec80625e40095fb7e0b8590

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,6 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```


---
## Patch 2 of bug id Math81
### Patch Diff Hash-SHA-256:

fa704148249c2ba531c772e90f5fdfb912ae6f5feaae16e71f16c7da77a56573

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -980,7 +980,7 @@
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
+						double b1 = (work[(nn - 5)]) / (work[(nn - 7)]);
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
```


---
## Patch 3 of bug id Math81
### Patch Diff Hash-SHA-256:

7c9bf63f19e6a233e952cfcf1563c4bd43e85685ee549ce13dad549642295b87

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							tType = -11;
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 4 of bug id Math81
### Patch Diff Hash-SHA-256:

d1152acedf25158cd3aa2a3f1661e4a938fec4f3ac15de669ed32574bab3b956

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,9 +970,6 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
-						}
 						tau = s;
 					}
 				}else
```


---
## Patch 5 of bug id Math81
### Patch Diff Hash-SHA-256:

04bc07560b29820d55e9621bab33badb6c7aadd91beb5005de3f8a111fed0198

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,24 +987,8 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
+						if ((dN) > b1) {
+							s = (dN) - b1;
 						}
 						if (a2 < cnst1) {
 							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
```


---
## Patch 6 of bug id Math81
### Patch Diff Hash-SHA-256:

8f183ba10883eba23e572a8f5ca24bfe118e8929f47b5898e40966cda2a83819

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							g = 0.0;
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```


---
## Patch 7 of bug id Math81
### Patch Diff Hash-SHA-256:

b3f81c3986637a6c3078abd1b91c2b756a0d9ee277849d9f2b191bba60b62d51

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -934,7 +934,6 @@
 						int np;
 						if ((dMin) == (dN)) {
 							gam = dN;
-							a2 = 0.0;
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
```


---
## Patch 8 of bug id Math81
### Patch Diff Hash-SHA-256:

c216568bb3d20e34e51a9dc8d38510eafc6fc9b7d48d594f3dc308340126996d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -934,7 +934,7 @@
 						int np;
 						if ((dMin) == (dN)) {
 							gam = dN;
-							a2 = 0.0;
+							eigenvectors = null;
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
```


---
## Patch 9 of bug id Math81
### Patch Diff Hash-SHA-256:

df196ef272f7b8725382e219f928db137b34d11ac04c8d8dd20f5901c9db9efd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							g = 0.0;
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 10 of bug id Math81
### Patch Diff Hash-SHA-256:

b5aeef64eb10174df00f2c6ad55b1609b225002adfbd6c09091212d49390cb7d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,6 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 11 of bug id Math81
### Patch Diff Hash-SHA-256:

2bb09c2865247c949bc659d01cfb684e35b97a518f13b937a315dc1aec98de92

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,25 +987,9 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
+						if ((work[(np - 4)]) > (work[(np - 2)])) {
 									return ;
 								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
-						}
 						if (a2 < cnst1) {
 							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}else {
```


---
## Patch 12 of bug id Math81
### Patch Diff Hash-SHA-256:

7c3126412ab6f308835f5a56b1c1b237a8ab74a9cff6eb6171a21a5f1df6e102

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,25 +987,9 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
 								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 									break;
 								}
-							}
-							a2 = cnst3 * a2;
-						}
 						if (a2 < cnst1) {
 							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}else {
```


---
## Patch 13 of bug id Math81
### Patch Diff Hash-SHA-256:

948563ddcb5522dfb9ceb5073d55b3668700ff2ba1fa02a3eb117f706dc939d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,25 +987,6 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
-						}
 						if (a2 < cnst1) {
 							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}else {
```


---
## Patch 14 of bug id Math81
### Patch Diff Hash-SHA-256:

a6df3df090006c18b2be0f2f20b0d814c3aa0692eb781de8c3f0eb88d55c1d2e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							tType = -5;
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 15 of bug id Math81
### Patch Diff Hash-SHA-256:

1d896ade94a96b08f0ac543fb50cb51585d886579e9245ce14f141ce79578728

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,42 +976,6 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
-						tType = -5;
-						double s = 0.25 * (dMin);
-						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
-						double b2 = work[(np - 6)];
-						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
-							return ;
-						}
-						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
-						}
-						if (a2 < cnst1) {
-							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
-						}else {
-							tau = s;
-						}
-					}else {
 						if ((tType) == (-6)) {
 							g += 0.333 * (1 - (g));
 						}else
@@ -1021,9 +985,6 @@
 								g = 0.25;
 							}
 						
-						tau = (g) * (dMin);
-						tType = -6;
-					}
 				
 				break;
 			case 1 :
```


---
## Patch 16 of bug id Math81
### Patch Diff Hash-SHA-256:

0b7c304f521778304eb76f897736fd5c65e19f303252db695243af8a653a4395

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							dMin1 = dMin;
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```


---
## Patch 17 of bug id Math81
### Patch Diff Hash-SHA-256:

b8ea6f4012c9729d568edc2059cdbbb065831e1a3d37d1178c77c3911e4dec20

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,8 +970,18 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+						if (b2 != 0.0) {
+							for (int i4 = ((4 * end) - 10) + (pingPong); i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
+								final double oldB1 = b1;
+								if ((work[i4]) > (work[(i4 - 2)])) {
+									return ;
+								}
+								b1 = b1 * ((work[i4]) / (work[(i4 - 2)]));
+								b2 = b2 + b1;
+								if ((100 * (java.lang.Math.max(b1, oldB1))) < b2) {
+									break;
+								}
+							}
 						}
 						tau = s;
 					}
```


---
## Patch 18 of bug id Math81
### Patch Diff Hash-SHA-256:

e1a975a785dbdcf95c87b41d9cd0e514cafa2abc1be7fca819937673f40c03b0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -934,7 +934,7 @@
 						int np;
 						if ((dMin) == (dN)) {
 							gam = dN;
-							a2 = 0.0;
+							gam = dN;
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
```


---
## Patch 19 of bug id Math81
### Patch Diff Hash-SHA-256:

9f75285aad99b21b2f60a9aa9d1e98ab00a19aa840ee5448f215b33602cd92d3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,25 +987,17 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
+						if ((tType) < (-22)) {
+							tau = 0.0;
+						}else
+							if ((dMin1) > 0.0) {
+								tau = ((tau) + (dMin)) * (1.0 - (2.0 * (org.apache.commons.math.util.MathUtils.EPSILON)));
+								tType -= 11;
+							}else {
+								tau *= 0.25;
+								tType -= 12;
 						}
+						
 						if (a2 < cnst1) {
 							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}else {
```


---
## Patch 20 of bug id Math81
### Patch Diff Hash-SHA-256:

d4c78acfa034526876d6d8dc2e2c38249af2072e1a17549588aaa295401c9647

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,6 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
 					}
```


---
## Patch 21 of bug id Math81
### Patch Diff Hash-SHA-256:

f4596c568a0b00d7d8d586826b2c6d02d213f7945d88f7d571b495535fafb1fc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,9 +970,15 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+						if ((tType) == (-6)) {
+							g += 0.333 * (1 - (g));
+						}else
+							if ((tType) == (-18)) {
+								g = 0.25 * 0.333;
+							}else {
+								g = 0.25;
 						}
+						
 						tau = s;
 					}
 				}else
```


---
## Patch 22 of bug id Math81
### Patch Diff Hash-SHA-256:

c286d9eb939c3d99d4fc8dbad4a9908f7627fc37361c936ff1a77bc93e4d1f0b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							gam = dN;
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 23 of bug id Math81
### Patch Diff Hash-SHA-256:

5daae86978d559b55d16a238cdbb67ceb14445de0efb7a0fed4c6801644064a7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							tType = -3;
 						}
 						tau = s;
 					}
```


---
## Patch 24 of bug id Math81
### Patch Diff Hash-SHA-256:

87f4e75d7d674188eca59309482a8a3e9fdeabf8dc6e0003b51234d218fa8e62

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							tau = -(dMin);
 						}
 						tau = s;
 					}
```


---
## Patch 25 of bug id Math81
### Patch Diff Hash-SHA-256:

1200f30e8984383bf2d73ec26e28dc3ec644fc28fa99244199b024c068592738

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							dMin = java.lang.Math.min(dMin, dN);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```


---
## Patch 26 of bug id Math81
### Patch Diff Hash-SHA-256:

1621c92a1988d2da1eb492e41a7894cdc31c2556e9169fc48888bbcc561b9ce4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -975,56 +975,8 @@
 						}
 						tau = s;
 					}
-				}else
-					if ((dMin) == (dN2)) {
-						tType = -5;
-						double s = 0.25 * (dMin);
-						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
-						double b2 = work[(np - 6)];
-						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
-							return ;
-						}
-						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
-						}
-						if (a2 < cnst1) {
-							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
-						}else {
-							tau = s;
-						}
-					}else {
-						if ((tType) == (-6)) {
-							g += 0.333 * (1 - (g));
-						}else
-							if ((tType) == (-18)) {
-								g = 0.25 * 0.333;
 							}else {
-								g = 0.25;
-							}
-						
-						tau = (g) * (dMin);
-						tType = -6;
 					}
-				
 				break;
 			case 1 :
 				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
```


---
## Patch 27 of bug id Math81
### Patch Diff Hash-SHA-256:

627bb09813b4e45badadecf9f491892bb8beef61e771cd61b98c0118f27896c5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,53 +976,12 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
-						tType = -5;
-						double s = 0.25 * (dMin);
-						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
-						double b2 = work[(np - 6)];
-						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
-							return ;
-						}
-						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
-						}
-						if (a2 < cnst1) {
-							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+					if ((dMin1) > 0.0) {
+						tau = ((tau) + (dMin)) * (1.0 - (2.0 * (org.apache.commons.math.util.MathUtils.EPSILON)));
+						tType -= 11;
 						}else {
-							tau = s;
-						}
-					}else {
-						if ((tType) == (-6)) {
-							g += 0.333 * (1 - (g));
-						}else
-							if ((tType) == (-18)) {
-								g = 0.25 * 0.333;
-							}else {
-								g = 0.25;
-							}
-						
-						tau = (g) * (dMin);
-						tType = -6;
+						tau *= 0.25;
+						tType -= 12;
 					}
 				
 				break;
```


---
## Patch 28 of bug id Math81
### Patch Diff Hash-SHA-256:

9ed1a555a1794a1c10c38a16a5454e39926bcfe7df2572fadca8df0972c16d32

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							org.apache.commons.math.linear.EigenDecompositionImpl.this.secondary = secondary.clone();
 						}
 						tau = s;
 					}
```


---
## Patch 29 of bug id Math81
### Patch Diff Hash-SHA-256:

6c6db26dca7a12fbd473da686a9022f931f3de14a362e044a00f96edbd294bef

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,24 +987,18 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
+						if (b2 != 0.0) {
+							for (int i4 = ((4 * end) - 10) + (pingPong); i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
+								final double oldB1 = b1;
 								if ((work[i4]) > (work[(i4 - 2)])) {
 									return ;
 								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
+								b1 = b1 * ((work[i4]) / (work[(i4 - 2)]));
+								b2 = b2 + b1;
+								if ((100 * (java.lang.Math.max(b1, oldB1))) < b2) {
 									break;
 								}
 							}
-							a2 = cnst3 * a2;
 						}
 						if (a2 < cnst1) {
 							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
```


---
## Patch 30 of bug id Math81
### Patch Diff Hash-SHA-256:

afca83a1f810588e73127eba563f438187ddd09f27fc43263bf0e83451b8adea

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							b2 = java.lang.Math.sqrt((cnst3 * b2));
 						}
 						tau = s;
 					}
```


---
## Patch 31 of bug id Math81
### Patch Diff Hash-SHA-256:

d707547b82e014c8919647108d1982d4cfb224e98b4b64d566d602929e5572e2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,8 +970,8 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+						if (a2 > (b1 + b2)) {
+							s = java.lang.Math.min(s, (a2 - (b1 + b2)));
 						}
 						tau = s;
 					}
```


---
## Patch 32 of bug id Math81
### Patch Diff Hash-SHA-256:

7a02cc6a774b01a2577d7efb41b5e9c8135c8dbe35e14d2762643c1ba8c3020b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,8 +970,8 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+						if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
+							break;
 						}
 						tau = s;
 					}
```


---
## Patch 33 of bug id Math81
### Patch Diff Hash-SHA-256:

7b0072384eb72e65a4aab5fd35c5ac7a7886e48c8a82b0e4aa571c5528e777ec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							dMin = -0.0;
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 34 of bug id Math81
### Patch Diff Hash-SHA-256:

f26c5e264e43e887dc28120374439073bf666ebefe7756fa8beaa0c8cb56b992

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							tau = java.lang.Math.max(s, (0.333 * (dMin)));
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```


---
## Patch 35 of bug id Math81
### Patch Diff Hash-SHA-256:

90511ff317a40be7ae9818b3a2a0f95b736717125fbf55932ed22063cf820938

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							dMin1 = dMin;
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 36 of bug id Math81
### Patch Diff Hash-SHA-256:

1effc93a616206d31cbe52e501a556eaef51a5b339b6d531f94f8960a6e17efa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -583,7 +583,7 @@
 	}
 
 	private int goodStep(final int start, final int end) {
-		g = 0.0;
+		dN2 = 0;
 		int deflatedEnd = end;
 		for (boolean deflating = true; deflating;) {
 			if (start >= deflatedEnd) {
```


---
## Patch 37 of bug id Math81
### Patch Diff Hash-SHA-256:

412dc32968aafe2aafcb84d386dace2e1a79d97e3a0ebc7132c4b7e35531e921

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,24 +987,8 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
-							a2 = a2 + b2;
-							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
-								if (b2 == 0.0) {
-									break;
-								}
-								b1 = b2;
-								if ((work[i4]) > (work[(i4 - 2)])) {
-									return ;
-								}
-								b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-								a2 = a2 + b2;
-								if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
-									break;
-								}
-							}
-							a2 = cnst3 * a2;
+						if (a2 > (b1 + b2)) {
+							s = java.lang.Math.min(s, (a2 - (b1 + b2)));
 						}
 						if (a2 < cnst1) {
 							tau = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
```


---
## Patch 1 of bug id Math53
### Patch Diff Hash-SHA-256:

7d729043bc11d24f3d80a6fe33c5bb3c5dcea7965b49275dfcea1eef2af2584e

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -55,6 +55,9 @@
 	}
 
 	public org.apache.commons.math.complex.Complex add(org.apache.commons.math.complex.Complex rhs) throws org.apache.commons.math.exception.NullArgumentException {
+		if ((isNaN) || (rhs.isNaN)) {
+			return org.apache.commons.math.complex.Complex.NaN;
+		}
 		org.apache.commons.math.util.MathUtils.checkNotNull(rhs);
 		return createComplex(((real) + (rhs.getReal())), ((imaginary) + (rhs.getImaginary())));
 	}
```


---
## Patch 2 of bug id Math53
### Patch Diff Hash-SHA-256:

9e4e10b0129d5e56b28ad4962e0c68a8e881cfe22d1c0bafb7d9ddae412e25d6

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -56,6 +56,9 @@
 
 	public org.apache.commons.math.complex.Complex add(org.apache.commons.math.complex.Complex rhs) throws org.apache.commons.math.exception.NullArgumentException {
 		org.apache.commons.math.util.MathUtils.checkNotNull(rhs);
+		if ((isNaN) || (rhs.isNaN)) {
+			return org.apache.commons.math.complex.Complex.NaN;
+		}
 		return createComplex(((real) + (rhs.getReal())), ((imaginary) + (rhs.getImaginary())));
 	}
```


---
## Patch 1 of bug id Math39
### Patch Diff Hash-SHA-256:

4cf1704a853cd8b3930a71489767a319d5a7dae05880d71cb603aa6a2abdc4ce

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/EmbeddedRungeKuttaIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/EmbeddedRungeKuttaIntegrator.java	
@@ -108,6 +108,9 @@
 						yTmp[j] = (y[j]) + ((stepSize) * sum);
 					}
 					computeDerivatives(((stepStart) + ((c[(k - 1)]) * (stepSize))), yTmp, yDotK[k]);
+					if ((forward && (((stepStart) + (stepSize)) > t)) || ((!forward) && (((stepStart) + (stepSize)) < t))) {
+						stepSize = t - (stepStart);
+					}
 				}
 				for (int j = 0; j < (y0.length); ++j) {
 					double sum = (b[0]) * (yDotK[0][j]);
```


---
## Patch 1 of bug id Math70
### Patch Diff Hash-SHA-256:

84237e6dc0bcc9350b34f559a6d849890f1e3dc578190bc2c8fdc892cd90ba49

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 2 of bug id Math70
### Patch Diff Hash-SHA-256:

4a055e5967b90b6f15f06c9ab75302d424717bf970dbaed957449bdb52637d20

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BisectionSolver.java	
@@ -24,7 +24,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max, double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		return solve(min, max);
+		return solve(f, min, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 1 of bug id Math84
### Patch Diff Hash-SHA-256:

11910d49650c4fafe58680b5770ce5911f336e4f55628d184dc4493e26e3779b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -37,6 +37,7 @@
 			if ((comparator.compare(contracted, best)) < 0) {
 				return ;
 			}
+			break;
 		} 
 	}
```


---
## Patch 2 of bug id Math84
### Patch Diff Hash-SHA-256:

908cd73d5b487afe1ffc2157c6c65a7006519be92610cc81f64b307816be9d5f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -37,6 +37,7 @@
 			if ((comparator.compare(contracted, best)) < 0) {
 				return ;
 			}
+			return ;
 		} 
 	}
```


---
## Patch 1 of bug id Math85
### Patch Diff Hash-SHA-256:

08afa6dd3983030516105e6aef7055875773cfca563a00da3505aad92b3ec375

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -47,7 +47,6 @@
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
 		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 2 of bug id Math85
### Patch Diff Hash-SHA-256:

bee6f38e123be7db2428f846afae914b1857229aab097c82a6b3e62ef2251981

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,8 +46,8 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
+		if (((initial < lowerBound) || (initial > upperBound)) || (lowerBound >= upperBound)) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("invalid bracketing parameters:  lower bound={0},  initial={1}, upper bound={2}", lowerBound, initial, upperBound);
 		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 3 of bug id Math85
### Patch Diff Hash-SHA-256:

ffd22459d5e35c6ae18c95157d34279d57a91c499ad1900a7f548340a47d9d68

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,9 +46,6 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
-		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 4 of bug id Math85
### Patch Diff Hash-SHA-256:

fec7b1dd59d10094026d94e252c2e102c7e8e2118f55f4561a59ee8d5264cf5e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,8 +46,8 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
+		if (maximumIterations <= 0) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("bad value for maximum iterations number: {0}", maximumIterations);
 		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 5 of bug id Math85
### Patch Diff Hash-SHA-256:

0a66163b1d904a32de72089a1bb391e15166a8649f5336248170bf35d7cd60a6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,8 +46,8 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
+		if (function == null) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("function is null");
 		}
 		return new double[]{ a , b };
 	}
```


---
## Patch 1 of bug id Math71
### Patch Diff Hash-SHA-256:

6fd3b56ad870203ac3e4947d92a8fdf040b35bf53cf832676b470b0755528a32

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -80,6 +80,9 @@
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
 				final double gb = handler.g(tb, interpolator.getInterpolatedState());
+				if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
+					return false;
+				}
 				if ((g0Positive) ^ (gb >= 0)) {
 					if ((ga * gb) > 0) {
 						final double epsilon = (forward ? 0.25 : -0.25) * (convergence);
```


---
## Patch 2 of bug id Math71
### Patch Diff Hash-SHA-256:

95b9aeafe336253e5e5b3bf601bb232441a7b5e69d24646fc2b353ee8fe07515

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -93,6 +93,7 @@
 						}
 					}
 					increasing = gb >= ga;
+					pendingEvent = true;
 					final org.apache.commons.math.analysis.UnivariateRealFunction f = new org.apache.commons.math.analysis.UnivariateRealFunction() {
 						public double value(final double t) throws org.apache.commons.math.FunctionEvaluationException {
 							try {
```


---
## Patch 3 of bug id Math71
### Patch Diff Hash-SHA-256:

86917fc8afb925d331e5c1f6c8f3c758abd8ed61b3c2e409ba004d83e5c710c0

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -72,6 +72,7 @@
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			pendingEvent = true;
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```


---
## Patch 4 of bug id Math71
### Patch Diff Hash-SHA-256:

a2acc33707c1edd61ed28a2f886529e52f280b6677e7d606cab293b0f9e11eb8

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,6 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
+			pendingEvent = true;
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
```


---
## Patch 5 of bug id Math71
### Patch Diff Hash-SHA-256:

161877ad531298f0ec12b4b3ac6ef3b8a7719971fece3b1e2638a6ac79997cf5

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -109,6 +109,9 @@
 					solver.setAbsoluteAccuracy(convergence);
 					solver.setMaximalIterationCount(maxIterationCount);
 					final double root = ta <= tb ? solver.solve(f, ta, tb) : solver.solve(f, tb, ta);
+					if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
+						return false;
+					}
 					if (((java.lang.Math.abs((root - ta))) <= (convergence)) && ((java.lang.Math.abs((root - (previousEventTime)))) <= (convergence))) {
 						ta = tb;
 						ga = gb;
```


---
## Patch 6 of bug id Math71
### Patch Diff Hash-SHA-256:

19a2db8c937466a2544a8f442fb4fca284c4c6fb2869acec388da693262a714d

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -75,6 +75,7 @@
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
+			pendingEvent = true;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
 			for (int i = 0; i < n; ++i) {
 				tb += h;
```


---
## Patch 7 of bug id Math71
### Patch Diff Hash-SHA-256:

c38c38cd1b2222fbd276db68aaf60d8dc582c2a91bba6169d9e7a01af8ca2823

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -112,7 +112,10 @@
 					if (((java.lang.Math.abs((root - ta))) <= (convergence)) && ((java.lang.Math.abs((root - (previousEventTime)))) <= (convergence))) {
 						ta = tb;
 						ga = gb;
-					}else
+					}else {
+						if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
+							return false;
+						}
 						if ((java.lang.Double.isNaN(previousEventTime)) || ((java.lang.Math.abs(((previousEventTime) - root))) > (convergence))) {
 							pendingEventTime = root;
 							if ((pendingEvent) && ((java.lang.Math.abs((t1 - (pendingEventTime)))) <= (convergence))) {
@@ -121,7 +124,7 @@
 							pendingEvent = true;
 							return true;
 						}
-					
+					}
 				}else {
 					ta = tb;
 					ga = gb;
```


---
## Patch 1 of bug id Math82
### Patch Diff Hash-SHA-256:

22a211091f9029d0f86f2ce242b01a68320675ddd795973d1cca0568c49af573

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -20,10 +20,9 @@
 		double minValue = 0;
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
-			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0)
 				minPos = i;
-			}
+			
 		}
 		return minPos;
 	}
```


---
## Patch 1 of bug id Math49
### Patch Diff Hash-SHA-256:

ef67153ab8a5618e4fb8f920af151ac6f3899b88f924f81a7a3a09145172ca53

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -223,7 +223,6 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
 		return previous;
 	}
```


---
## Patch 2 of bug id Math49
### Patch Diff Hash-SHA-256:

9c6cb84af8a7e0ae8a0a894856c8fce54573851a9499ccc0fb606d573a288687

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -470,7 +470,7 @@
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
-				entries.remove(index);
+				entries.put(index, value);
 			}
 		
 	}
```


---
## Patch 3 of bug id Math49
### Patch Diff Hash-SHA-256:

c7ca96e91f0b9036105508f4e9327cd67c30f8f013bb55d4da2116f9bca46519

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -196,6 +196,7 @@
 	public double remove(final int key) {
 		final int hash = org.apache.commons.math.util.OpenIntToDoubleHashMap.hashOf(key);
 		int index = hash & (mask);
+		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		if (containsKey(key, index)) {
 			return doRemove(index);
 		}
```


---
## Patch 4 of bug id Math49
### Patch Diff Hash-SHA-256:

d95b6c56c9fb66876fdc6548ecba63d4782e62b37ece10215962edde9324b18c

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -220,6 +220,7 @@
 	private double doRemove(int index) {
 		keys[index] = 0;
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
+		int count = 1;
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
```


---
## Patch 5 of bug id Math49
### Patch Diff Hash-SHA-256:

18a7df84cd9c925a5af217108d6bf5167425e275a1fbfcbe89a8bf05e0320d1f

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -220,6 +220,7 @@
 	private double doRemove(int index) {
 		keys[index] = 0;
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
+		int count = 0;
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
```


---
## Patch 6 of bug id Math49
### Patch Diff Hash-SHA-256:

aeffbecaa2ed75f8b92b473752a4fa3ef1134cf066ac4c732c53e6abb3b675ed

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -222,6 +222,7 @@
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		final double previous = values[index];
 		values[index] = missingEntries;
+		int count = 0;
 		--(size);
 		++(count);
 		return previous;
```


---
## Patch 7 of bug id Math49
### Patch Diff Hash-SHA-256:

8faee62433f22224c415e7b84ffbec70c305f0d00eba3ce81354741040c7f866

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -222,6 +222,7 @@
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		final double previous = values[index];
 		values[index] = missingEntries;
+		int count = 1;
 		--(size);
 		++(count);
 		return previous;
```


---
## Patch 8 of bug id Math49
### Patch Diff Hash-SHA-256:

06cc04624ac7ff97e8bc22cacd9b206739f27364f69ac97642c87205f4ca5e9c

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -221,6 +221,7 @@
 		keys[index] = 0;
 		states[index] = org.apache.commons.math.util.OpenIntToDoubleHashMap.REMOVED;
 		final double previous = values[index];
+		int count = 0;
 		values[index] = missingEntries;
 		--(size);
 		++(count);
```


---
## Patch 1 of bug id Math78
### Patch Diff Hash-SHA-256:

d82cd2aacb90b7c92b3de99926d90530d781506cd4a1f5a31d99dbdea69a7339

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -71,6 +71,7 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
+			final double t0 = interpolator.getPreviousTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
```


---
## Patch 2 of bug id Math78
### Patch Diff Hash-SHA-256:

6a834048d1cc66e056c6ecc1f7c0b875e6669f0650045397cc8543bd77c5232d

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -70,6 +70,7 @@
 	public boolean evaluateStep(final org.apache.commons.math.ode.sampling.StepInterpolator interpolator) throws org.apache.commons.math.ConvergenceException, org.apache.commons.math.ode.DerivativeException, org.apache.commons.math.ode.events.EventException {
 		try {
 			forward = interpolator.isForward();
+			final double t0 = interpolator.getPreviousTime();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
```


---
## Patch 3 of bug id Math78
### Patch Diff Hash-SHA-256:

75f4b24af1d4e591072a972990fa71be4b4fe63e17fc64a7512a2e8c6d96d4b6

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -77,6 +77,7 @@
 			double ga = g0;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
 			for (int i = 0; i < n; ++i) {
+				ta = tb;
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
 				final double gb = handler.g(tb, interpolator.getInterpolatedState());
```


---
## Patch 4 of bug id Math78
### Patch Diff Hash-SHA-256:

f4e2c5dfe9995807cd70b63ccf034dc4ced72130431f83fef243b269893b79e1

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -73,6 +73,7 @@
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
 			final double h = (t1 - (t0)) / n;
+			final double t0 = interpolator.getPreviousTime();
 			double ta = t0;
 			double ga = g0;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
```


---
## Patch 5 of bug id Math78
### Patch Diff Hash-SHA-256:

055000c32bd3c0a225ab04bffdd554831a7ccf2fa659778d7b3d46766e559034

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -72,6 +72,7 @@
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
+			final double t0 = interpolator.getPreviousTime();
 			final double h = (t1 - (t0)) / n;
 			double ta = t0;
 			double ga = g0;
```


---
## Patch 6 of bug id Math78
### Patch Diff Hash-SHA-256:

a0ca07e4f7e62ec66974ec3abf78efebc8220ce610e19d49507c18aacc501d9b

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -69,6 +69,7 @@
 
 	public boolean evaluateStep(final org.apache.commons.math.ode.sampling.StepInterpolator interpolator) throws org.apache.commons.math.ConvergenceException, org.apache.commons.math.ode.DerivativeException, org.apache.commons.math.ode.events.EventException {
 		try {
+			final double t0 = interpolator.getPreviousTime();
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
 			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
```


---
## Patch 7 of bug id Math78
### Patch Diff Hash-SHA-256:

a45ed2d440f50621e71e5f0ed2689e1c10bea10bc6d7fd2983f2802a138039d2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -155,6 +155,7 @@
 				x2 = x0;
 				y2 = y0;
 				delta = x1 - x0;
+				delta = 0.5 * oldDelta;
 				oldDelta = delta;
 			}
 			i++;
```


---
## Patch 8 of bug id Math78
### Patch Diff Hash-SHA-256:

392367a8a7c0bda67202fb47c9effd3be699b56d1beaef35357b4e56b719b498

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -76,6 +76,7 @@
 			double ta = t0;
 			double ga = g0;
 			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
+			ta = tb;
 			for (int i = 0; i < n; ++i) {
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
```


---
## Patch 9 of bug id Math78
### Patch Diff Hash-SHA-256:

5580ffc13a373e0f907695693604f59311a13d9d87f9dd8a9c6cf2377a2ea910

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -154,7 +154,7 @@
 			if ((y1 > 0) == (y2 > 0)) {
 				x2 = x0;
 				y2 = y0;
-				delta = x1 - x0;
+				delta = 0.5 * oldDelta;
 				oldDelta = delta;
 			}
 			i++;
```


---
## Patch 1 of bug id Math56
### Patch Diff Hash-SHA-256:

4e48f676c913f47c8f00fbe1bd698915df01ada76cb19b6c68966919f951efb7

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MultidimensionalCounter.java	
+++ /fixed/org/apache/commons/math/util/MultidimensionalCounter.java	
@@ -110,6 +110,10 @@
 		int idx = 1;
 		while (count < index) {
 			count += idx;
+			while (count < index) {
+				count += idx;
+				++idx;
+			} 
 			++idx;
 		} 
 		--idx;
```


---
## Patch 1 of bug id Math32
### Patch Diff Hash-SHA-256:

dd6f0404fbc1e20c403ebee64a203e833454c9a81c0d9c1a759d742068ec651c

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/partitioning/AbstractRegion.java	
+++ /fixed/org/apache/commons/math3/geometry/partitioning/AbstractRegion.java	
@@ -151,6 +151,7 @@
 			if (plusChar.hasOut()) {
 				final org.apache.commons.math3.geometry.partitioning.Characterization<S> minusChar = new org.apache.commons.math3.geometry.partitioning.Characterization<S>();
 				characterize(node.getMinus(), plusChar.getOut(), minusChar);
+				characterize(node.getMinus(), plusChar.getOut(), minusChar);
 				if (minusChar.hasIn()) {
 					plusOutside = minusChar.getIn();
 				}
```


---
## Patch 2 of bug id Math32
### Patch Diff Hash-SHA-256:

6604dd96ade105b23fa7f269bb42e62e232ce85fa43c23de0785e4f18b091671

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
+++ /fixed/org/apache/commons/math3/geometry/euclidean/threed/Vector3D.java	
@@ -162,7 +162,7 @@
 			return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(0, (inverse * (z)), ((-inverse) * (y)));
 		}else
 			if (((y) >= (-threshold)) && ((y) <= threshold)) {
-				double inverse = 1 / (org.apache.commons.math3.util.FastMath.sqrt((((x) * (x)) + ((z) * (z)))));
+				double inverse = 1 / (org.apache.commons.math3.util.FastMath.sqrt((((x) * (x)) + ((y) * (y)))));
 				return new org.apache.commons.math3.geometry.euclidean.threed.Vector3D(((-inverse) * (z)), 0, (inverse * (x)));
 			}
```


---
## Patch 1 of bug id Math20
### Patch Diff Hash-SHA-256:

1aa02b21a75b80de3c374b55282d79b62aba3fd5d6b232f9cab9adda82ae1fe1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -586,7 +586,7 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
+						valueRange = 1.0;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 2 of bug id Math20
### Patch Diff Hash-SHA-256:

a9285df7dab28cabd461b4ecb352b545fe2be1c86cfe55ffade664837101afab

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -586,7 +586,7 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
+						isRepairMode = true;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 3 of bug id Math20
### Patch Diff Hash-SHA-256:

d66f763e14c6a4aa1dbcddbacc9e26d2e16ef497135e1ecc662f38377c22626d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -586,7 +586,6 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 4 of bug id Math20
### Patch Diff Hash-SHA-256:

b08a5a42691215b624be16ad66c131fd10ead83a9f56a35e5bd087e625b1af76

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -528,7 +528,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				valueRange = 1.0;
 			}
 			return res;
 		}
```


---
## Patch 5 of bug id Math20
### Patch Diff Hash-SHA-256:

460078027c14af99b1207a95f99992bcba500931c5f54a54f1a41cffe5eb31fb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -526,10 +526,6 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
-				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
-			}
 			return res;
 		}
```


---
## Patch 1 of bug id Math28
### Patch Diff Hash-SHA-256:

507361f278146e2ab5e228c7d3aa253c601bc56b1ae05a65814e2c26b474b5bb

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -59,13 +59,6 @@
 		}else
 			if ((minRatioPositions.size()) > 1) {
 				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
-						}
-					}
 				}
 				java.lang.Integer minRow = null;
 				int minIndex = tableau.getWidth();
```


---
## Patch 2 of bug id Math28
### Patch Diff Hash-SHA-256:

e2abbecb9621b20ee286c2d35602097b08aba454e0ca3ceb50cb4123f7c57862

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -80,7 +80,7 @@
 						}
 					}
 				}
-				return minRow;
+				return minRatioPositions.get(0);
 			}
 		
 		return minRatioPositions.get(0);
```


---
## Patch 3 of bug id Math28
### Patch Diff Hash-SHA-256:

ff1791318d4897b6d46123c220fb81ddcf9be77a40bdab59a94b60dabd71ea7c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -74,7 +74,7 @@
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
 							if (i < minIndex) {
-								minIndex = i;
+								minRatioPositions = new java.util.ArrayList<java.lang.Integer>();
 								minRow = row;
 							}
 						}
```


---
## Patch 4 of bug id Math28
### Patch Diff Hash-SHA-256:

bf52f162192c8ec6d664201a7f69a18b69b84e2e3e8a3166e88f315e8e89edac

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -56,33 +56,8 @@
 		}
 		if ((minRatioPositions.size()) == 0) {
 			return null;
-		}else
-			if ((minRatioPositions.size()) > 1) {
-				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
+		}else {
 						}
-					}
-				}
-				java.lang.Integer minRow = null;
-				int minIndex = tableau.getWidth();
-				for (java.lang.Integer row : minRatioPositions) {
-					int i = tableau.getNumObjectiveFunctions();
-					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
-						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
-								minIndex = i;
-								minRow = row;
-							}
-						}
-					}
-				}
-				return minRow;
-			}
-		
 		return minRatioPositions.get(0);
 	}
```


---
## Patch 5 of bug id Math28
### Patch Diff Hash-SHA-256:

4fa7364586c371b4d328242d79d474a85a5d092f945710d60a62df1b638074d4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,7 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
+					setMaxIterations(org.apache.commons.math3.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```


---
## Patch 6 of bug id Math28
### Patch Diff Hash-SHA-256:

6e733bcbe1e1c6e2ffae2c42448cf5bffb5a64d335d9b5de192db37f3d391b01

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -58,15 +58,6 @@
 			return null;
 		}else
 			if ((minRatioPositions.size()) > 1) {
-				for (java.lang.Integer row : minRatioPositions) {
-					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
-						int column = i + (tableau.getArtificialVariableOffset());
-						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
-						}
-					}
-				}
 				java.lang.Integer minRow = null;
 				int minIndex = tableau.getWidth();
 				for (java.lang.Integer row : minRatioPositions) {
```


---
## Patch 7 of bug id Math28
### Patch Diff Hash-SHA-256:

d166467c83b4ff8e26f8310e2b075bfc23875d034d736d969186bfc9c420dc8c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -26,10 +26,9 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			final double entry = tableau.getEntry(0, i);
-			if (entry < minValue) {
-				minValue = entry;
+			if (entry < minValue)
 				minPos = i;
-			}
+			
 		}
 		return minPos;
 	}
```


---
## Patch 8 of bug id Math28
### Patch Diff Hash-SHA-256:

21a3b3753ca3273af618a21ad4c27e99893e9e87730c4bb5cad2b75ce0a70cf5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -44,7 +44,6 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```


---
## Patch 9 of bug id Math28
### Patch Diff Hash-SHA-256:

1b92de9ebd2f1b04f61428a53de0a744607262cd0b46c8e3c15341c0782191a1

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -73,10 +73,9 @@
 					int i = tableau.getNumObjectiveFunctions();
 					for (; (i < ((tableau.getWidth()) - 1)) && (minRow != row); i++) {
 						if (row == (tableau.getBasicRow(i))) {
-							if (i < minIndex) {
-								minIndex = i;
+							if (i < minIndex)
 								minRow = row;
-							}
+							
 						}
 					}
 				}
```


---
## Patch 10 of bug id Math28
### Patch Diff Hash-SHA-256:

8eea2eabc32d443ec60c9e2796b9252b78daaefba92acb768475c8f6a1618fa7

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -80,7 +80,6 @@
 						}
 					}
 				}
-				return minRow;
 			}
 		
 		return minRatioPositions.get(0);
```


---
## Patch 11 of bug id Math28
### Patch Diff Hash-SHA-256:

014ae56c12ce25b9abe5c4324f7f1912fcaca8c4a7d6ffae9189c44bb1a3861c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -63,7 +63,6 @@
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
 						}
 					}
 				}
```


---
## Patch 1 of bug id Math8
### Patch Diff Hash-SHA-256:

c2a62f636361bfeb7c6add9f084790d1addf32a1e32667167caddddd2411af9d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,9 +68,6 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
-		}
 		return out;
 	}
 }
```


---
## Patch 2 of bug id Math8
### Patch Diff Hash-SHA-256:

cf6e0a4996f72a7bfd9bbc0f7499576e89634309fc8094cb86c4ab8f95a91c3c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -69,7 +69,6 @@
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
 		}
 		return out;
 	}
```


---
## Patch 1 of bug id Math40
### Patch Diff Hash-SHA-256:

4f2a2364cb5c4743ccfbf64dc7648761c5bd94f4b0856c8674b21211e1e9c674

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -147,7 +147,7 @@
 			}
 			if ((nbPoints > 2) && ((end - start) != nbPoints)) {
 				nbPoints = end - start;
-				java.lang.System.arraycopy(x, start, x, 0, nbPoints);
+				java.lang.System.arraycopy(x, 1, x, 0, nbPoints);
 				java.lang.System.arraycopy(y, start, y, 0, nbPoints);
 				signChangeIndex -= start;
 			}else
```


---
## Patch 2 of bug id Math40
### Patch Diff Hash-SHA-256:

8e49644c4c1006b80d06cfcb6b7f7a914e0a59d103e2b0edca4b6648545a07e1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -131,7 +131,7 @@
 					if ((signChangeIndex - start) >= (end - signChangeIndex)) {
 						++start;
 					}else {
-						--end;
+						signChangeIndex++;
 					}
 					nextX = java.lang.Double.NaN;
 				}
```


---
## Patch 3 of bug id Math40
### Patch Diff Hash-SHA-256:

559376e939e1e3732effe2407955ef06f1e56f87f52dc834365de5db973f20cb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BracketingNthOrderBrentSolver.java	
@@ -118,6 +118,7 @@
 				if (agingB >= (org.apache.commons.math.analysis.solvers.BracketingNthOrderBrentSolver.MAXIMAL_AGING)) {
 					targetY = (-(org.apache.commons.math.analysis.solvers.BracketingNthOrderBrentSolver.REDUCTION_FACTOR)) * yA;
 				}else {
+					signChangeIndex = 2;
 					targetY = 0;
 				}
```


---
## Patch 1 of bug id Math7
### Patch Diff Hash-SHA-256:

beae7fe5596ec4e267f1d6dbe1acc4d7b21a023c8dba53fb375c67325e270fd0

### Patch Diff:
```
--- /original/org/apache/commons/math3/ode/AbstractIntegrator.java	
+++ /fixed/org/apache/commons/math3/ode/AbstractIntegrator.java	
@@ -45,6 +45,7 @@
 	}
 
 	public void addStepHandler(final org.apache.commons.math3.ode.sampling.StepHandler handler) {
+		eventsStates = new java.util.ArrayList<org.apache.commons.math3.ode.events.EventState>();
 		stepHandlers.add(handler);
 	}
```


---
## Patch 1 of bug id Math2
### Patch Diff Hash-SHA-256:

496a52808bcd2658e1f42bcc8414ab26464c689cb62e6c7e75f81e5395bb1b9f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -58,7 +58,6 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 2 of bug id Math2
### Patch Diff Hash-SHA-256:

41a93e73b2bf5c74b7ec735e0ece931e7b8363a57b2c678c931123d8bfdbfca6

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,18 +49,6 @@
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
-		if (chebyshevApplies) {
-			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
-			double tmp = mu - (k * sigma);
-			if (tmp > lower) {
-				lower = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-			k = 1.0 / k;
-			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 3 of bug id Math2
### Patch Diff Hash-SHA-256:

ed40558a844b3e8b3d0198d2433f742c79b87511694b7e5dd251cf6648a8513a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
-		if (chebyshevApplies) {
-			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
-			double tmp = mu - (k * sigma);
-			if (tmp > lower) {
-				lower = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-			k = 1.0 / k;
-			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
+		if (p == 1.0) {
+			return upper;
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 4 of bug id Math2
### Patch Diff Hash-SHA-256:

38f03d87c5cda18bdcf2e6fbccede66b6b6481c42362766937602282316e8fe1

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,8 +57,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (p == 0.0) {
+				return lower;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 5 of bug id Math2
### Patch Diff Hash-SHA-256:

a4446d0ee15926cb21f3f2955513748447a144cbda0a15e1f34e901bddc4e0fc

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,8 +57,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (java.lang.Double.isInfinite(p)) {
+				throw new org.apache.commons.math3.exception.NotFiniteNumberException(p);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 6 of bug id Math2
### Patch Diff Hash-SHA-256:

a1760e800c73de211b8cbd8712e0ee285c3e8e3edc34c2b100ffb431e4b48ff0

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
-		if (chebyshevApplies) {
-			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
-			double tmp = mu - (k * sigma);
-			if (tmp > lower) {
-				lower = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-			k = 1.0 / k;
-			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
+		if (p == 0.0) {
+			return lower;
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 7 of bug id Math2
### Patch Diff Hash-SHA-256:

daffc27a408c795e67763d543fd069176312c3d14b743583eadb39fc3fdb0ab8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -57,9 +57,6 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 8 of bug id Math2
### Patch Diff Hash-SHA-256:

ea17bd4da9a1037b321fd38b060be14de8da5197fa7f94025b90c53340d1cd6c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
-		if (chebyshevApplies) {
-			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
-			double tmp = mu - (k * sigma);
-			if (tmp > lower) {
-				lower = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-			k = 1.0 / k;
-			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
+		if (java.lang.Double.isNaN(p)) {
+			throw new org.apache.commons.math3.exception.NotANumberException();
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 9 of bug id Math2
### Patch Diff Hash-SHA-256:

3fe3e61efb9f80ccabbb9a5aba12c4d32bf3b9ad067af3866f3e3dcfd9744051

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
-		if (chebyshevApplies) {
-			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
-			double tmp = mu - (k * sigma);
-			if (tmp > lower) {
-				lower = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-			k = 1.0 / k;
-			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
+		if (java.lang.Double.isInfinite(p)) {
+			throw new org.apache.commons.math3.exception.NotFiniteNumberException(p);
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 10 of bug id Math2
### Patch Diff Hash-SHA-256:

9a679ee964b5fc58bb69603c2994452601da0120cb32fef051bd651b5e80b363

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -49,17 +49,8 @@
 		final double mu = getNumericalMean();
 		final double sigma = org.apache.commons.math3.util.FastMath.sqrt(getNumericalVariance());
 		final boolean chebyshevApplies = !(((((java.lang.Double.isInfinite(mu)) || (java.lang.Double.isNaN(mu))) || (java.lang.Double.isInfinite(sigma))) || (java.lang.Double.isNaN(sigma))) || (sigma == 0.0));
-		if (chebyshevApplies) {
-			double k = org.apache.commons.math3.util.FastMath.sqrt(((1.0 - p) / p));
-			double tmp = mu - (k * sigma);
-			if (tmp > lower) {
-				lower = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
-			k = 1.0 / k;
-			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
-			}
+		if ((p < 0) || (p > 1)) {
+			throw new org.apache.commons.math3.exception.OutOfRangeException(p, 0, 1);
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 11 of bug id Math2
### Patch Diff Hash-SHA-256:

ceae2e4a2e181de9f1af349aea59bd2ff4f7c99c247caac9545cc16ec41d8d81

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -58,7 +58,7 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+				tmp = mu + (k * sigma);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 1 of bug id Math5
### Patch Diff Hash-SHA-256:

1546323dccdd64f7e5c29590eea17a01e4dd162dabcf556fa983d966a49c858b

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -121,7 +121,7 @@
 			return org.apache.commons.math3.complex.Complex.NaN;
 		}
 		if (((real) == 0.0) && ((imaginary) == 0.0)) {
-			return org.apache.commons.math3.complex.Complex.NaN;
+			return org.apache.commons.math3.complex.Complex.INF;
 		}
 		if (isInfinite) {
 			return org.apache.commons.math3.complex.Complex.ZERO;
```


---