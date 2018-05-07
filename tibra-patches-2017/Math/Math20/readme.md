
# Patches of Math20 from Defects4J 
Total patches 6
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