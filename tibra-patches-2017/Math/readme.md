
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
## Patch 1 of bug id Math50
### Patch Diff Hash-SHA-256:

5a0ab0ae89347985e62225e4616b3a8c512fdf98c24dab0376499b3170b8f366

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -78,10 +78,9 @@
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

c6c3ed541f2a4491f9ceb32eb418ca87eb352ca38bea028a4d22c4bd8a683681

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							incrementEvaluationCount();
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 3 of bug id Math50
### Patch Diff Hash-SHA-256:

e86fb5c217e3fa3dcc912105426f727e3e5087fdf65b295c4f2b743573a432f7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							x1 = 0;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 4 of bug id Math50
### Patch Diff Hash-SHA-256:

88787cdb3caa1e0cba475c273001e6b136069617f7b74123732ddf6e753de781

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f1 = ftol / fx;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 5 of bug id Math50
### Patch Diff Hash-SHA-256:

fa3641b1a23c28917175f38ba5cffd54ab04c678da47b74ef41b5a42b529c71d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -80,6 +80,7 @@
 					case REGULA_FALSI :
 						if (x == x1) {
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							double ym = computeObjectiveValue(f0);
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 6 of bug id Math50
### Patch Diff Hash-SHA-256:

e93acea9fe2b2a49692f830ccbab73ee94eef396bf8c95b9799470955d2c2d40

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,6 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
+							double y1 = computeObjectiveValue(x1);
 							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
 							f0 = computeObjectiveValue(x0);
 						}
```


---
## Patch 7 of bug id Math50
### Patch Diff Hash-SHA-256:

0dbfc0f06d4613ab1a09548acfc57679ddeb9cd2f8c1a20328bfcaaae17dae1f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BaseSecantSolver.java	
@@ -79,7 +79,7 @@
 						break;
 					case REGULA_FALSI :
 						if (x == x1) {
-							x0 = 0.5 * ((x0 + x1) - (org.apache.commons.math.util.FastMath.max((rtol * (org.apache.commons.math.util.FastMath.abs(x1))), atol)));
+							f1 = f1;
 							f0 = computeObjectiveValue(x0);
 						}
 						break;
```


---
## Patch 1 of bug id Math32
### Patch Diff Hash-SHA-256:

c73c2ebbff35c2e4b56eeff94a4a9a61ded043aeb48e31a1c112757daf090884

### Patch Diff:
```
--- /original/org/apache/commons/math3/geometry/partitioning/BSPTree.java	
+++ /fixed/org/apache/commons/math3/geometry/partitioning/BSPTree.java	
@@ -57,6 +57,7 @@
 		cut = chopped;
 		plus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>();
 		plus.parent = this;
+		cut = cut.reunite(chopped);
 		minus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>();
 		minus.parent = this;
 		return true;
@@ -227,11 +228,11 @@
 				{
 					final org.apache.commons.math3.geometry.partitioning.BSPTree<S> split = minus.split(sub);
 					if ((cut.side(sHyperplane)) == (org.apache.commons.math3.geometry.partitioning.Side.PLUS)) {
-						split.plus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.plus, attribute);
+						split.plus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.plus, this.attribute);
 						split.plus.condense();
 						split.plus.parent = split;
 					}else {
-						split.minus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.minus, attribute);
+						split.minus = new org.apache.commons.math3.geometry.partitioning.BSPTree<S>(cut.copySelf(), plus.copySelf(), split.minus, this.attribute);
 						split.minus.condense();
 						split.minus.parent = split;
 					}
```


---
## Patch 1 of bug id Math20
### Patch Diff Hash-SHA-256:

a8e260ebe0f2ddb52e917dfb78557624f64325cebc2fd337b5fee61c2cf296dd

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -49,10 +49,6 @@
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
## Patch 2 of bug id Math20
### Patch Diff Hash-SHA-256:

9bb67e48e18bbc76e68c5939374f86e85cd0ad0ac3e5734676ca00db3dd6d9b4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -109,7 +109,7 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
+						valueRange = valueRange;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 3 of bug id Math20
### Patch Diff Hash-SHA-256:

8403e49d48aac10a6b37ade34b7b55c9be23de630098ea5843a6410af41a8e20

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -49,10 +49,6 @@
 				return x;
 			}
 			double[] res = new double[x.length];
-			for (int i = 0; i < (x.length); i++) {
-				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
-			}
 			return res;
 		}
 
@@ -526,7 +522,7 @@
 			double oldFac = (hsig) ? 0 : ((ccov1) * (cc)) * (2.0 - (cc));
 			oldFac += (1.0 - (ccov1)) - (ccovmu);
 			if (isActiveCMA) {
-				negccov = (((1.0 - (ccovmu)) * 0.25) * (mueff)) / ((java.lang.Math.pow(((dimension) + 2.0), 1.5)) + (2.0 * (mueff)));
+				negccov = (((1.0 - (ccovmu)) * 0.25) * (mueff)) / ((java.lang.Math.pow(((this.dimension) + 2.0), 1.5)) + (2.0 * (mueff)));
 				double negminresidualvariance = 0.66;
 				double negalphaold = 0.5;
 				int[] arReverseIndex = org.apache.commons.math3.optimization.direct.CMAESOptimizer.reverse(arindex);
@@ -543,13 +539,13 @@
 				if (negccov > negcovMax) {
 					negccov = negcovMax;
 				}
-				arzneg = org.apache.commons.math3.optimization.direct.CMAESOptimizer.times(arzneg, org.apache.commons.math3.optimization.direct.CMAESOptimizer.repmat(arnormsInv, dimension, 1));
+				arzneg = org.apache.commons.math3.optimization.direct.CMAESOptimizer.times(arzneg, org.apache.commons.math3.optimization.direct.CMAESOptimizer.repmat(arnormsInv, this.dimension, 1));
 				org.apache.commons.math3.linear.RealMatrix artmp = BD.multiply(arzneg);
 				org.apache.commons.math3.linear.RealMatrix Cneg = artmp.multiply(org.apache.commons.math3.optimization.direct.CMAESOptimizer.diag(weights)).multiply(artmp.transpose());
 				oldFac += negalphaold * negccov;
-				C = C.scalarMultiply(oldFac).add(roneu).add(arpos.scalarMultiply(((ccovmu) + ((1.0 - negalphaold) * negccov))).multiply(org.apache.commons.math3.optimization.direct.CMAESOptimizer.times(org.apache.commons.math3.optimization.direct.CMAESOptimizer.repmat(weights, 1, dimension), arpos.transpose()))).subtract(Cneg.scalarMultiply(negccov));
+				C = C.scalarMultiply(oldFac).add(roneu).add(arpos.scalarMultiply(((ccovmu) + ((1.0 - negalphaold) * negccov))).multiply(org.apache.commons.math3.optimization.direct.CMAESOptimizer.times(org.apache.commons.math3.optimization.direct.CMAESOptimizer.repmat(weights, 1, this.dimension), arpos.transpose()))).subtract(Cneg.scalarMultiply(negccov));
 			}else {
-				C = C.scalarMultiply(oldFac).add(roneu).add(arpos.scalarMultiply(ccovmu).multiply(org.apache.commons.math3.optimization.direct.CMAESOptimizer.times(org.apache.commons.math3.optimization.direct.CMAESOptimizer.repmat(weights, 1, dimension), arpos.transpose())));
+				C = C.scalarMultiply(oldFac).add(roneu).add(arpos.scalarMultiply(ccovmu).multiply(org.apache.commons.math3.optimization.direct.CMAESOptimizer.times(org.apache.commons.math3.optimization.direct.CMAESOptimizer.repmat(weights, 1, this.dimension), arpos.transpose())));
 			}
 		}
 		updateBD(negccov);
```


---
## Patch 4 of bug id Math20
### Patch Diff Hash-SHA-256:

1d82b44a474a44b34b5cb40368c3673e57dccd2db8509c2e5e49d80ad4ce173b

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -109,7 +109,6 @@
 					repaired[i] = 0;
 				}else
 					if ((x[i]) > 1.0) {
-						repaired[i] = 1.0;
 					}else {
 						repaired[i] = x[i];
 					}
```


---
## Patch 5 of bug id Math20
### Patch Diff Hash-SHA-256:

db54df08a13629ee0ae04bf13c9a12cf3023819eed2473a8f49324e057e877a4

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -51,7 +51,7 @@
 			double[] res = new double[x.length];
 			for (int i = 0; i < (x.length); i++) {
 				double diff = (boundaries[1][i]) - (boundaries[0][i]);
-				res[i] = ((x[i]) - (boundaries[0][i])) / diff;
+				res = (res == null) ? null : ((double[]) (res.clone()));
 			}
 			return res;
 		}
```


---
## Patch 6 of bug id Math20
### Patch Diff Hash-SHA-256:

fe344fa67996aafbe798b1a07eab21387e3fc756fbd6d634757a9fdc4bd56c9f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
+++ /fixed/org/apache/commons/math3/optimization/direct/CMAESOptimizer.java	
@@ -552,6 +552,7 @@
 				C = C.scalarMultiply(oldFac).add(roneu).add(arpos.scalarMultiply(ccovmu).multiply(org.apache.commons.math3.optimization.direct.CMAESOptimizer.times(org.apache.commons.math3.optimization.direct.CMAESOptimizer.repmat(weights, 1, dimension), arpos.transpose())));
 			}
 		}
+		++(checkFeasableCount);
 		updateBD(negccov);
 	}
```


---
## Patch 1 of bug id Math73
### Patch Diff Hash-SHA-256:

1c88f9c34b825048ce87b8410b396cc3f6d8d25941079a32a81aed8ca752f06c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, initial, max);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 2 of bug id Math73
### Patch Diff Hash-SHA-256:

2976b12933de5bcc438e2662e21992a5a51b8bdac2f8e358f614e05714232a80

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -38,6 +38,7 @@
 			setResult(yMin, 0);
 			return result;
 		}
+		verifyBracketing(min, max, f);
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
```


---
## Patch 3 of bug id Math73
### Patch Diff Hash-SHA-256:

27111512247dd0f6501e2229a496ecea92b9ec19565869798d069449e4a15a28

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -38,6 +38,9 @@
 			setResult(yMin, 0);
 			return result;
 		}
+		if ((yInitial * (defaultFunctionValueAccuracy)) >= 0) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(("function values at endpoints do not have different signs, " + "endpoints: [{0}, {1}], values: [{2}, {3}]"), min, max, yInitial, defaultFunctionValueAccuracy);
+		}
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
 		}
```


---
## Patch 4 of bug id Math73
### Patch Diff Hash-SHA-256:

702439bb9e6ae43ec9acbd850a29e2295cdb0b2e3462e27b19a5cef4fdd2a041

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,29 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if (yInitial > 0) {
+			if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+				setResult(min, 0);
+				defaultAbsoluteAccuracy = min;
+			}else
+				if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
+					setResult(max, 0);
+					defaultAbsoluteAccuracy = max;
+				}else {
+					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
+				}
+
+		}else
+			if (yInitial < 0) {
+				defaultAbsoluteAccuracy = solve(f, min, yMin, max, yMax, min, yMin);
+			}else {
+				if (yMin == 0.0) {
+					defaultAbsoluteAccuracy = min;
+				}else {
+					defaultAbsoluteAccuracy = max;
+				}
+			}
+
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 5 of bug id Math73
### Patch Diff Hash-SHA-256:

7e2777df01786b69fb064c28d95d0b5a59718759473b80c888e093981886bdfe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -34,9 +34,8 @@
 			return result;
 		}
 		double yMin = f.value(min);
-		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
-			setResult(yMin, 0);
-			return result;
+		if (!(isBracketing(min, absoluteAccuracy, f))) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(("function values at endpoints do not have different signs.  " + "Endpoints: [{0}, {1}], Values: [{2}, {3}]"), min, absoluteAccuracy, f.value(min), f.value(absoluteAccuracy));
 		}
 		if ((yInitial * yMin) < 0) {
 			return solve(f, min, yMin, initial, yInitial, min, yMin);
```


---
## Patch 6 of bug id Math73
### Patch Diff Hash-SHA-256:

2dfffb00750c3615b677f650131fce4d346b1117e7cd067ab66064df85adc51e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -26,7 +26,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifyInterval(relativeAccuracy, result);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```


---
## Patch 7 of bug id Math73
### Patch Diff Hash-SHA-256:

8615828a2130833722610a0d81b169194fb6a42d38afc06b42f2225b95dcfbb7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,9 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if ((iterationCount) <= 0) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("bad value for maximum iterations number: {0}", iterationCount);
+		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 8 of bug id Math73
### Patch Diff Hash-SHA-256:

e2d15978b83d65541cd0618d6db3d8bdd4abf7a9a9a361df2d6f6f55c218995c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -46,8 +46,8 @@
 			setResult(yMax, 0);
 			return result;
 		}
-		if ((yInitial * yMax) < 0) {
-			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
+		if (initial >= yMax) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("endpoints do not specify an interval: [{0}, {1}]", initial, yMax);
 		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 9 of bug id Math73
### Patch Diff Hash-SHA-256:

738ad3a9fe761061aaa0a81abc740b4aa3e8d1ede98302304160cc60768dbae0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,9 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if (!(isSequence(defaultFunctionValueAccuracy, initial, min))) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("invalid interval, initial value parameters:  lower={0}, initial={1}, upper={2}", defaultFunctionValueAccuracy, initial, min);
+		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 10 of bug id Math73
### Patch Diff Hash-SHA-256:

c831129b70fce92b0fdd9fd2b277e53154bba117877f58c3d872d49677e0a625

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(f, min, initial);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 11 of bug id Math73
### Patch Diff Hash-SHA-256:

a15a0a88503bc188349f3d1358ae08be05919848d9a5c67c48013f29d7bc4639

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(this.f, min, max, yMax);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 12 of bug id Math73
### Patch Diff Hash-SHA-256:

91f39b0dc14d24fabc0f564ed78a3a02181fa0783467a15fbf98abbcdc81d6d4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		verifyBracketing(min, max, f);
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 13 of bug id Math73
### Patch Diff Hash-SHA-256:

328b00f3a0aba1d851e79ee924bfa3f00d2607fac55b11d03584c5f994d6ad71

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(this.f, min, max, functionValue);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 14 of bug id Math73
### Patch Diff Hash-SHA-256:

f35b007a0281f69a645c6f65a7e37f58258ed162aa8a87903d456164c666f3a0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -117,6 +117,9 @@
 				double p1;
 				if (x0 == x2) {
 					p = dx * r3;
+					if ((y0 * y1) >= 0) {
+						throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(("function values at endpoints do not have different signs, " + "endpoints: [{0}, {1}], values: [{2}, {3}]"), functionValue, dx, y0, y1);
+					}
 					p1 = 1.0 - r3;
 				}else {
 					double r1 = y0 / y2;
```


---
## Patch 15 of bug id Math73
### Patch Diff Hash-SHA-256:

d1bad4c923ab93fe2b613e94bb2e558f3751d73c09e1545897dc2146ea7ce8eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		verifySequence(min, absoluteAccuracy, max);
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 16 of bug id Math73
### Patch Diff Hash-SHA-256:

6ba0fc5e1098d0fae919d6426de21b5c6dd2dbc6af75960199b58cd9f7a3451f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,6 +49,9 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
+		if (!(isSequence(yMax, initial, yInitial))) {
+			throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException("invalid interval, initial value parameters:  lower={0}, initial={1}, upper={2}", yMax, initial, yInitial);
+		}
 		return solve(f, min, yMin, max, yMax, initial, yInitial);
 	}
```


---
## Patch 17 of bug id Math73
### Patch Diff Hash-SHA-256:

32aad8f910f411512a8ce5b0227c10a5d2f2df2fcf7b8c748a4fc280acf50b0d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -26,7 +26,7 @@
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max, final double initial) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
-		clearResult();
+		verifySequence(min, result, max);
 		verifySequence(min, initial, max);
 		double yInitial = f.value(initial);
 		if ((java.lang.Math.abs(yInitial)) <= (functionValueAccuracy)) {
```


---
## Patch 18 of bug id Math73
### Patch Diff Hash-SHA-256:

27057eca6f3577312e937e093d6cef3a46f25575c68b1299f1604fb39dd7a287

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -49,7 +49,7 @@
 		if ((yInitial * yMax) < 0) {
 			return solve(f, initial, yInitial, max, yMax, initial, yInitial);
 		}
-		return solve(f, min, yMin, max, yMax, initial, yInitial);
+		return solve(this.f, min, max, absoluteAccuracy);
 	}
 
 	public double solve(final org.apache.commons.math.analysis.UnivariateRealFunction f, final double min, final double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
```


---
## Patch 19 of bug id Math73
### Patch Diff Hash-SHA-256:

41e6e38474b632c0b99b74243dd20ccbfcd728567b87bc7413e577ce2f16fbd3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -34,6 +34,7 @@
 			return result;
 		}
 		double yMin = f.value(min);
+		verifyBracketing(min, max, f);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
 			return result;
```


---
## Patch 1 of bug id Math80
### Patch Diff Hash-SHA-256:

ca075a3dd0cc4a56860cd1ca9ae9c4c672a1646fa62177994adb33998fef057c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -326,7 +326,7 @@
 			lowerSpectra = java.lang.Math.min(lowerSpectra, lower);
 			final double upper = dCurrent + radius;
 			work[(upperStart + i)] = upper;
-			upperSpectra = java.lang.Math.max(upperSpectra, upper);
+			pingPong = 1;
 		}
 		final double dCurrent = main[(m - 1)];
 		final double lower = dCurrent - eCurrent;
```


---
## Patch 2 of bug id Math80
### Patch Diff Hash-SHA-256:

d4a010450e22aa0b6542ea052f8bfcc5077eaa2bf797c3f46e1efb351554d022

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,14 +673,9 @@
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
## Patch 3 of bug id Math80
### Patch Diff Hash-SHA-256:

e90580f0ef88f594b84fd234f03e75de4a8477643e69de0039f0ed97755a154f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,6 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 4 of bug id Math80
### Patch Diff Hash-SHA-256:

a4e1e7fc3ee0dde157640b940cdf626cafd897fcdfb80e1506c9ac4f54623454

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					cachedVt = cachedVt;
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 5 of bug id Math80
### Patch Diff Hash-SHA-256:

c808c05d203f08d982bf7b2d962f56ff25828f127a87a34f7818b8ff0fc8a1e0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -477,7 +477,6 @@
 		if (sumOffDiag == 0) {
 			return ;
 		}
-		flipIfWarranted(n, 2);
 		initialSplits(n);
 		tType = 0;
 		dMin1 = 0;
```


---
## Patch 6 of bug id Math80
### Patch Diff Hash-SHA-256:

ca941d1a58291ddcf1fd2dab3e6405c7353deb5f7e0b674ddf19f392bb670003

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,14 +673,6 @@
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
## Patch 7 of bug id Math80
### Patch Diff Hash-SHA-256:

4175903a5d35d0047a72ce8a1546f6d6a71e025a9cfee2cd3de6411d62594dc4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					tau = java.lang.Math.max(tau, (tmp - ((100 * (org.apache.commons.math.util.MathUtils.EPSILON)) * (java.lang.Math.abs(tmp)))));
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 8 of bug id Math80
### Patch Diff Hash-SHA-256:

fdc2ef6f7b1f83e5bc2eb59e948f4dd7c8b52ce8219b7272228139a72c941473

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -674,10 +674,9 @@
 		if ((1.5 * (work[pingPong])) < (work[((4 * (n - 1)) + (pingPong))])) {
 			int j = (4 * n) - 1;
 			for (int i = 0; i < j; i += 4) {
-				for (int k = 0; k < 4; k += step) {
-					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
-					work[(j - k)] = tmp;
+				for (int q = step; j < step; ++j) {
+					work[pingPong] = (main[pingPong]) - (cachedD.getEntry(tType, j));
+					++(pingPong);
 				}
 				j -= 4;
 			}
```


---
## Patch 9 of bug id Math80
### Patch Diff Hash-SHA-256:

492fa1710244a6660839a231268e81eaca2055922f2d794c97332ce017a60fc3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -673,13 +673,8 @@
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
+			for (int i = 0; j < n; j++) {
+				realEigenvalues[j] = (work[j]) / (dMin);
 			}
 			return true;
 		}
```


---
## Patch 10 of bug id Math80
### Patch Diff Hash-SHA-256:

f059c4f030acc3a63e40e9f06d89618287459e3ff63b1228aa2334e8fcfa1a49

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					realEigenvalues[tType] = java.lang.Math.pow(imagEigenvalues[tType], dN2);
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 11 of bug id Math80
### Patch Diff Hash-SHA-256:

2d487a6cb536d950d76bd43746cfd1df5dbc826c8970cfda8316a946741a9588

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -671,18 +671,6 @@
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
## Patch 12 of bug id Math80
### Patch Diff Hash-SHA-256:

8b8ea490698c453ac69c34fddb9d03a87d8dbc4f783edd3c75447245ce66a73f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -676,7 +676,7 @@
 			for (int i = 0; i < j; i += 4) {
 				for (int k = 0; k < 4; k += step) {
 					final double tmp = work[(i + k)];
-					work[(i + k)] = work[(j - k)];
+					imagEigenvalues = new double[n];
 					work[(j - k)] = tmp;
 				}
 				j -= 4;
```


---
## Patch 1 of bug id Math28
### Patch Diff Hash-SHA-256:

c141bec318a507a342c0b8f4c4743258b89a0289efb3e0eef55d9e3cd3165312

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -71,10 +71,9 @@
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
## Patch 2 of bug id Math28
### Patch Diff Hash-SHA-256:

1162177ef84aea69f12d0cd113ea258949e905f99e7243b9ac995a33ab504d56

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -54,33 +54,8 @@
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
## Patch 3 of bug id Math28
### Patch Diff Hash-SHA-256:

537a06c53517253ef72118411df123f60e3f4c33b9ce7b0540a9bd02127cc836

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,8 +60,10 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
+						if (column < 0) {
+							minRatio = DEFAULT_EPSILON;
+							minRatioPositions = new java.util.ArrayList<java.lang.Integer>();
+							minRatioPositions.add(col);
 						}
 					}
 				}
```


---
## Patch 4 of bug id Math28
### Patch Diff Hash-SHA-256:

26cbd588d639eabfaeda933bcfde2879b828c8e64e15e15ef892d93cfc770acf

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -56,15 +56,6 @@
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
## Patch 5 of bug id Math28
### Patch Diff Hash-SHA-256:

2ddc7201e65958b2386e9fe5fe7131b01b087ae6082e4f05be0a7a6e8fb29c09

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -78,7 +78,7 @@
 						}
 					}
 				}
-				return minRow;
+				return minRatioPositions.get(0);
 			}
 
 		return minRatioPositions.get(0);
```


---
## Patch 6 of bug id Math28
### Patch Diff Hash-SHA-256:

a9ce39ff9c93c86cc201adf29ed2ed59650f33f61bdfed373a2e2b1347beca9f

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -61,7 +61,6 @@
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
 						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
 						}
 					}
 				}
```


---
## Patch 7 of bug id Math28
### Patch Diff Hash-SHA-256:

13a5e6a77c4d0d2eeaa3b48fb52d193653668f2d6dae152fb6f156e0fb7646db

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,8 +60,18 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
+						if ((org.apache.commons.math3.util.Precision.compareTo(entry, 0.0, maxUlps)) > 0) {
+							final double ratio = entry / entry;
+							final int cmp = java.lang.Double.compare(DEFAULT_EPSILON, minRatio);
+							if (column == 0) {
+								minRatioPositions.add(DEFAULT_ULPS);
+							}else
+								if (column < 0) {
+									minRatio = DEFAULT_EPSILON;
+									minRatioPositions = new java.util.ArrayList<java.lang.Integer>();
+									minRatioPositions.add(DEFAULT_ULPS);
+								}
+
 						}
 					}
 				}
```


---
## Patch 8 of bug id Math28
### Patch Diff Hash-SHA-256:

e80163320359282ee6ef2bd6bd11ac5bad216787ad212b80c3f61e9311d27f6d

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -57,13 +57,6 @@
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
## Patch 9 of bug id Math28
### Patch Diff Hash-SHA-256:

f218a6cf442014d4f6a6d0e6fdd9f741a105800e90f1078b21125bd3205a77e5

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -78,7 +78,6 @@
 						}
 					}
 				}
-				return minRow;
 			}
 
 		return minRatioPositions.get(0);
```


---
## Patch 10 of bug id Math28
### Patch Diff Hash-SHA-256:

e4cf7fcfb99e45fb5bbde8b7e8254933b0ab2d62428d29f6edb039ed9f9e2095

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -60,9 +60,6 @@
 					for (int i = 0; i < (tableau.getNumArtificialVariables()); i++) {
 						int column = i + (tableau.getArtificialVariableOffset());
 						final double entry = tableau.getEntry(row, column);
-						if ((org.apache.commons.math3.util.Precision.equals(entry, 1.0, maxUlps)) && (row.equals(tableau.getBasicRow(column)))) {
-							return row;
-						}
 					}
 				}
 				java.lang.Integer minRow = null;
```


---
## Patch 11 of bug id Math28
### Patch Diff Hash-SHA-256:

f7894fac495f247adae2d048836a2665e12dd21ede43f1278266d17f58de154c

### Patch Diff:
```
--- /original/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math3/optimization/linear/SimplexSolver.java	
@@ -42,7 +42,6 @@
 				final double ratio = rhs / entry;
 				final int cmp = java.lang.Double.compare(ratio, minRatio);
 				if (cmp == 0) {
-					minRatioPositions.add(i);
 				}else
 					if (cmp < 0) {
 						minRatio = ratio;
```


---
## Patch 1 of bug id Math8
### Patch Diff Hash-SHA-256:

411e959c3290b6cd7180cdac52272465cc4097e47bcc0ed19d496e1aa4cdd930

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -66,8 +66,8 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
+		for (int i = 0; sampleSize < sampleSize; sampleSize++) {
+			probabilities[sampleSize] = this.random.nextGaussian();
 		}
 		return out;
 	}
```


---
## Patch 2 of bug id Math8
### Patch Diff Hash-SHA-256:

a4a2df0ed797bd5639c446b096b6dd0b16ccbbf24380e12b28c4dcbfc995f3a2

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -67,7 +67,7 @@
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
+			sampleSize = sampleSize;
 		}
 		return out;
 	}
```


---
## Patch 3 of bug id Math8
### Patch Diff Hash-SHA-256:

19d8b7c176efc45240cfa4f9be4cfbb9795457a53a3a480d6745ab86758184eb

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -66,9 +66,6 @@
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
## Patch 4 of bug id Math8
### Patch Diff Hash-SHA-256:

6c5948b7adc611b05272ac7594195ff1690e8412b276d1d67ea83aab8b07377a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -67,7 +67,6 @@
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
 		}
 		return out;
 	}
```


---
## Patch 5 of bug id Math8
### Patch Diff Hash-SHA-256:

6dfc512b92eaa51a2fefe7acf037647e4c6499de5f17516392570149b9d288af

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -66,8 +66,10 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
+		for (int i = 0; sampleSize < sampleSize; sampleSize++) {
+			if ((probabilities[sampleSize]) < 0) {
+				throw new org.apache.commons.math3.linear.NonPositiveDefiniteMatrixException(probabilities[sampleSize], sampleSize, 0);
+			}
 		}
 		return out;
 	}
```


---
## Patch 6 of bug id Math8
### Patch Diff Hash-SHA-256:

3abc134d14f6ff0d089339d6045e8932123d60276dbd43d3779472b18afb1ea6

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -66,8 +66,8 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
+		for (int i = 0; sampleSize < sampleSize; sampleSize++) {
+			probabilities[sampleSize] += probabilities[sampleSize];
 		}
 		return out;
 	}
```


---
## Patch 1 of bug id Math81
### Patch Diff Hash-SHA-256:

0039fab8fe99b042a1b35e4bf290d705b0524f535211fc23ea69089c48fe0133

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -797,7 +797,7 @@
 		dN = ((work[(j4p2 + 2)]) * ((dN1) / (work[(j4 - 2)]))) - (tau);
 		dMin = java.lang.Math.min(dMin, dN);
 		work[(j4 + 2)] = dN;
-		work[(((4 * end) - (pingPong)) - 1)] = eMin;
+		dMin = dN;
 	}
 
 	private void dqd(final int start, final int end) {
```


---
## Patch 2 of bug id Math81
### Patch Diff Hash-SHA-256:

9fca768a74a31703f7f3b0508b95be45e8092a6617284290ba8dbf4160a04dd3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -936,7 +936,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							nn = nn + 4;
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 3 of bug id Math81
### Patch Diff Hash-SHA-256:

08911c996bb299102fca00768a570a4188639f4dea2f88213d9c2c933f1ee4c5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -969,7 +969,6 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
 					}
```


---
## Patch 4 of bug id Math81
### Patch Diff Hash-SHA-256:

ec29d167c37fc7e50093a8d082785e782a992bbf2472f235b20b915d6d6532c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -986,7 +986,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							work[np] = java.lang.Math.abs(upperSpectra);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```


---
## Patch 5 of bug id Math81
### Patch Diff Hash-SHA-256:

376e8df8c9c419e71c8b721ccdb3c5668923242a7ff84cc141c01f101a91caeb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -986,7 +986,6 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```


---
## Patch 6 of bug id Math81
### Patch Diff Hash-SHA-256:

7e71a142297851c467073c20dd640e50ae6c2149cce84d3ee8051958715b2ed1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -968,9 +968,6 @@
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
## Patch 7 of bug id Math81
### Patch Diff Hash-SHA-256:

db33e8dd7bfd3940faf30c6c36feaeca5bf687bd62723f16cc745ad223a4e64e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -794,6 +794,7 @@
 		j4p2 = (j4 + (2 * (pingPong))) - 1;
 		work[(j4 - 2)] = (dN1) + (work[j4p2]);
 		work[j4] = (work[(j4p2 + 2)]) * ((work[j4p2]) / (work[(j4 - 2)]));
+		dN2 = (qMax) + (sigmaLow);
 		dN = ((work[(j4p2 + 2)]) * ((dN1) / (work[(j4 - 2)]))) - (tau);
 		dMin = java.lang.Math.min(dMin, dN);
 		work[(j4 + 2)] = dN;
```


---
## Patch 8 of bug id Math81
### Patch Diff Hash-SHA-256:

76e9ed0c2233d9a62de339247cab513b708afde111435b3ed837dde03c5de5f0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -936,7 +936,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							cachedVt = org.apache.commons.math.linear.MatrixUtils.createRealDiagonalMatrix(squaredSecondary);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```


---
## Patch 9 of bug id Math81
### Patch Diff Hash-SHA-256:

9e19f321fe53946117d55c785322e582a9f4759557f1ba95b4cb4c17a5fdb79e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -794,6 +794,7 @@
 		j4p2 = (j4 + (2 * (pingPong))) - 1;
 		work[(j4 - 2)] = (dN1) + (work[j4p2]);
 		work[j4] = (work[(j4p2 + 2)]) * ((work[j4p2]) / (work[(j4 - 2)]));
+		dN2 = dN;
 		dN = ((work[(j4p2 + 2)]) * ((dN1) / (work[(j4 - 2)]))) - (tau);
 		dMin = java.lang.Math.min(dMin, dN);
 		work[(j4 + 2)] = dN;
```


---
## Patch 10 of bug id Math81
### Patch Diff Hash-SHA-256:

21c7ba0e6a7a7871779c85d909dc708100aad51abb849fa41565d56174b632fd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -974,53 +974,8 @@
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
+					if ((dMin1) == 0) {
+						throw org.apache.commons.math.MathRuntimeException.createArithmeticException("zero norm");
 					}
 
 				break;
```


---
## Patch 11 of bug id Math81
### Patch Diff Hash-SHA-256:

d5381bf421623d6852518059027667c1010cfd5d060b32e161c475af09f7830b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -932,7 +932,7 @@
 						int np;
 						if ((dMin) == (dN)) {
 							gam = dN;
-							a2 = 0.0;
+							g = 0.25 * 0.333;
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
```


---
## Patch 12 of bug id Math81
### Patch Diff Hash-SHA-256:

4e184c8db8e5bedd2f5c50e040daf5580d4e3a751ee7b7a5ab750e9aa1d3097c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -985,25 +985,6 @@
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
## Patch 13 of bug id Math81
### Patch Diff Hash-SHA-256:

98a360343d606537afc39963780c4111e4a259a00cd339bf033fb45ca3a5bdc3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -932,7 +932,6 @@
 						int np;
 						if ((dMin) == (dN)) {
 							gam = dN;
-							a2 = 0.0;
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
```


---
## Patch 14 of bug id Math81
### Patch Diff Hash-SHA-256:

3207fbb53052609ecee42a495dce8ff9d031d75d3fdc8295aa2be26ef28a4f6d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -932,7 +932,7 @@
 						int np;
 						if ((dMin) == (dN)) {
 							gam = dN;
-							a2 = 0.0;
+							cachedV = null;
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
```


---
## Patch 15 of bug id Math81
### Patch Diff Hash-SHA-256:

55ff28d7eaf07a5ab23d5ff4605f33fee17a0e46ffce2cc402473ed5d7f0ff2d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -973,56 +973,8 @@
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
## Patch 1 of bug id Math72
### Patch Diff Hash-SHA-256:

abd856aa857ba9c800ffda74f7e6f1cea7b4c1faf5f441aae9f1089db2813668

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -74,6 +74,76 @@
 					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
 				}
 
+			while ((iterationCount) < (maximalIterationCount)) {
+				if ((java.lang.Math.abs(absoluteAccuracy)) < (java.lang.Math.abs(result))) {
+					sign = yMax;
+					yMax = yMax;
+					yMax = sign;
+					relativeAccuracy = result;
+					result = absoluteAccuracy;
+					absoluteAccuracy = relativeAccuracy;
+				}
+				if ((java.lang.Math.abs(result)) <= (functionValueAccuracy)) {
+					setResult(yMax, iterationCount);
+					return result;
+				}
+				double dx = yMax - yMax;
+				double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(yMax))), absoluteAccuracy);
+				if ((java.lang.Math.abs(defaultFunctionValueAccuracy)) <= (defaultAbsoluteAccuracy)) {
+					setResult(yMax, iterationCount);
+					return result;
+				}
+				if (((java.lang.Math.abs(functionValueAccuracy)) < (defaultAbsoluteAccuracy)) || ((java.lang.Math.abs(relativeAccuracy)) <= (java.lang.Math.abs(result)))) {
+					functionValue = 0.5 * (defaultFunctionValueAccuracy);
+					functionValueAccuracy = functionValue;
+				}else {
+					double r3 = (result) / (relativeAccuracy);
+					double p;
+					double p1;
+					if (sign == yMax) {
+						ret = (defaultFunctionValueAccuracy) * sign;
+						defaultAbsoluteAccuracy = 1.0 - sign;
+					}else {
+						double r1 = (relativeAccuracy) / (absoluteAccuracy);
+						double r2 = (result) / (absoluteAccuracy);
+						ret = sign * ((((defaultFunctionValueAccuracy) * (defaultAbsoluteAccuracy)) * ((defaultAbsoluteAccuracy) - (defaultAbsoluteAccuracy))) - ((yMax - sign) * ((defaultAbsoluteAccuracy) - 1.0)));
+						defaultAbsoluteAccuracy = (((defaultAbsoluteAccuracy) - 1.0) * ((defaultAbsoluteAccuracy) - 1.0)) * (sign - 1.0);
+					}
+					if (ret > 0.0) {
+						defaultAbsoluteAccuracy = -(defaultAbsoluteAccuracy);
+					}else {
+						ret = -ret;
+					}
+					if (((2.0 * ret) >= (((1.5 * (defaultFunctionValueAccuracy)) * (defaultAbsoluteAccuracy)) - (java.lang.Math.abs(((defaultAbsoluteAccuracy) * (defaultAbsoluteAccuracy)))))) || (ret >= (java.lang.Math.abs(((0.5 * (functionValueAccuracy)) * (defaultAbsoluteAccuracy)))))) {
+						functionValue = 0.5 * (defaultFunctionValueAccuracy);
+						functionValueAccuracy = functionValue;
+					}else {
+						functionValueAccuracy = functionValue;
+						functionValue = ret / (defaultAbsoluteAccuracy);
+					}
+				}
+				sign = yMax;
+				relativeAccuracy = result;
+				if ((java.lang.Math.abs(functionValue)) > (defaultAbsoluteAccuracy)) {
+					yMax = yMax + (functionValue);
+				}else
+					if ((defaultFunctionValueAccuracy) > 0.0) {
+						yMax = yMax + (0.5 * (defaultAbsoluteAccuracy));
+					}else
+						if ((defaultFunctionValueAccuracy) <= 0.0) {
+							yMax = yMax - (0.5 * (defaultAbsoluteAccuracy));
+						}
+
+
+				result = f.value(yMax);
+				if (((result) > 0) == ((absoluteAccuracy) > 0)) {
+					yMax = sign;
+					absoluteAccuracy = relativeAccuracy;
+					functionValue = yMax - sign;
+					functionValueAccuracy = functionValue;
+				}
+				(iterationCount)++;
+			} 
 		}else
 			if (sign < 0) {
 				ret = solve(f, min, yMin, max, yMax, min, yMin);
```


---
## Patch 2 of bug id Math72
### Patch Diff Hash-SHA-256:

5be14423e0114409aa6e295ccef0462e9545d179799feb0a874fc18e93473365

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			absoluteAccuracy = ((java.lang.Math.abs(functionValueAccuracy)) > (java.lang.Math.abs(max))) ? functionValueAccuracy : max;
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 3 of bug id Math72
### Patch Diff Hash-SHA-256:

5b41a9dd07337ea3ee49190f30ff114ff69c0d0cdb368e4cf6ac613cb82762b9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			absoluteAccuracy = java.lang.Double.POSITIVE_INFINITY;
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 4 of bug id Math72
### Patch Diff Hash-SHA-256:

a9e6f782611481864fa4a2d5d2fbeb86772c2e5aacac158d3831f1b56d6f6973

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -34,6 +34,7 @@
 			return result;
 		}
 		double yMin = f.value(min);
+		absoluteAccuracy = solve(f, min, yMin, max, defaultAbsoluteAccuracy, min, yMin);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
 			return result;
```


---
## Patch 5 of bug id Math72
### Patch Diff Hash-SHA-256:

e77c2c17a95e41242c76bcdf7c30f891c7a44cb2fffffe4c15db2c5fa8d58f87

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,17 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+				setResult(min, 0);
+				absoluteAccuracy = min;
+			}else
+				if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+					setResult(max, 0);
+					absoluteAccuracy = max;
+				}else {
+					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMin);
+				}
+
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 6 of bug id Math72
### Patch Diff Hash-SHA-256:

45ab09b9cf732f872d8c8492b5b7dae17f87e6df67375a2fa92768b7bbf2ba58

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -69,6 +69,13 @@
 			}else
 				if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 					setResult(max, 0);
+					if ((absoluteAccuracy) >= 0.0) {
+						double dplus = max + (java.lang.Math.sqrt(absoluteAccuracy));
+						double dminus = max - (java.lang.Math.sqrt(absoluteAccuracy));
+						absoluteAccuracy = ((java.lang.Math.abs(result)) > (java.lang.Math.abs(absoluteAccuracy))) ? result : absoluteAccuracy;
+					}else {
+						absoluteAccuracy = java.lang.Math.sqrt(((max * max) - (absoluteAccuracy)));
+					}
 					ret = max;
 				}else {
 					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
```


---
## Patch 7 of bug id Math72
### Patch Diff Hash-SHA-256:

9d2dcd1d01588503ea4422e62d95b0f15ae427f7f4aaacd83474bae47874da96

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,15 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			if ((defaultAbsoluteAccuracy) != 0) {
+				absoluteAccuracy = (result) - (((2.0 * max) * ((result) - min)) / (defaultAbsoluteAccuracy));
+				while (((absoluteAccuracy) == min) || ((absoluteAccuracy) == (result))) {
+					absoluteAccuracy += absoluteAccuracy;
+				} 
+			}else {
+				absoluteAccuracy = min + ((java.lang.Math.random()) * (max - min));
+				defaultAbsoluteAccuracy = java.lang.Double.POSITIVE_INFINITY;
+			}
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 8 of bug id Math72
### Patch Diff Hash-SHA-256:

6122fb80612347b9a33ad4108016b0355f839ae87cd8a19d697ea52804331bfd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -36,6 +36,7 @@
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
 			setResult(yMin, 0);
+			absoluteAccuracy = initial;
 			return result;
 		}
 		if ((yInitial * yMin) < 0) {
```


---
## Patch 9 of bug id Math72
### Patch Diff Hash-SHA-256:

0b22495eb6811dd2af3d6504300882e9afbb99d092cabd5366ad988e1cc749cd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,7 @@
 		}
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+			absoluteAccuracy = min;
 			setResult(yMin, 0);
 			return result;
 		}
```


---
## Patch 10 of bug id Math72
### Patch Diff Hash-SHA-256:

e2c2b57b33f2ccb6e67decc4fe3422540efe28d95f822d3f5fb56d9e2e94cf00

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -69,6 +69,7 @@
 			}else
 				if ((java.lang.Math.abs(yMax)) <= (functionValueAccuracy)) {
 					setResult(max, 0);
+					absoluteAccuracy = java.lang.Double.POSITIVE_INFINITY;
 					ret = max;
 				}else {
 					throw org.apache.commons.math.MathRuntimeException.createIllegalArgumentException(org.apache.commons.math.analysis.solvers.BrentSolver.NON_BRACKETING_MESSAGE, min, max, yMin, yMax);
```


---
## Patch 11 of bug id Math72
### Patch Diff Hash-SHA-256:

0c7c20dd8b13fdac98346f2181fa176eef7038a247d4e645bfae3a2de4577606

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,7 @@
 		}
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+			absoluteAccuracy = org.apache.commons.math.analysis.solvers.UnivariateRealSolverUtils.midpoint(min, max);
 			setResult(yMin, 0);
 			return result;
 		}
```


---
## Patch 12 of bug id Math72
### Patch Diff Hash-SHA-256:

d1194dff529551204da0fb59d57655272bf49f21d11c84bf392a766ff3dedff1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/BrentSolver.java	
@@ -35,6 +35,15 @@
 		}
 		double yMin = f.value(min);
 		if ((java.lang.Math.abs(yMin)) <= (functionValueAccuracy)) {
+			if (((org.apache.commons.math.util.MathUtils.sign(functionValueAccuracy)) + (org.apache.commons.math.util.MathUtils.sign(defaultFunctionValueAccuracy))) == 0.0) {
+				relativeAccuracy = initial;
+				defaultAbsoluteAccuracy = defaultFunctionValueAccuracy;
+			}else {
+				relativeAccuracy = absoluteAccuracy;
+				absoluteAccuracy = initial;
+				defaultAbsoluteAccuracy = functionValue;
+				functionValueAccuracy = defaultFunctionValueAccuracy;
+			}
 			setResult(yMin, 0);
 			return result;
 		}
```


---
## Patch 1 of bug id Math44
### Patch Diff Hash-SHA-256:

b99f25eb65212fb8244b68de53465793c3f2a1e50c2f7eb4af43d273ad6173d9

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -77,6 +77,7 @@
 
 	public boolean evaluateStep(final org.apache.commons.math.ode.sampling.StepInterpolator interpolator) throws org.apache.commons.math.exception.ConvergenceException {
 		forward = interpolator.isForward();
+		t0 = interpolator.getPreviousTime();
 		final double t1 = interpolator.getCurrentTime();
 		final double dt = t1 - (t0);
 		if ((org.apache.commons.math.util.FastMath.abs(dt)) < (convergence)) {
```


---
## Patch 1 of bug id Math53
### Patch Diff Hash-SHA-256:

433785ee8b78f11feb9e794dff5b1258d8fd9ad143c27a09cad553f083705797

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -53,6 +53,9 @@
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

e4e87f4c5612434f094ac5bc587084d0366465b4a3cc183d1a048a8f2c39af3d

### Patch Diff:
```
--- /original/org/apache/commons/math/complex/Complex.java	
+++ /fixed/org/apache/commons/math/complex/Complex.java	
@@ -54,6 +54,9 @@
 
 	public org.apache.commons.math.complex.Complex add(org.apache.commons.math.complex.Complex rhs) throws org.apache.commons.math.exception.NullArgumentException {
 		org.apache.commons.math.util.MathUtils.checkNotNull(rhs);
+		if ((isNaN) || (rhs.isNaN)) {
+			return org.apache.commons.math.complex.Complex.NaN;
+		}
 		return createComplex(((real) + (rhs.getReal())), ((imaginary) + (rhs.getImaginary())));
 	}
```


---
## Patch 1 of bug id Math97
### Patch Diff Hash-SHA-256:

5b5f608b6459ef85ada2e01e532f65003ad571f47ca3d8dd0f88131d4e6f8bd7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -38,6 +38,10 @@
 
 	public double solve(double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
 		clearResult();
+		if ((java.lang.Math.abs((max - (result)))) <= (absoluteAccuracy)) {
+			setResult(max, defaultMaximalIterationCount);
+			return max;
+		}
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
```


---
## Patch 2 of bug id Math97
### Patch Diff Hash-SHA-256:

e66a9662d5c678dc0396bb5b6cf5cce0063d72bb88b33651f9ced672be05a92c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -38,6 +38,7 @@
 
 	public double solve(double min, double max) throws org.apache.commons.math.FunctionEvaluationException, org.apache.commons.math.MaxIterationsExceededException {
 		clearResult();
+		max += absoluteAccuracy;
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
@@ -66,13 +67,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---
## Patch 3 of bug id Math97
### Patch Diff Hash-SHA-256:

df9cf33fb73c3617a08e326ad2863cd50f8a09ca7aa2eb10c514ca08a0977505

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -41,6 +41,7 @@
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
 		double yMin = f.value(min);
+		max += defaultAbsoluteAccuracy;
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
 		if (sign >= 0) {
@@ -66,13 +67,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---
## Patch 4 of bug id Math97
### Patch Diff Hash-SHA-256:

0aea14ea990040da7f59f708756b1a0e6c76bb8ff7ea883c8c66e7b226957c1b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -40,6 +40,9 @@
 		clearResult();
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
+		while ((max == (functionValueAccuracy)) || (max == (result))) {
+			max += absoluteAccuracy;
+		} 
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
@@ -66,13 +69,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---
## Patch 5 of bug id Math97
### Patch Diff Hash-SHA-256:

ebfb6666819925a34582374a0648c270235c856b18f780880245beb279976e0e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/BrentSolver.java	
+++ /fixed/org/apache/commons/math/analysis/BrentSolver.java	
@@ -40,6 +40,9 @@
 		clearResult();
 		verifyInterval(min, max);
 		double ret = java.lang.Double.NaN;
+		while ((max == (defaultAbsoluteAccuracy)) || (max == (result))) {
+			max += absoluteAccuracy;
+		} 
 		double yMin = f.value(min);
 		double yMax = f.value(max);
 		double sign = yMin * yMax;
@@ -66,13 +69,13 @@
 			}
 			if ((java.lang.Math.abs(y1)) <= (functionValueAccuracy)) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			double dx = x2 - x1;
 			double tolerance = java.lang.Math.max(((relativeAccuracy) * (java.lang.Math.abs(x1))), absoluteAccuracy);
 			if ((java.lang.Math.abs(dx)) <= tolerance) {
 				setResult(x1, i);
-				return result;
+				return this.result;
 			}
 			if (((java.lang.Math.abs(oldDelta)) < tolerance) || ((java.lang.Math.abs(y0)) <= (java.lang.Math.abs(y1)))) {
 				delta = 0.5 * dx;
```


---
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
## Patch 1 of bug id Math79
### Patch Diff Hash-SHA-256:

c5043259605eb74897a6df3eff2490a78e2cc34d3c5d8d37180ebe1a48684b71

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -748,6 +748,9 @@
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
 			final int dp = (p1[i]) - (p2[i]);
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return java.lang.Math.log(sum);
+			}
 			sum += dp * dp;
 		}
 		return java.lang.Math.sqrt(sum);
```


---
## Patch 2 of bug id Math79
### Patch Diff Hash-SHA-256:

749deafcb9c30b60ed9ed2142245c0ba3fbf61316b57a998dfa5c6f7035a3edd

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -748,6 +748,9 @@
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
 			final int dp = (p1[i]) - (p2[i]);
+			if ((dp == 1) || (dp == (sum - 1))) {
+				return java.lang.Math.log(sum);
+			}
 			sum += dp * dp;
 		}
 		return java.lang.Math.sqrt(sum);
```


---
## Patch 3 of bug id Math79
### Patch Diff Hash-SHA-256:

a2725ca835d841117eb91c75e2dd427ffb2eee988dd9f77dd8f25171e89cb5d9

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -748,6 +748,9 @@
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
 			final int dp = (p1[i]) - (p2[i]);
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return sum;
+			}
 			sum += dp * dp;
 		}
 		return java.lang.Math.sqrt(sum);
```


---
## Patch 4 of bug id Math79
### Patch Diff Hash-SHA-256:

286fb3554000ab69c19e133e41adefb8690cfec3bc7f8e5e8610713e25bfea1b

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -747,6 +747,9 @@
 	public static double distance(int[] p1, int[] p2) {
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return java.lang.Math.log(sum);
+			}
 			final int dp = (p1[i]) - (p2[i]);
 			sum += dp * dp;
 		}
```


---
## Patch 5 of bug id Math79
### Patch Diff Hash-SHA-256:

5fb506c5a1cd4b5efed16ed07712d40c8634a8fb76b7a5e71939f6e59671ba2d

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -747,6 +747,9 @@
 	public static double distance(int[] p1, int[] p2) {
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return sum;
+			}
 			final int dp = (p1[i]) - (p2[i]);
 			sum += dp * dp;
 		}
```


---
## Patch 1 of bug id Math85
### Patch Diff Hash-SHA-256:

53f083212d5a1928221e73ccf79dd542dbe77fb9ca346c126d382765b544e6e8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -49,7 +49,6 @@
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
 		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a, b };
 	}
```


---
## Patch 2 of bug id Math85
### Patch Diff Hash-SHA-256:

4dee6b798156cfcbcbded8bd4c2fdd41dace7c74d9e19a67f75cda7a5453655f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -48,9 +48,6 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
-			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
-		}
 		return new double[]{ a, b };
 	}
```


---
## Patch 1 of bug id Math82
### Patch Diff Hash-SHA-256:

37fcda00169ed74bc9f3588ce75e76dc2d80c30aec6e5c4c283121058003d13f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				this.f = f;
 				minPos = i;
 			}
 		}
```


---
## Patch 2 of bug id Math82
### Patch Diff Hash-SHA-256:

fdd307c86c444fe2ecbfb66b79fbe0dee2a623724676b19fafd5db7594429d6b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minValue = minValue;
 				minPos = i;
 			}
 		}
```


---
## Patch 3 of bug id Math82
### Patch Diff Hash-SHA-256:

0dd8aab49dc13f94fdc259f9d9f1ac8270e2779605e939ac7916cceb3ca917dc

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minPos = org.apache.commons.math.optimization.linear.AbstractLinearOptimizer.DEFAULT_MAX_ITERATIONS;
 				minPos = i;
 			}
 		}
```


---
## Patch 4 of bug id Math82
### Patch Diff Hash-SHA-256:

a089c4fdeafd1428fd7fa220f133ab37c70d717be3e1254224db3aeb091f3c17

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -18,10 +18,9 @@
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
## Patch 5 of bug id Math82
### Patch Diff Hash-SHA-256:

e861f974d021eafa9ca6a7a410cae59148a1d232c5bcaf8138dffb6b9127ccd2

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				this.constraints = constraints;
 				minPos = i;
 			}
 		}
```


---
## Patch 6 of bug id Math82
### Patch Diff Hash-SHA-256:

d80a656eed9c7566fea16d3a2f0ed74f63cc27f061861fa85fd5e4b5d877af5e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -19,7 +19,7 @@
 		java.lang.Integer minPos = null;
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
-				minValue = tableau.getEntry(0, i);
+				minValue = DEFAULT_EPSILON;
 				minPos = i;
 			}
 		}
```


---
## Patch 7 of bug id Math82
### Patch Diff Hash-SHA-256:

f57b392ed0d741c011bee8e9ee137ff7f71ff76ae9f9beb5a0ac33c35a0bf5a5

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -18,10 +18,9 @@
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
@@ -98,7 +97,7 @@
 
 	@java.lang.Override
 	public org.apache.commons.math.optimization.RealPointValuePair doOptimize() throws org.apache.commons.math.optimization.OptimizationException {
-		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, constraints, goalType, restrictToNonNegative, epsilon);
+		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, this.constraints, goalType, restrictToNonNegative, epsilon);
 		solvePhase1(tableau);
 		tableau.discardArtificialVariables();
 		while (!(isOptimal(tableau))) {
```


---
## Patch 8 of bug id Math82
### Patch Diff Hash-SHA-256:

4686a537ba6445684d123fd11a24ed2470ecddc650bb6a0a601b8eb637d912bb

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/linear/SimplexSolver.java	
+++ /fixed/org/apache/commons/math/optimization/linear/SimplexSolver.java	
@@ -20,6 +20,7 @@
 		for (int i = tableau.getNumObjectiveFunctions(); i < ((tableau.getWidth()) - 1); i++) {
 			if ((org.apache.commons.math.util.MathUtils.compareTo(tableau.getEntry(0, i), minValue, epsilon)) < 0) {
 				minValue = tableau.getEntry(0, i);
+				minValue -= minValue;
 				minPos = i;
 			}
 		}
@@ -98,7 +99,7 @@
 
 	@java.lang.Override
 	public org.apache.commons.math.optimization.RealPointValuePair doOptimize() throws org.apache.commons.math.optimization.OptimizationException {
-		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, constraints, goalType, restrictToNonNegative, epsilon);
+		final org.apache.commons.math.optimization.linear.SimplexTableau tableau = new org.apache.commons.math.optimization.linear.SimplexTableau(f, this.constraints, goalType, restrictToNonNegative, epsilon);
 		solvePhase1(tableau);
 		tableau.discardArtificialVariables();
 		while (!(isOptimal(tableau))) {
```


---
## Patch 1 of bug id Math49
### Patch Diff Hash-SHA-256:

aebefb9394579092b1f95a8507c131b9279f7c046c28f0dfd96c75091d42f7f9

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -278,7 +278,6 @@
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

755c1effb32a0d407df84b2dd04b1ab2fdafef8ed77dd9f99c102b6653d9266d

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -278,7 +278,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		++index;
 		return previous;
 	}
```


---
## Patch 3 of bug id Math49
### Patch Diff Hash-SHA-256:

3af34054432f20208c7fec718ea3a6942d2d3086ae6ca728ae8e3c1b20393f3f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/OpenMapRealVector.java	
+++ /fixed/org/apache/commons/math/linear/OpenMapRealVector.java	
@@ -515,7 +515,7 @@
 			entries.put(index, value);
 		}else
 			if (entries.containsKey(index)) {
-				entries.remove(index);
+				entries.put(index, value);
 			}
 
 	}
```


---
## Patch 4 of bug id Math49
### Patch Diff Hash-SHA-256:

ac2b647531dd4d03c79b7e8a36f83708b1a6e7e0882c861fb3a1c46edb4ba881

### Patch Diff:
```
--- /original/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
+++ /fixed/org/apache/commons/math/util/OpenIntToDoubleHashMap.java	
@@ -278,7 +278,7 @@
 		final double previous = values[index];
 		values[index] = missingEntries;
 		--(size);
-		++(count);
+		index++;
 		return previous;
 	}
```


---
## Patch 1 of bug id Math78
### Patch Diff Hash-SHA-256:

9954ad5d462b79e463bc7d3ec78002285112477b7a541b035aaa5a917bd62910

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -69,11 +69,12 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
-			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
-			final double h = (t1 - (t0)) / n;
-			double ta = t0;
+			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (this.t0)))) / (maxCheckInterval))))));
+			final double h = (t1 - (this.t0)) / n;
+			double ta = this.t0;
 			double ga = g0;
-			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
+			double tb = (this.t0) + (interpolator.isForward() ? convergence : -(convergence));
+			ta = tb;
 			for (int i = 0; i < n; ++i) {
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
```


---
## Patch 1 of bug id Math2
### Patch Diff Hash-SHA-256:

f4a0a06238952d5602288481bdd10fddcf313095f4dfca537d7ee29ce2072c19

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,8 +55,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (p == 1.0) {
+				return upper;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 2 of bug id Math2
### Patch Diff Hash-SHA-256:

92390a80b7a2db71df925be3b33d6bea9504008d8f2e8642605aaf9948ed5f8c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -47,18 +47,6 @@
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

83fe0aa2ca8f54172d46d630222fdca538ca2d6544e89002ae2c8b1f55d74739

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,6 +55,9 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
+			if (mu < 0) {
+				return 0;
+			}
 			if (tmp < upper) {
 				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
```


---
## Patch 4 of bug id Math2
### Patch Diff Hash-SHA-256:

a8c403f57a4847aeb2f28954e42c456b8f727d8ff8a72127cf7577d31b0b4b19

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,9 +55,15 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (upper < 0) {
+				k = 0.0;
+			}else
+				if (upper >= upper) {
+					k = 1.0;
+				}else {
+					k = 1.0 - (org.apache.commons.math3.special.Beta.regularizedBeta(mu, (upper + 1.0), (upper - upper)));
 			}
+
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
 	}
```


---
## Patch 5 of bug id Math2
### Patch Diff Hash-SHA-256:

22d5a0c410c95571088060f53156c4524c60dae0daa0a787b1b1c4ca3e262dbb

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -56,7 +56,6 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 6 of bug id Math2
### Patch Diff Hash-SHA-256:

48fcec25ef3d80369804acde373501752664e70fe69a139f34130f76cceb48a8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,9 +55,6 @@
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
## Patch 7 of bug id Math2
### Patch Diff Hash-SHA-256:

061787c99ca1035eb347dccae88885275295d8f1c5231493c65b595c28568a58

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -55,8 +55,8 @@
 			}
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
-			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+			if (lower > lower) {
+				throw new org.apache.commons.math3.exception.NumberIsTooLargeException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SUCCESS_LARGER_THAN_POPULATION_SIZE, lower, lower, true);
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 8 of bug id Math2
### Patch Diff Hash-SHA-256:

73d7ec287640ebd2e71bff38bf055c6ca8f3bc6835e598cebfdbb821e19979ca

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/AbstractIntegerDistribution.java	
@@ -56,7 +56,7 @@
 			k = 1.0 / k;
 			tmp = mu + (k * sigma);
 			if (tmp < upper) {
-				upper = ((int) (java.lang.Math.ceil(tmp))) - 1;
+				k = org.apache.commons.math3.util.FastMath.exp(((mu + tmp) - sigma));
 			}
 		}
 		return solveInverseCumulativeProbability(p, lower, upper);
```


---
## Patch 1 of bug id Math5
### Patch Diff Hash-SHA-256:

5934ee3d118acb4e3c4818d81bd648af32eebcd4b3624ede12c6d31bebacc69e

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -119,7 +119,7 @@
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
## Patch 2 of bug id Math5
### Patch Diff Hash-SHA-256:

e68ea76406a1925af695123b16973633e3a9ada18502912a37fbc84f74824261

### Patch Diff:
```
--- /original/org/apache/commons/math3/complex/Complex.java	
+++ /fixed/org/apache/commons/math3/complex/Complex.java	
@@ -119,7 +119,7 @@
 			return org.apache.commons.math3.complex.Complex.NaN;
 		}
 		if (((real) == 0.0) && ((imaginary) == 0.0)) {
-			return org.apache.commons.math3.complex.Complex.NaN;
+			return createComplex(((real) + (INF.getReal())), ((imaginary) + (INF.getImaginary())));
 		}
 		if (isInfinite) {
 			return org.apache.commons.math3.complex.Complex.ZERO;
```


---