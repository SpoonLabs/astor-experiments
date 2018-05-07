
# Patches of Math81 from Defects4J 
Total patches 15
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