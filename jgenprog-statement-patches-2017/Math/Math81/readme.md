
# Patches of Math81 from Defects4J 
Total patches 37
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