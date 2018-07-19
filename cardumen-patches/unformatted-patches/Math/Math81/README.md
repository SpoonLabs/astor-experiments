
# Patches of Math81 from Defects4J 
Total patches 676
## Patch 1 of bug id Math81
### Patch Diff Hash-SHA-256:

8b05dff856f29263a4c9b56c860c96dbc46729bb9cb7499dd0e9368d19083b16

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (deflated > (pingPong)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math81
### Patch Diff Hash-SHA-256:

dd0fe29aa6dad8114f7edecf7681cccfa4b8c47faad417caa97dca6a6c793bf7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) < end) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math81
### Patch Diff Hash-SHA-256:

b03775038e5ee1ce3c611ed4e9292bbcc846c43406cf6391f2e623be18dc564b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((transformer) == null) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math81
### Patch Diff Hash-SHA-256:

780a83625c04c1e8de7bbcb262e427640b113e6d4a2ad24cfb428bf67ddfb1fd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dN2) > 0.0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math81
### Patch Diff Hash-SHA-256:

aa77370f650e80ba68c8fb1a37bc1aecdb8b5106702b1d905c584c2ff2853872

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < (4 * (end - 3))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math81
### Patch Diff Hash-SHA-256:

8153c297fe7c0f96c9c49edfa3b64af45a277ce6c7185e11ab354fb40bdf7ae3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((TOLERANCE) < (sigma)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math81
### Patch Diff Hash-SHA-256:

291badddf06da71d8f4f13e5f60b8c33f96bd2629b8ea97e495d057904cc1fab

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((dMin2) == (dN2)) && ((2 * (work[(nn - 5)])) < (work[(nn - 7)]))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math81
### Patch Diff Hash-SHA-256:

b1f29b87d0bdc0ec67886508e618cd883dd58dddc0084ad90e0fd94b7ba2fd46

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((tType) == (-18)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math81
### Patch Diff Hash-SHA-256:

a698f1ba7afa2512c20facb62672fd55bb844e499016aab72eeffc0914c4399a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (start < end) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math81
### Patch Diff Hash-SHA-256:

c05053c8a6ec8a8e12e3c5e950853363a58125e92ee51103ab3973be714f3266

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[(end - 2)]) == 0.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math81
### Patch Diff Hash-SHA-256:

b245f218eb5cf6aaa210bccf6467bed66603136391b2083965ac8291ddae98da

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((tType) - 1) >= (nn - (pingPong))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math81
### Patch Diff Hash-SHA-256:

f1590018babd971617d4584984418e704eb9e4f8b40782ffab9de8c71fa72384

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((cachedV) == null) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math81
### Patch Diff Hash-SHA-256:

f63bef82cf9ac9153a676b9bc5e92cbfe3c98fb94f903901b853e8b631f169c6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (np <= deflated) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math81
### Patch Diff Hash-SHA-256:

361c0fcabbbeaba4d22af1003acb32810a1125cf11ddc135b67da17002dbf57c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (end < ((4 * (pingPong)) - 2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math81
### Patch Diff Hash-SHA-256:

cd84d6d57d68da0a1d47c18578b48045931b6a02a03171153f88e01b2c7bf367

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (end >= deflated) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math81
### Patch Diff Hash-SHA-256:

c035d19f0a3c9e6c90cee3359df75278d2533e0ad33aa423b891982697f4a2cc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * np) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math81
### Patch Diff Hash-SHA-256:

838c6b0155103172caf809342364630df7683278522fa9b0563c077b9a7688ae

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (nn < (nn - 1)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math81
### Patch Diff Hash-SHA-256:

022719959a426d29c9a671463cc0e7d3b21562df78fcd0a198f32d59a9dadb94

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[start])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[start])) < (work[((pingPong) + 2)]))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math81
### Patch Diff Hash-SHA-256:

eff3aed64b9173316e6421270bcfbb9d15e006ad981716202dbdefaf4be884c6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math81
### Patch Diff Hash-SHA-256:

8154d0dc374a15327154dcb6360ffda8db778a745a0d897607d0bdecbafe5b57

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (nn < 4) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math81
### Patch Diff Hash-SHA-256:

4725a9d8bcbe01334905796f320161109d9c2de85ce07cbbdec66c0c4d6d2933

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (end == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math81
### Patch Diff Hash-SHA-256:

8d3b6b0daa4fd60813fe94877ced9a4cd68ecd1d41eec7e388f2344cac851fad

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((np * deflated) <= 4096) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math81
### Patch Diff Hash-SHA-256:

dddc502922454661e1210f6068af9bdc3cb941e67175d39241a3670968ce7ef0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((qMax) > 0.0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math81
### Patch Diff Hash-SHA-256:

d3d59c440b88975d1780efb5a0700836ed692999fada01f354b46f42e2e5549d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((tType) < 4) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math81
### Patch Diff Hash-SHA-256:

6bffc370d315992bed219ec6aeef8f2787057208e481eb347665fc314cd9aafc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((cachedVt) == null) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math81
### Patch Diff Hash-SHA-256:

4b366f5e674949c461c073f2be2fca25bd3df9b01f5635b8d2a931f952cf8e39

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (end < deflated) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math81
### Patch Diff Hash-SHA-256:

de56678f21d63aeb29f9aa03d0e8e1ae45a314b782e061dd86cd6633d6a41d7a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) == gam) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math81
### Patch Diff Hash-SHA-256:

102b74517ccc8d28b7855cd1ef3b123dbddb2bbc1a497a4fc7ee89c97b1a4e77

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (b2 == 0.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math81
### Patch Diff Hash-SHA-256:

4c8ba7accd22be5dee63ab8e66666638dfc04e87bea76822eb4c214394a3e5ff

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((work[(nn - 2)]) == 0.0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math81
### Patch Diff Hash-SHA-256:

974150d7cb0b180b92bf3969c7895e9ef4d2aca20ace081caaf4aa977f7e5c50

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) == 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math81
### Patch Diff Hash-SHA-256:

cbc3ed1cae505fd49e00ff9cb86b87269b2cea82857fb83378166ad147020322

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start == (end - 2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math81
### Patch Diff Hash-SHA-256:

cc7e9506be9628c9e51844d81e11308e1fdbbd8ca70cb7b1200a423e7ef548c7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((100 * b1) < b2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math81
### Patch Diff Hash-SHA-256:

d4b4569bd8d59851e629687fdab0cb21d4b2d7788d389b13ae73878225caef73

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (end >= (((4 * start) + 2) + (pingPong))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math81
### Patch Diff Hash-SHA-256:

e0c3c6da0672c395b0725cd539b088c01ed34cbf299e6aa7d63e260594c4b10c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) < (tType)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math81
### Patch Diff Hash-SHA-256:

0f313624d560de2947071b577b3f9082f61fab97fceee69ac6dc7850eb3b6741

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((upperSpectra) == 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math81
### Patch Diff Hash-SHA-256:

ad26ba8762f8a2ab4b53d046278ab19cefb4e410135189bf900b0005eafbcd70

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (start < (tType)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math81
### Patch Diff Hash-SHA-256:

4c72ac5964afdf7a0d0ef7bf9a39fa9addfebab5d0ab62affa69f196f2fec5cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np == (tType)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math81
### Patch Diff Hash-SHA-256:

e32081521de258ce246316d73aeee6e92abd55e90ed6a0a1ede2633687f11047

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((work[(np + 3)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (work[np]))) && ((work[(np + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma)))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math81
### Patch Diff Hash-SHA-256:

51b49a4e5f0a2e931b75186e9b5b63f5efff13d69c19899e0d2233e3fd063fd9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < np) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math81
### Patch Diff Hash-SHA-256:

e347bdeb121c9822dd9c331207701676a4c8b43767d257bf12b2272ac43d4bb6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math81
### Patch Diff Hash-SHA-256:

0cf5014dc043075a822547d2ac3963126a6edf8338d5ac95478e4c0688c24e96

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np <= 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math81
### Patch Diff Hash-SHA-256:

9cc2a97c0e319a77b2fb46d2facdd2ff8bc8b2310a7886bc1a09f650a4d57e0e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) < start) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math81
### Patch Diff Hash-SHA-256:

1e63f276480a0426581c7107ac558ddfd339859602b3e2a17f383d4aaa2bac5c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((end * deflated) <= 4096) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math81
### Patch Diff Hash-SHA-256:

55d56f8628d288d1f079d9df8c5f9317add6ecc34f8e0815f4c2db0ed1435527

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((java.lang.Math.abs(secondary[start])) <= (sigmaLow)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math81
### Patch Diff Hash-SHA-256:

134ab9cf16a260f28a6aa2551db2b153ead2ef715b1dc9d5a5a4fb83fd1db086

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start == (deflated - 2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math81
### Patch Diff Hash-SHA-256:

a0b2cc2adcb73f9585b7ccecdeba2c7f124e668c87e8dd69b2c4dd487cf2f059

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) < end) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math81
### Patch Diff Hash-SHA-256:

19041c30a083bce79bd08f6576d493dae1a7e431dd3023b93d1c6d0259a9e068

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((cachedV) == null) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math81
### Patch Diff Hash-SHA-256:

a8b7102bcf9bd37593bac5f38c406a937495e6bd80556c71501f6dcba9449fa5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (b2 > 0.0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math81
### Patch Diff Hash-SHA-256:

230b0d45aeadffec5081806ff70986e1b36a063bd1fe484a991df39c1af66597

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn <= 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math81
### Patch Diff Hash-SHA-256:

73d309ec10b80b060bd4f2603119a0fd199f0af959b4d9ca0836430602f17a09

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((java.lang.Math.abs(((tau) - (minPivot)))) > (lowerSpectra)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math81
### Patch Diff Hash-SHA-256:

229b3f6f0aae18fad02d9a3a65ca2c89c1342b9011bed71415e3f806f4ce245f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin2) < 0.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math81
### Patch Diff Hash-SHA-256:

25b7fe0c015d5ec88ac6f3fe48fd9a99a89114801ca86defb06264f00b158ad9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((countEigenValues(sigma, start, pingPong)) >= 1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math81
### Patch Diff Hash-SHA-256:

0e9cb46a7b612a279011b56b6179852b2c12b043f93ea2dfdb1b39e48f8813b1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (org.apache.commons.math.util.MathUtils.equals(eMin, dN2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math81
### Patch Diff Hash-SHA-256:

a0a31d589dd9008f1c0b308ad1a1869676db546f0eb8b5ed6077cac04dbe8aba

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((sigma) < 0.1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math81
### Patch Diff Hash-SHA-256:

0dd0681a980de0e85128c0503ddfd10343ebb55c6fc8239192371c1f5e8b5f76

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (java.lang.Double.isNaN(g)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math81
### Patch Diff Hash-SHA-256:

bed464809b43d8f78204fbc2f6f276aeb9f55cb2b93d27beae79ac280fb71377

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((minPivot) - 1) != 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math81
### Patch Diff Hash-SHA-256:

dc875fe2ee2843908a1d98e88bd607b5fa788d8f3c0d50f99e41c7e5722a85e4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((main[deflated]) >= (main[(deflated + 1)])) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math81
### Patch Diff Hash-SHA-256:

89b6c26dae081c32a07389e2f61f05d5de4e972ee5d3c630a76444916625b47f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (start < (end - nn)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math81
### Patch Diff Hash-SHA-256:

ccf6cbe6027ec1381a356be742c307e0bcaf92c07727a5319e4b488cf13a79c6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((squaredSecondary[start]) > 0.0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math81
### Patch Diff Hash-SHA-256:

87bbcc00152c36b02a5190fe629b51e3987def7d74d9edc91e8f3332ba764213

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (cnst1 >= 1) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math81
### Patch Diff Hash-SHA-256:

5dff1326f00720322f50aebc285db7f200b22e4202782ac5d59e6fa748cdf87e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) > 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math81
### Patch Diff Hash-SHA-256:

569f41882a882a7789e97ec0ad2772a1870ea340c88be837667006f66f4d3c4e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((java.lang.Math.abs(((lowerSpectra) - (lowerSpectra)))) < 1.0E-6) || ((java.lang.Math.abs(((TOLERANCE) - (lowerSpectra)))) < 1.0E-6)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math81
### Patch Diff Hash-SHA-256:

e6784dac4db061ba9a41765e8de10b3a55d92dbf6db866601cdcdfb383d555c7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (start < start) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math81
### Patch Diff Hash-SHA-256:

6b924cc93b058f6cc62fe2d75a74a30b976490e1860f2b81876c5924a36942d0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (end >= 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math81
### Patch Diff Hash-SHA-256:

f40ed64e7d811748b05d1a299730b640fcf84d375eed6c0ad5491a1350237592

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np < (tType)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math81
### Patch Diff Hash-SHA-256:

b808fd2259efb4ad65f8edaaedccc54c17b4b4948d1364045456aa9dd614b0c2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((lowerSpectra) < 0.1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math81
### Patch Diff Hash-SHA-256:

7ea1f3d83d451466053f9a25e909da6288b639474cc3c4e207165228419340c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dN) < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math81
### Patch Diff Hash-SHA-256:

891fffa28b00578d1bdfebf0af0ba6398a5956ad2356fa5e10a328029b645327

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (cnst2 < 0.1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math81
### Patch Diff Hash-SHA-256:

59a90f22ab213f5e27ac4a1b4a17d270203b27dc00c66614a5a16211010a6246

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((g) > 0) && ((g) < 0)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math81
### Patch Diff Hash-SHA-256:

cf429771acecdc4baeed0b29f0491d3b90a5918490f7c4172838aad7ea351cec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((eMin) < 1.0E-19) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math81
### Patch Diff Hash-SHA-256:

82eb067b281e4899972794b82bd059e89871ef4dc96e56161ff60e2263dccc52

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) > end) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math81
### Patch Diff Hash-SHA-256:

db23042a258f2480104c446005d7e6a987346fdc18781a8e3bc000925f6ab5e5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (java.lang.Double.isNaN(cnst1)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math81
### Patch Diff Hash-SHA-256:

c16e3fcb9e521d267661cb5cff0928209a9080319533209b378b1565a6f62d22

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((((((java.lang.Double.isNaN(TOLERANCE)) || (java.lang.Double.isNaN(TOLERANCE))) || (java.lang.Double.isNaN(TOLERANCE_2))) || ((TOLERANCE) < 0)) || ((TOLERANCE) > 1)) || ((TOLERANCE) <= 0.0)) || ((TOLERANCE_2) <= 0.0)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math81
### Patch Diff Hash-SHA-256:

114117f83d98de8bba2e56f0c5053cef05e32f15824b6e755663508def56d7a2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (np < 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math81
### Patch Diff Hash-SHA-256:

048b4b50f1822467c97bfb7208ab3a868ef1ddb3349e7ff8b836292364c230cd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (java.lang.Double.isInfinite(cnst3)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math81
### Patch Diff Hash-SHA-256:

0db695bb76b4a720b7316955c8e62b69205e14aeebd3a9f3990165b0626c946c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (np == 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math81
### Patch Diff Hash-SHA-256:

da43e29f9d75ef67ff12ee3dd398c5361a3a58e6134e96e1b812c45d0225f13f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) <= 66) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math81
### Patch Diff Hash-SHA-256:

024c80e96ca4fc3ef68473e51d7b864f54afaad96d9fdd39efa67388968b95d6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (start == 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math81
### Patch Diff Hash-SHA-256:

bddd387d135640e4ef58235cafce3cce5c3b745c8c9f685036077ba4912f67b8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((dN2) > 100) || ((dN2) <= 0)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math81
### Patch Diff Hash-SHA-256:

0deb88e7f22e7ccf93187f1e77fc814554defb8d4737e56aa039e0b772eb3a1e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) <= 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math81
### Patch Diff Hash-SHA-256:

d4fd44405bd7602056e6fe6a2e619846c7280f72eb3246643c6e8e72c1fd7e27

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((end <= 6) || ((end % 2) != 0)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math81
### Patch Diff Hash-SHA-256:

278535859b3a08af28659cdba0d602440a9946a870bc1e01605497e9745ff273

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (true) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math81
### Patch Diff Hash-SHA-256:

99d74ef6c3d426009f5b748cedcb64f2d7ffa620fed84cea38ea04f0ba62e02c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((g) <= 0.0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math81
### Patch Diff Hash-SHA-256:

4796f0d5335723ed13a0ba323ba71b6b0ed5cfe42aefbca20646b2b0b9ef672b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((minPivot) == (dN2)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math81
### Patch Diff Hash-SHA-256:

4aead6b8d96e68aaa19784d020711310db8d5401dda6993bf06653097485fc7b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (end >= 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math81
### Patch Diff Hash-SHA-256:

d7f47af425f69c92bace7adfee9e04740791c826c975b106a59050d06129c709

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((sigma) != (java.lang.Math.floor(sigma))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math81
### Patch Diff Hash-SHA-256:

620f185464855695fbebe1f127d970179a63686f185c49425654bb12d370fc73

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (start > 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math81
### Patch Diff Hash-SHA-256:

300794dc7524e39cdc328cf6c0be42322a5eccb47f2824c7492c1811645553f3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((transformer) == null) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math81
### Patch Diff Hash-SHA-256:

956ef34b777fd181641504070a1f7370e7296779c9aa10a6e9672b76a696371a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) <= end) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math81
### Patch Diff Hash-SHA-256:

119349e6286a555cf61e913ca7167e151705c10a8d9a4fe3684e9270ebf73cf5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || (((dMin1) < 1.0E-4) || ((dMin1) > 0.9999))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math81
### Patch Diff Hash-SHA-256:

c98760db58ef0e5b1a73d5a96211765406519ac0b8080e8d7140b9b9ea93a51d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || (!(java.lang.Double.isNaN(realEigenvalues[start])))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math81
### Patch Diff Hash-SHA-256:

8ca9f7b776ec267d8d2c59b7e45dfea9fca974d1f440f6cb7bf17c7d2abbecff

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((pingPong) <= start) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math81
### Patch Diff Hash-SHA-256:

d5caf3283593a5352ba51f0f063dd16470baf027781e633f33b0a6619733cd42

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (end >= (2 * (start + 1))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math81
### Patch Diff Hash-SHA-256:

1e8482205eb492bfa306b024b4c7b2cafe22f72967d2334fb9094d5fcfa5fe64

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (java.lang.Double.isNaN(sigma)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math81
### Patch Diff Hash-SHA-256:

53d41029648ba0bf34f58b1075a92d99d1a43404b729533b339b7b8b0648de2d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (end < 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math81
### Patch Diff Hash-SHA-256:

3a797acc94f8fa924c08cb7ae67fc5120ca105e83783ac575ec5c9e4930f58e9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((java.lang.Math.abs(qMax)) <= (0.1 * (tau))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math81
### Patch Diff Hash-SHA-256:

38b084f2c1ed9fc4f94278714c1873e020625d618d37e2956780716fb8e9397e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) < end) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math81
### Patch Diff Hash-SHA-256:

86bd9f123639ebb0f54a27c9e8201cdc7b3e09af9c7d89a3cf509df17a02cd7c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((dN2) > 0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math81
### Patch Diff Hash-SHA-256:

7d5f21293bcc6649f5b336e64c23e618df0825f361f86667763e3d4e1b5d64c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((TOLERANCE) > ((TOLERANCE) + (TOLERANCE_2))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math81
### Patch Diff Hash-SHA-256:

619655d16e40e59f5da7170de98081f7517ac4dd694ce8d92fcd6d1f2ed0f0be

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np == 1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math81
### Patch Diff Hash-SHA-256:

ee98c3335ef9b99ac2dabacdab2ed477ffc69fa7f9844324429bdf57e16eb5e3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (np > 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math81
### Patch Diff Hash-SHA-256:

212347e96e3b2af7e0cc7f56f312e62337d7f8b8a1661d5b5094457ae2dd6bd3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (false) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math81
### Patch Diff Hash-SHA-256:

d7a43d56eb0ceee983c9409b2d82fccab2c734f5e2231c85cca318288b1e554d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((java.lang.Math.abs(splitTolerance)) <= (0.1 * (TOLERANCE_2))) || ((((splitTolerance) == 0) && ((splitTolerance) <= (splitTolerance))) && ((splitTolerance) < 0))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math81
### Patch Diff Hash-SHA-256:

8c6989b3b88540db9a473ccaa55ed562d343fb724e0f6f01ea4e644252ed3fac

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (nn == 1) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math81
### Patch Diff Hash-SHA-256:

aa743cd5bd8a2e9534050d384ed407aa838a920061beb8fdb4f9882b01de8cd9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dN1) < b1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math81
### Patch Diff Hash-SHA-256:

938f253721bda6390ffc195ad76625275508aa8d14f99a47fc008e1e8120345a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (deflated > nn) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math81
### Patch Diff Hash-SHA-256:

f36ea06828ba6f54341e4d25a67bacd9ed017bb6ddfbc4861bca40e817e16985

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < deflated) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math81
### Patch Diff Hash-SHA-256:

6a6d07b5fcf6bffc28442c369bac41f0625b66ee0d8470e40f1db91890e04b7d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) < 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math81
### Patch Diff Hash-SHA-256:

b9cbc2bc4785e3874841e879cdc41b27d2d040f5d51677e81f83a8d43a8e775c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) >= 1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Math81
### Patch Diff Hash-SHA-256:

32e56cfdd70131c155a7edebf4abe14c9883f60bb7284c622b561aa135d01c0e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) <= 1) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Math81
### Patch Diff Hash-SHA-256:

ca963c08e41242cd8e031a56cfe6c154a801f7a6598442a66b6e7b1760738bcc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (nn > 1) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Math81
### Patch Diff Hash-SHA-256:

c4ac400e215e2269b5af9727efc896f939176af551cdf13efd9337bb7d716ef7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((dMin2) < 1.0E-10) || (gam < 1.0E-10)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Math81
### Patch Diff Hash-SHA-256:

c9cceb7a2e6fb1f8087ada151ab3f607a93cc16073f476b376e4d16094c22bf6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((qMax) == 0.0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Math81
### Patch Diff Hash-SHA-256:

6e8d5ce96d96c6b9665e094dcac107b291da10ea03dea7629c2b9f72dee3c1a3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dMin1) != 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Math81
### Patch Diff Hash-SHA-256:

bfcfb32e47d7de941e40b5b979d19b6021a9d3927c67e30f06c54a63696c8b42

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((tType) < 3) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Math81
### Patch Diff Hash-SHA-256:

3e8f9da9370f6a4530dc3062679cc42b40d372a4fd65e291287fcd3cfc287eb1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (end < nn) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Math81
### Patch Diff Hash-SHA-256:

b1ee329f6f1dff664f395bbb1fef8e6368ba6b5351c92b57d8cfeb6512461938

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((splitTolerance) < 0.5) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Math81
### Patch Diff Hash-SHA-256:

17825a80015cede2aea5798d16c6f86a491f0d7caafea65b306ee06826080416

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np < np) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Math81
### Patch Diff Hash-SHA-256:

888519b6cbce16fef3c658c957cde60438423b6f23231c00d8ae68e1787b6e21

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Math81
### Patch Diff Hash-SHA-256:

f1adb6a236ffec90e75188e17dbb80a8a8111b240eae30b3a8300fed7cbbff46

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < start) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Math81
### Patch Diff Hash-SHA-256:

e8126cf5869461880e5ad28218bc64e377281563da1fe79739866d08b2c12c36

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || (start == 0)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Math81
### Patch Diff Hash-SHA-256:

b7f63a5e4879d156d1b96c5fe348a03c74e3fc46b1659d61f8a83a7382a5be78

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || (((java.lang.Math.abs(TOLERANCE_2)) <= (0.1 * (TOLERANCE))) || ((((TOLERANCE_2) == 0) && ((TOLERANCE_2) <= (TOLERANCE_2))) && ((TOLERANCE_2) < 0)))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Math81
### Patch Diff Hash-SHA-256:

e44132fc3d34a1e39bbf655bf733b42d4d2cd6c03650e4e91892a09b393be3ed

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (start != 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Math81
### Patch Diff Hash-SHA-256:

a0520a239f81d0a0395dfccc9951f5b474290f59f09dcd08c3ad8d3fc096cacb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((deflated - deflated) > 3) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Math81
### Patch Diff Hash-SHA-256:

65c5ae13526ecf5932da6adf0fe9a0cb938efd8127737500c515e3caf8b1c288

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (b1 > 10.0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Math81
### Patch Diff Hash-SHA-256:

b391b22eb223c0be35c8337a2ec6d7383496e3317484a7904078b3a4f279c188

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((TOLERANCE_2) == a2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Math81
### Patch Diff Hash-SHA-256:

470adb7f00df2067e84443531c725b9453b632372b1740a605b51ab17b7cf742

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (cnst2 == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Math81
### Patch Diff Hash-SHA-256:

5e8a2601193b7ab46a09cdc5801177c7e6c9d4616117a26b85e48b8823266dd4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((transformer) instanceof org.apache.commons.math.linear.RealMatrix) == false) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Math81
### Patch Diff Hash-SHA-256:

55169fdd2fde2a2a26edb1092516c6798416bf8d63667ef302d90b6fb7c9c0c4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((java.lang.Math.floor(splitTolerance)) / 2.0) == (java.lang.Math.floor(((java.lang.Math.floor(splitTolerance)) / 2.0)))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Math81
### Patch Diff Hash-SHA-256:

5726f3a0a5e0076052b842202f81f8f413f94edfa376fe80ab7f60623e7b96c3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (true) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Math81
### Patch Diff Hash-SHA-256:

1453bba023d123739ccdff4a6919da85fc374e191ad9b0674ff3af3bc7b7df89

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np <= 6) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Math81
### Patch Diff Hash-SHA-256:

c089bb0100138c1fae0e0cb6e3453d9a2a671779a00d50e0fce8db71d8c1a2b3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (start == 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Math81
### Patch Diff Hash-SHA-256:

e69aaac7858218b294d3714b365e5938eea147909d97c078d38e077f7356a26c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dN1) >= (dMin1)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Math81
### Patch Diff Hash-SHA-256:

50bd861c76b244c75556fad66d5831f08f026d939f7d0215ceabf9d7d38d3700

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (cnst3 <= 0.0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Math81
### Patch Diff Hash-SHA-256:

89f4d1973456dda2afd815c50e5e31d3382137edf211599b78d3e9cce138dbc7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((dMin2) < 0.1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Math81
### Patch Diff Hash-SHA-256:

dc97508c1407883420478ed8cdd7cfe63b831bcb9fb809156cb265bca1801b64

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((cachedD) == null) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Math81
### Patch Diff Hash-SHA-256:

0ee30392de1e2edea735c6e4464229e1e1c479dc56ee5b37e4641a48ed717e61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (deflated >= 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Math81
### Patch Diff Hash-SHA-256:

343c9dee396d49060ef50389c824591270927650b090d1546370f4db68fe759f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((((TOLERANCE) < (TOLERANCE)) && (((TOLERANCE) - (TOLERANCE)) > (0.95 * ((TOLERANCE) - (TOLERANCE))))) || (((TOLERANCE) > (TOLERANCE)) && (((TOLERANCE) - (TOLERANCE)) > (0.95 * ((TOLERANCE) - (TOLERANCE)))))) || ((TOLERANCE) == (TOLERANCE))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Math81
### Patch Diff Hash-SHA-256:

ff74ba083b387409929dffb2a2539bd61ca260d0c033da06102e66b190b4862d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (deflated == 31) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Math81
### Patch Diff Hash-SHA-256:

30af6730265d8672a803f54a7969bb2e8a5658156d2cbd73684f2b54f4c9bde7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (java.lang.Double.isNaN(imagEigenvalues[pingPong])) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Math81
### Patch Diff Hash-SHA-256:

538e44bf9092b15eb275cf9e70401c224622dacfc656718397e951fb4559e1aa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated < (start + np)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Math81
### Patch Diff Hash-SHA-256:

9591fe3ce37edbddafd7eb0cb0c3e268bf632d6bf32ccfac7a3cf9816ebacaf3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((imagEigenvalues[pingPong]) <= 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Math81
### Patch Diff Hash-SHA-256:

ed2e5b9ffb715d734a738be2eb17687d15cf070b561e5f5f321ea96f59a86e35

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (b1 < (minPivot)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Math81
### Patch Diff Hash-SHA-256:

fd0fa62981ef67ae82ad5f5bfc9e5d87ee260651cf5c9d71e8ea89044e6baf97

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) < 3) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Math81
### Patch Diff Hash-SHA-256:

625241ee61a8f19cbb80ae007fcd482fab71c15327370f109cc7c76422c6fbad

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) <= 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Math81
### Patch Diff Hash-SHA-256:

bc2773ffa28ab38dc8ff43c1b8cc1f54a867e4f7adc4262a5e596b98c8271594

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dN2) >= (lowerSpectra)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Math81
### Patch Diff Hash-SHA-256:

8cc964e4640342e6009d801a797ee7dd3e7c437fe042d5cdf55b594f98eaf9e2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((cachedVt) instanceof org.apache.commons.math.linear.FieldMatrix) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Math81
### Patch Diff Hash-SHA-256:

4839faecf1e4aa816af3223b699af43c3cd9b6b56ff5f76525b6c5fd0b6fc7f4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Math81
### Patch Diff Hash-SHA-256:

57b32318a510f2567e3d507c2ba4afca594cedba63e986e0f637f14ae55d9d37

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (a2 < (sigmaLow)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 150 of bug id Math81
### Patch Diff Hash-SHA-256:

6ba1a103b04d74a7bcfa81a07d26eb79ddb936e330eb269f6c15408127f6765f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((cachedD) instanceof org.apache.commons.math.stat.descriptive.AbstractStorelessUnivariateStatistic) == false) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 151 of bug id Math81
### Patch Diff Hash-SHA-256:

55c68bad86c216070a5f8819989e905741f453ec87b555e1cd47c957ebb514f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Math.floor(cnst1)) == cnst1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 152 of bug id Math81
### Patch Diff Hash-SHA-256:

083ee9a4296b64536c9c83f5c8c1cab4fdb9d7f196521738029ef7970cb22f04

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (nn >= (java.lang.Math.min(nn, pingPong))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 153 of bug id Math81
### Patch Diff Hash-SHA-256:

1a23220cef6383e24b1179083935b0f2a00d39ef2e275eb4e245aff08a83ed7b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (end == 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 154 of bug id Math81
### Patch Diff Hash-SHA-256:

1c1138245a00b3c3ebda7bbecbb0f9c5feef4f1e45d0dcdcc95c8c1f492260e2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((cachedV) instanceof org.apache.commons.math.linear.FieldMatrix) == false) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 155 of bug id Math81
### Patch Diff Hash-SHA-256:

740205355a43ff6a856974205ef5d5fc677f7aed6d3b822dff16c880a899a650

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((start <= 6) || ((start % 2) != 0)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 156 of bug id Math81
### Patch Diff Hash-SHA-256:

0793f2bcea66eb4e7d681ac8d39ad09cb89aa401308d7ec070f20cb4c6b123a7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (end == 1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 157 of bug id Math81
### Patch Diff Hash-SHA-256:

f8e18cc225e7a188db334bd49d942bee8ec8c5c1562ad1bb5fe1458125830144

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (java.lang.Double.isNaN(a2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 158 of bug id Math81
### Patch Diff Hash-SHA-256:

ee97e907be1913031403ffd1cfd2b1974602df10a1758998bde09210cf6abd7c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) <= (4 * (nn - 3))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 159 of bug id Math81
### Patch Diff Hash-SHA-256:

31a0103a2210e925bb638375c96fc54629eb53410c68a07bfe87002cdee3387b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((cachedV) instanceof org.apache.commons.math.linear.FieldMatrix) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 160 of bug id Math81
### Patch Diff Hash-SHA-256:

eae14a3c87cf69074bd9d9054d4d3010794fbeeba421c3285c5d2ae879f3665d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) - end) > 3) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 161 of bug id Math81
### Patch Diff Hash-SHA-256:

a98212ca17784fdb478bb977c8d73367286f0cfaf9896679724b12be35630156

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Double.isNaN(qMax)) || (java.lang.Double.isNaN(gam))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 162 of bug id Math81
### Patch Diff Hash-SHA-256:

b663a1769734765baacc1153b20c1c8431123200adb8f6d836f88024d792c1d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (java.lang.Double.isNaN(qMax)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 163 of bug id Math81
### Patch Diff Hash-SHA-256:

64a93c935ca74d3c881e25b1f5ad659f2e3d75b9c52f5d3e4575cac2594092d8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((java.lang.Math.abs(s)) > (TOLERANCE_2)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 164 of bug id Math81
### Patch Diff Hash-SHA-256:

5edc88b1894b4b6b5699e94465d39232a9fb804ac5e76c7a787181764809976e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 165 of bug id Math81
### Patch Diff Hash-SHA-256:

19849c15dbd0b92c87368c657a581ff1961839d607a3ec8c7248af45e082952b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((g) > 1.0E15) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 166 of bug id Math81
### Patch Diff Hash-SHA-256:

63c5817c9c67effbe7d297dbdc113354e4fabd512d311ba1d45524aa1a9100dc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((minPivot) > a2) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 167 of bug id Math81
### Patch Diff Hash-SHA-256:

4c9385cd0015671ce1f9edc8ae2500ed41d95a292996233cc5203727042862fc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((g) < 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 168 of bug id Math81
### Patch Diff Hash-SHA-256:

062c7d7f0f0119ec54b71d509a52eeb83af8976d3c33353096dfa88386a5c1a5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (start <= 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 169 of bug id Math81
### Patch Diff Hash-SHA-256:

bdeb40d6f7091062fbbe2b36bf60da8a64ef26a6ffb1e49ca7ad784bd1cfd1e8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin1) <= cnst3) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 170 of bug id Math81
### Patch Diff Hash-SHA-256:

e91adf5e1086872c91f2206a64af95f684127bca9ccd7736af3628e14cbdb8c8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (!((cachedVt) instanceof org.apache.commons.math.stat.Frequency)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 171 of bug id Math81
### Patch Diff Hash-SHA-256:

24ae825b9604fc43ab1b0f0ebaee12c84d1e889784c51f9bad8df4773e783333

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (start >= 0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 172 of bug id Math81
### Patch Diff Hash-SHA-256:

e1282731b406b325c377f076aaba8c17d7f1e9a429d5697467b80eee1361b98d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((tType) == 1) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 173 of bug id Math81
### Patch Diff Hash-SHA-256:

08d79cce54ac5293bb510d2ef8974c6a563f0493840f6453b346b15ffee7c997

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((cnst3 == 0.0) && ((TOLERANCE) == 0.0)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 174 of bug id Math81
### Patch Diff Hash-SHA-256:

d26accbb8360d656e633a7784db06dd5bcd50b6ce0041640b8000ec2492f660f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((tType) < 0) || ((work[(np - 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 175 of bug id Math81
### Patch Diff Hash-SHA-256:

83356ba6085f4038045daad197410b91d2837718f6b6b099c5b57521e928aa85

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((sigma) >= (dN1)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 176 of bug id Math81
### Patch Diff Hash-SHA-256:

8e035a664b88c831448befcdc185541c923a9230ca199e852479f1d432262973

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((pingPong) == 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 177 of bug id Math81
### Patch Diff Hash-SHA-256:

5c8465544733d21ff2efc301d93e899f2a07612a9d80952dbf654f9432887e1d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((deflated < 1) || (deflated < 1))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 178 of bug id Math81
### Patch Diff Hash-SHA-256:

af0152cf7adb9d5b87afa2169fbbd93e1a18378cdc9aee99b70d7ac2fc54ac98

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (true || ((dMin) == (dN1))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 179 of bug id Math81
### Patch Diff Hash-SHA-256:

4c621e268f78be8ff2cf2a5651800ceb4c1b9a76a0b970128d19f4a9faf3c13f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((splitTolerance) > 0)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 180 of bug id Math81
### Patch Diff Hash-SHA-256:

a19188cdacb891f26eff03dd81ce88a35861486138fc8e53680f6304eb44deda

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((dMin1) >= (qMax))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 181 of bug id Math81
### Patch Diff Hash-SHA-256:

d33cee34483f3536d2645171abe28bdef72aaacbfe4f25eda0b00d003a1b28f4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((org.apache.commons.math.util.MathUtils.sign(s)) + (org.apache.commons.math.util.MathUtils.sign(lowerSpectra))) == 0.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 182 of bug id Math81
### Patch Diff Hash-SHA-256:

443b37dc452973014d54d0726d6d84090b0e9cb13a457e89e3cd99fea44c7396

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((work[0]) != 0.0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 183 of bug id Math81
### Patch Diff Hash-SHA-256:

0b6eeea3512179cbe383748d803b95fa17cd6f73feecaa3f420093d96cebff86

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((java.lang.Math.abs(((dN) - s))) > 1.0E-5) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 184 of bug id Math81
### Patch Diff Hash-SHA-256:

9dc0bcf45a6182ffce54303db2d4fb634cc86a45aa5f244e6873c4d05425affd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (cnst1 == 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 185 of bug id Math81
### Patch Diff Hash-SHA-256:

ae8d27b8b960b38216bad94dded35a364989582e784f27ceed877f13ab339e7b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((tType) == 1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 186 of bug id Math81
### Patch Diff Hash-SHA-256:

7f9692bec58891f1e1f2cc9eee4e789e3d10a7754129b454211ce1950fd0b0a9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((pingPong) > 1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 187 of bug id Math81
### Patch Diff Hash-SHA-256:

0ea51717a80c8da8dd88a6c7275e5a35a68846b82f46fe731c8260fc012fe2bb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (deflated > 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 188 of bug id Math81
### Patch Diff Hash-SHA-256:

1ec04a44fc4d19ccf7940c23088a107b9953990f74828a21aea5e99d4c082626

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((pingPong) == nn) || (nn == 0)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 189 of bug id Math81
### Patch Diff Hash-SHA-256:

b188e880f6bd0eb85770db889cfd9f87b46f342f45b7ca2a023a2b9c12d9c594

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (end != end) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 190 of bug id Math81
### Patch Diff Hash-SHA-256:

824d7a42fb0e201ba67521d2de8492de78cd41c1dabac66fcaac5442435086ce

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((upperSpectra) >= (TOLERANCE_2)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 191 of bug id Math81
### Patch Diff Hash-SHA-256:

de7a07a871aa73f9f557ea660d7743afb95fbe5d92558d6e3d78e04283855f7d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((TOLERANCE) > 1.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 192 of bug id Math81
### Patch Diff Hash-SHA-256:

c419805150aa48c6a9945157cb8e154ba608264c22ca37ba7a9378e56625f11e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((nn - np) > 3) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 193 of bug id Math81
### Patch Diff Hash-SHA-256:

5db55f83f664285721bae6dc0a5da5546a9a7469de680b55ef85c89113f1446d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((pingPong) * (pingPong)) <= 4096) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 194 of bug id Math81
### Patch Diff Hash-SHA-256:

8974eb9a21bec04746466f64e1fcd71284c99da80e9871d9e81303cc530fe3c8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((end == end) && (end > 1)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 195 of bug id Math81
### Patch Diff Hash-SHA-256:

d1f9af828eea1f3d9b91054a30b9381506e6e1122d091646059fb33fae9178eb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((gam == 0.0) && ((sigmaLow) == 0.0)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 196 of bug id Math81
### Patch Diff Hash-SHA-256:

a8a8e12ede3e2365ea572b7afbfe71a3a19c0dca6cf4945558b849015811e7c8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((upperSpectra) <= 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 197 of bug id Math81
### Patch Diff Hash-SHA-256:

bce9d8fa29196578bd3ea87bdb189732e80dae39d55376322e247810a9362394

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start > 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 198 of bug id Math81
### Patch Diff Hash-SHA-256:

853108d9a4c4ad1ca76cef8a2499e9ad4c2f8e5df9f16239024f25a247a7563d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (gam < (TOLERANCE)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 199 of bug id Math81
### Patch Diff Hash-SHA-256:

701390d2f9a1b9c0528bbf7707526c58c81de6ad19a720ea7efc77b0dfe18b05

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) != (pingPong)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 200 of bug id Math81
### Patch Diff Hash-SHA-256:

4063c77c9f094f98279ca542876e79d48b6a0707fbfc17f4db052cc0b5ff6725

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((tType) < (deflated + (tType))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 201 of bug id Math81
### Patch Diff Hash-SHA-256:

10cc58abccbc5d9b9afae70f24f909ba2e00893eb1ef66446578af86fde5d320

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((secondary) == null) || ((work) == null)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 202 of bug id Math81
### Patch Diff Hash-SHA-256:

d36a0016d32f8885c33104f2657e64c769d50e093c81a29f4223686631a08ae4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((cachedV) == null)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 203 of bug id Math81
### Patch Diff Hash-SHA-256:

2b3969c06d7302213dbf16d314d0039a9759eb7ed882a497c663147879bc3f07

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((lowerSpectra) < 1.0E-10) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 204 of bug id Math81
### Patch Diff Hash-SHA-256:

72171eec93d80639854334e327a40ab023e7ab063d6767a11fa0e7040d74219a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 205 of bug id Math81
### Patch Diff Hash-SHA-256:

c56c08afbb3b22bad58cafae746e28f5280e40c2ce5607624861d93bb41c099f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((TOLERANCE_2) <= 2.0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 206 of bug id Math81
### Patch Diff Hash-SHA-256:

291e1f0374b3bf248f3a466162d1f71c412982f044bf34cf6d5d08871af9daef

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((lowerSpectra) > (splitTolerance)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 207 of bug id Math81
### Patch Diff Hash-SHA-256:

7a2a894062da173d318e7dac697d15e01b5003c2ad11b313a641357bf3422229

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (false) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 208 of bug id Math81
### Patch Diff Hash-SHA-256:

6b6c2bb68af3de33a4a24dab7aca69d7c77a7cc9f77816b07cdb3ed7ca3d29fc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((eMin) <= (0.1 * (dMin1))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 209 of bug id Math81
### Patch Diff Hash-SHA-256:

4195f75057c8dac13d21ecf3ff3fe79ca6c0064e72b824f5be24633e184ccfa2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (start <= 0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 210 of bug id Math81
### Patch Diff Hash-SHA-256:

4661b6a6549aa6f45dfb2eff2c15478dab9f766633d378f3d9610659ae3a8dff

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin) >= 1) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 211 of bug id Math81
### Patch Diff Hash-SHA-256:

01b96f33f09b3a142de4a6250b730a27eafe19d2ddfc9fdfb02e3ea65648a087

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -898,7 +898,7 @@
 		final double cnst1 = 0.563;
 		final double cnst2 = 1.01;
 		final double cnst3 = 1.05;
-		if ((dMin) <= 0.0) {
+		if ((java.lang.Math.abs(dMin)) < (tau)) {
 			tau = -(dMin);
 			tType = -1;
 			return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 212 of bug id Math81
### Patch Diff Hash-SHA-256:

8620c2e12ee756fb0b6ebed11e9f104f882a3e61bf7ecb8451061deac655429e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Math.abs((gam - (dMin)))) > 1.0E-5) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 213 of bug id Math81
### Patch Diff Hash-SHA-256:

e9fb64259bacd36026b2534360171a31088b7d0a5de7786c465a74cbbbe57211

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -630,7 +630,7 @@
 				dMin = -0.0;
 			}
 		}
-		if (((dMin) < 0) || (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (qMax)) < (java.lang.Math.min(work[(l - 1)], java.lang.Math.min(work[(l - 9)], ((dMin2) + (work[(l - (2 * (pingPong)))]))))))) {
+		if (((lowerSpectra) > 100) || ((lowerSpectra) <= 0)) {
 			computeShiftIncrement(start, deflatedEnd, (end - deflatedEnd));
 			for (boolean loop = true; loop;) {
 				dqds(start, deflatedEnd);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 214 of bug id Math81
### Patch Diff Hash-SHA-256:

ec3e1902255cf45a42fe09aa7be4c0d99b9ce82f3cc16cd8022abe3b21f837e8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((java.lang.Math.abs(splitTolerance)) < (java.lang.Math.abs(((0.5 * (tau)) * (tau))))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 215 of bug id Math81
### Patch Diff Hash-SHA-256:

e5c7940348846a05cc1486c70fc61d4919ae4099d3ad917635a950d5ddaeb05f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((work) == null) || ((secondary) == null)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 216 of bug id Math81
### Patch Diff Hash-SHA-256:

6a344ebb57827f5a4c1c33d3448c77e699d9f95cb4bf22f280a99d785feb8996

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((secondary) == null) || ((realEigenvalues) == null)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 217 of bug id Math81
### Patch Diff Hash-SHA-256:

b9e317005c2ddfd38206874bc06d8e7bbb145f8cf44dd519ec2e1c78bcb9d7d0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (nn > 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 218 of bug id Math81
### Patch Diff Hash-SHA-256:

44c55ae886522b0df81ef5026568f72528771ad468838776f1322568a58083c9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((TOLERANCE) > 0.5) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 219 of bug id Math81
### Patch Diff Hash-SHA-256:

6049077d38b35f564fefc5cba82fcdd8c4358baeade37c8dbd256e18d1a74484

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((cnst3 - 1) != 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 220 of bug id Math81
### Patch Diff Hash-SHA-256:

1101c2372c22217d2b58a9f722b59ef122f0ea8790c543d1eb124dcebca19c10

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated == deflated) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 221 of bug id Math81
### Patch Diff Hash-SHA-256:

6f3f5247c1b307397bff6b55a8944ce581db9aa8bf60e28ec101a6fdb8b4240e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((TOLERANCE_2) >= 1.0) && ((splitTolerance) > (TOLERANCE_2))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 222 of bug id Math81
### Patch Diff Hash-SHA-256:

5897245da4313ef0dcc19475aab7e17bc123e7bb626f11f5f457538a30ac8030

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Math.abs(a2)) < (java.lang.Math.ulp(1.0))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 223 of bug id Math81
### Patch Diff Hash-SHA-256:

c043d66ae370f4d61d51585968c1cdb972e8f5d4755a0ca3dc5e6e27b2311532

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (false) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 224 of bug id Math81
### Patch Diff Hash-SHA-256:

f6a14e720003890bea04a232ead8dd356437804ec9d8db4ef90fba27fe3d041c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((java.lang.Math.abs(splitTolerance)) < (java.lang.Math.abs(secondary[pingPong])))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 225 of bug id Math81
### Patch Diff Hash-SHA-256:

6b583cfc7353c8c37a391ed565a6bb252805caedbf4736b41990805759b9084c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((java.lang.Math.abs(TOLERANCE_2)) < (java.lang.Math.abs(((0.5 * (TOLERANCE_2)) * (TOLERANCE))))) && ((TOLERANCE_2) < ((TOLERANCE_2) * ((TOLERANCE) - (TOLERANCE_2))))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 226 of bug id Math81
### Patch Diff Hash-SHA-256:

8dbe5b5e37398f7065bd39dd63bf1b08ad82f255acf370b126f90765bc9a1009

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) <= deflated) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 227 of bug id Math81
### Patch Diff Hash-SHA-256:

65bfae726d6ccf2f6f9efd56d3f34e03cf1048402b72afee2c9830ed89d62469

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (!(org.apache.commons.math.transform.FastFourierTransformer.isPowerOf2(pingPong))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 228 of bug id Math81
### Patch Diff Hash-SHA-256:

e4d586d1272401f0c39aedbcddbcd4394c304a23734b06ccfa01400f61cfdd59

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((tau) < 0.1) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 229 of bug id Math81
### Patch Diff Hash-SHA-256:

09f09783101f7f81e40165c2d8365d664e5b67d8515f4324834690dfd2cce533

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((splitTolerance) < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 230 of bug id Math81
### Patch Diff Hash-SHA-256:

7c58b196b571d73a4184f75bcea8943d2ae3b7debe640a9b0cce71b6fa00549c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((pingPong) & 1) == 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 231 of bug id Math81
### Patch Diff Hash-SHA-256:

e7e6dac4a41824525127bcdc594cb92beb9703adc3ef8ed23e51bc005f919bf2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((eMin) < 1.0E-4) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 232 of bug id Math81
### Patch Diff Hash-SHA-256:

8f3cd14b2beca6283f3f9f3f41f80e28cf65b4fe75eb631e016eaaff8eca9a4f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (java.lang.Double.isNaN(dMin)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 233 of bug id Math81
### Patch Diff Hash-SHA-256:

abd469701c9d1d273ca6329ca9b1fe71458d2e79470a32b6231c64885fe9a7e1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (deflated < 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 234 of bug id Math81
### Patch Diff Hash-SHA-256:

94595344dfc6e408d0e1b4596f70479ddd6fc45e476b64cce1f34216c6a033d1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((java.lang.Double.isNaN(TOLERANCE_2)) || (java.lang.Double.isNaN(splitTolerance))) || ((TOLERANCE_2) <= 0.0)) || ((splitTolerance) < 0.0)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 235 of bug id Math81
### Patch Diff Hash-SHA-256:

dc1d95e7434a63dc5cb05a9d1bd18c5e564563026694e861d35d072b33517e58

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (a2 <= 0.0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 236 of bug id Math81
### Patch Diff Hash-SHA-256:

06e1a55ae84398cbed7c0416205845b9e27bec113a55ca8f81cb7e2a868a3043

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((tType) == 1) || ((tType) == (np - 1))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 237 of bug id Math81
### Patch Diff Hash-SHA-256:

617798e1687c1846a61afb6c8faeb761ab3c145eb81f41dbe797105515670f2a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) < 2) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 238 of bug id Math81
### Patch Diff Hash-SHA-256:

1ce6a789db0eafaea0faf72a14976f0dca32fda386f4d801220896d5087a2e27

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (gam == (dMin1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 239 of bug id Math81
### Patch Diff Hash-SHA-256:

901b560092111ee7f58b18946dc985f008cf2c3fe5a71c25d0da1ed0c7c79f6e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((tType) > 1) && ((realEigenvalues[((tType) - 1)]) == 0)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 240 of bug id Math81
### Patch Diff Hash-SHA-256:

8b4c30f6b616a1f82197a3ec5b6f2970f1babca9b81f7296c38da335d6f44c6c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (gam >= (eMin)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 241 of bug id Math81
### Patch Diff Hash-SHA-256:

0d85915af044f9c63bd31fd85b82c2388ac124083ab8f2bd439b75b077488c8f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((upperSpectra) / (lowerSpectra)) < 0.0) || (((lowerSpectra) / (lowerSpectra)) < 0.0)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 242 of bug id Math81
### Patch Diff Hash-SHA-256:

e02753e4f907e378befc0cd3dee8cc8f11fbc53a6b340ca1c0d6e7c30becaec2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((squaredSecondary) == null) || ((main) == null)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 243 of bug id Math81
### Patch Diff Hash-SHA-256:

ef15d305b160b20c7d37807afd692f09e52c633d5143aefd0d505545793c9802

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 244 of bug id Math81
### Patch Diff Hash-SHA-256:

4e5d560d7a8a221d8c471ccfbadd068d687de6f7b911f877e2ce70cffca6a519

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dN2) >= (sigmaLow)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 245 of bug id Math81
### Patch Diff Hash-SHA-256:

430ccaa088734ec093de01a214dbe7498e2400517cb8db871a6e406508630627

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin) >= (tau)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 246 of bug id Math81
### Patch Diff Hash-SHA-256:

8c335935fa8c7b6e6a7eac92ce8cf6af988b782e1852e3ca783ef1bd0426d6a3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) >= start) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 247 of bug id Math81
### Patch Diff Hash-SHA-256:

a026c59f220d975fcddc8cbb414ad7f1ec74091dce95fc726de16cf0b9365d6d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (java.lang.Double.isNaN(cnst1)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 248 of bug id Math81
### Patch Diff Hash-SHA-256:

4f95f0190fc02088e166294449430d0408b7e0d12fdf4137419d149084e5f77b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((g) > (qMax)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 249 of bug id Math81
### Patch Diff Hash-SHA-256:

f21592e5e3450627490c2717c2bc1338bc2fa1b0f8c126799b116082dab1671f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) < deflated) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 250 of bug id Math81
### Patch Diff Hash-SHA-256:

091d2d875b8e92a04f90835bc2715ffeed8f630da60de3df13ed285f786a814f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((imagEigenvalues[end]) == 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 251 of bug id Math81
### Patch Diff Hash-SHA-256:

319889a3f1c5bd94ab42646032de44f14f118f0d0f1a7ce5be735ce5fd11b03a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((cachedVt) instanceof org.apache.commons.math.stat.descriptive.moment.VectorialCovariance) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 252 of bug id Math81
### Patch Diff Hash-SHA-256:

a802a010774bda62cac61e2205c455e06383e60d9d7902c89d840d58f8a2ad80

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((squaredSecondary[deflated]) >= (squaredSecondary[(deflated + 1)])) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 253 of bug id Math81
### Patch Diff Hash-SHA-256:

e4095a01ef12338ced7ba0ee8ad80e485f3c42b877f2d077d2c3949442aa7b55

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((TOLERANCE_2) <= 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 254 of bug id Math81
### Patch Diff Hash-SHA-256:

575abe0ee8df95c9b69a34ed58c037b59b0da97be735c004aaf47ec69c1628e0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (start == 0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 255 of bug id Math81
### Patch Diff Hash-SHA-256:

ff79c655baf136461afcfb9e46b5b7cd80065f431014163c305299a5b30c17f1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((work[start]) <= 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 256 of bug id Math81
### Patch Diff Hash-SHA-256:

2f3a9bb6511007d2d1652ce16e4bac51c99adf2f943e792efa3e60b8d50b0114

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((end + start) > start) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 257 of bug id Math81
### Patch Diff Hash-SHA-256:

cda2267ab09b9f5b86930c90908724d09f720da3749ef66f941ddbb02a72e706

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((imagEigenvalues[start]) == 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 258 of bug id Math81
### Patch Diff Hash-SHA-256:

7985839a7245ead1defd4e4be3d0b6906c92373798ee77307782b5a82ac85daa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dMin1) > 0.5) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 259 of bug id Math81
### Patch Diff Hash-SHA-256:

0d5fd4c64c87008269880123a79acffe63c58f3b9bf34e7a8530b30d40940351

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -632,7 +632,7 @@
 		}
 		if (((dMin) < 0) || (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (qMax)) < (java.lang.Math.min(work[(l - 1)], java.lang.Math.min(work[(l - 9)], ((dMin2) + (work[(l - (2 * (pingPong)))]))))))) {
 			computeShiftIncrement(start, deflatedEnd, (end - deflatedEnd));
-			for (boolean loop = true; loop;) {
+			for (boolean loop = ((TOLERANCE_2) < (-(lowerSpectra))) || ((TOLERANCE_2) > (lowerSpectra)); loop;) {
 				dqds(start, deflatedEnd);
 				if (((dMin) >= 0) && ((dMin1) > 0)) {
 					updateSigma(tau);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 260 of bug id Math81
### Patch Diff Hash-SHA-256:

720177d4a8256250c0737cb01292b226b4c42abacb71a5b671371098a7611a10

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (deflated > 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 261 of bug id Math81
### Patch Diff Hash-SHA-256:

da700f99baf45baa0ca15e9d9899b0f14af0e79f186ce79de514d127af8f1719

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((TOLERANCE) != 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 262 of bug id Math81
### Patch Diff Hash-SHA-256:

3277ac2c7b0e49229761537a5bd0f1a87157910af42aeec22ab6c62b89e82013

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work) == null) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 263 of bug id Math81
### Patch Diff Hash-SHA-256:

c490546c1e9da8d2911b738d57ef6f9a4caa6d893ea63b6b1cab4019ceec8f03

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (end < ((tType) + 1)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 264 of bug id Math81
### Patch Diff Hash-SHA-256:

7e6c95d763773f12b4bc65c5d584bb30d4260f89a40a9a09aa84affc832bf9b1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (start >= (2 * (end + 1))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 265 of bug id Math81
### Patch Diff Hash-SHA-256:

a20ac106f6ee95515f334282095192e9198329f50101eb2ea2fad640b65896e9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (!(java.lang.Double.isNaN(work[start]))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 266 of bug id Math81
### Patch Diff Hash-SHA-256:

9b12a94acba7d9b21a76713dbf2cc29d024bd3105c8513fce50934fb35586be6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((lowerSpectra) == 0.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 267 of bug id Math81
### Patch Diff Hash-SHA-256:

1678d58d39fa45da61c1c2ce2c264da08aecc8d513f1519cf6caca4aef7b5242

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) <= start) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 268 of bug id Math81
### Patch Diff Hash-SHA-256:

c40cb01b4ec3e85485b7b0d5b19ed197de630d2e64a0e7e6f1e70b294dc95e20

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (b1 > 0.5) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 269 of bug id Math81
### Patch Diff Hash-SHA-256:

cd8a9d6f1e9c7bb9d26d59a9d8cec83eca93ad43175b233616eb9c71b904df7b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) >= 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 270 of bug id Math81
### Patch Diff Hash-SHA-256:

a52c2e3763f84b8a52f7e49adff3375524d83cf35686ae964d2205cd1599e9bf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (deflated < 67) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 271 of bug id Math81
### Patch Diff Hash-SHA-256:

fa71bf26122731020ab281b88e1309f7600508c2f4fd65fda5683f626d049ec0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((pingPong) < 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 272 of bug id Math81
### Patch Diff Hash-SHA-256:

b651c3c3d20be72983924ba95d1d256e04e51dcd8a90137b44bbfc325e23dc91

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin2) > (-0.19)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 273 of bug id Math81
### Patch Diff Hash-SHA-256:

ee4065308b03bf209d279eb8655918a7aa85cd6d8aaa7ccd5d078656a249a83b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((upperSpectra) >= (java.lang.Math.abs(((0.5 * (sigma)) * (lowerSpectra))))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 274 of bug id Math81
### Patch Diff Hash-SHA-256:

cc04a4fc23668e0f653195d3673937c9494461b4b8de2e2341d55fd03f8c331d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) == 1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 275 of bug id Math81
### Patch Diff Hash-SHA-256:

919861a328035f13e63ebd92ed15963c2b5ab64880f601239c41c65853a589ea

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (deflated < 1) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 276 of bug id Math81
### Patch Diff Hash-SHA-256:

0ea4246772fa693f58735921462c2e5acce213f29b6cb9840267b371c8d72085

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) < 4) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 277 of bug id Math81
### Patch Diff Hash-SHA-256:

f770c77d496c2b6fca693c3c5f8bca0a4e02c0edd35d001081d3e311b35cd528

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (b2 >= 1) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 278 of bug id Math81
### Patch Diff Hash-SHA-256:

e28c85d24c2287ebb3cd42b62f14100a85d1d203968ce59fbffafa9f0b17f67c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start < deflated) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 279 of bug id Math81
### Patch Diff Hash-SHA-256:

9de517612c630bffb8269c41fa1f807c038ea91e27552daee3dfd78011c3e8d8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((np & 1) == 0) && (((tType) & 1) == 0)) && ((pingPong) < 31)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 280 of bug id Math81
### Patch Diff Hash-SHA-256:

6a0444bcb44bfabf8490c86f25cb21a2d91a9929e3c54cd66b30a73a4de76c18

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((cachedD) instanceof org.apache.commons.math.stat.descriptive.MultivariateSummaryStatistics) == false) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 281 of bug id Math81
### Patch Diff Hash-SHA-256:

31590940eed2d2fb6c6c0d58f8a576b5980ab388eb3894205e8971120df98b21

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((secondary[start]) == 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 282 of bug id Math81
### Patch Diff Hash-SHA-256:

26bada76ac7711634688402e1b83ad67161b35c8ff6689f12939fa2b3a834cec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dMin) != 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 283 of bug id Math81
### Patch Diff Hash-SHA-256:

cdc70fc5b17afde35e9fa9cf088459a904726cb6efc5ac4b15a6f4185202b379

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((((minPivot) == 0) || (java.lang.Double.isNaN(minPivot))) || (java.lang.Double.isInfinite(minPivot))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 284 of bug id Math81
### Patch Diff Hash-SHA-256:

31911b95dedfdb135133041e1b3e3b299a9b0b00d79f9b258bc3df8e21fb6410

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (start < (start + 1)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 285 of bug id Math81
### Patch Diff Hash-SHA-256:

329efe81eace0ae50616bcc349ba359dcf1ad2f05f23a3f092280cceaa6a178a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (org.apache.commons.math.util.MathUtils.equals(realEigenvalues[start], secondary[start])) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 286 of bug id Math81
### Patch Diff Hash-SHA-256:

7d89091c3dc007105ba1e5ae3b821bbbe8c67d09603fdde54b3581764f38f7f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tau) >= 0.75) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 287 of bug id Math81
### Patch Diff Hash-SHA-256:

137fbde22c871f22933e512ed41bbfabb41b2c7c829f5944513415e0c6787a4f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (end < 2) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 288 of bug id Math81
### Patch Diff Hash-SHA-256:

65ea57fd8247eaad4212afc153ca5c2a976fce4ae5e3f01f181b403af2b48a8a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated < 31) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 289 of bug id Math81
### Patch Diff Hash-SHA-256:

08da144d071906309c64dd9cfb9676202e99ece00b47c2a75ba7db35e17c3d78

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn == (np - 1)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 290 of bug id Math81
### Patch Diff Hash-SHA-256:

7e786595b37f8e2694fd04fa8aca2404400547c0f7439a0042114c48676dde43

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((splitTolerance) > 0.0) && ((splitTolerance) > (TOLERANCE_2))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 291 of bug id Math81
### Patch Diff Hash-SHA-256:

9e5438ca80de3b4381b6571f463b682673326e015c7c61463b51e50bcf92f44b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) < ((pingPong) - 3)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 292 of bug id Math81
### Patch Diff Hash-SHA-256:

e993e2df93bdd301c23ba83a060eeecc8f6b1d7454a33f4950814b5a2db5bdb1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((TOLERANCE_2) <= 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 293 of bug id Math81
### Patch Diff Hash-SHA-256:

d4556edb81f200dc835edc3dfb439a8dc2bf05e531c5aaa79fc17e12656ab548

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) < (-22)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 294 of bug id Math81
### Patch Diff Hash-SHA-256:

a7b8cd87a581c6dd6a67db0794bebc283d7d744461ba573c0269fd1bd22128d9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((upperSpectra) > 0.0) && ((upperSpectra) > (sigma))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 295 of bug id Math81
### Patch Diff Hash-SHA-256:

b028e7a0c6625822028e41904532fcf2e6b07a570b7d98b21d33170bfa2e4b56

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((b2 != 0.0) || ((work[(np - 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 296 of bug id Math81
### Patch Diff Hash-SHA-256:

22f5b9c92288e5ddc1febe830f2ab95cfaa6ec5cfc2e6e6664ba0fb4680efbf5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((pingPong) >= 0) || ((work[(np - 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 297 of bug id Math81
### Patch Diff Hash-SHA-256:

c234818f8b64cef299dd6b7c5fdd94f54113e10c12860d4cd08f9dded21d858d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (nn < ((4 * end) - 11)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 298 of bug id Math81
### Patch Diff Hash-SHA-256:

cf49eaf24b81c23dde61a28fc0c545403436d8732f3ca5ebd37b08b4328584da

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || ((tType) < (pingPong))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 299 of bug id Math81
### Patch Diff Hash-SHA-256:

deb829147e897cdc30d499e461a8ad4d82c46a72aa9b3d978df0571ad7a6c11f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start == nn) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 300 of bug id Math81
### Patch Diff Hash-SHA-256:

3d5a2f2afeb34a2015e453de6127acab75f96e4933e2c4aacd836abe9fbc8b3c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (s < (splitTolerance)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 301 of bug id Math81
### Patch Diff Hash-SHA-256:

84fc0ed2a092bac0ea769ccd82dbeed67febc75726ff6a18b89498888ef8f96b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((dMin1) == (dN1)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 302 of bug id Math81
### Patch Diff Hash-SHA-256:

2392d2f54f9938c28c7e7f6c22038192885aa6850602c2ea169c758a2e13f6cd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (cnst2 < (TOLERANCE)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 303 of bug id Math81
### Patch Diff Hash-SHA-256:

1dfcd0a5fb557c4c8a2a5b104981e09e1f56158e38e45f46f8f78a612fa95fbe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np == start) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 304 of bug id Math81
### Patch Diff Hash-SHA-256:

f2c907228ed1fbc6530c9464696b2a785496beb1c5d0b4a88130f4af33b540ea

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) < deflated) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 305 of bug id Math81
### Patch Diff Hash-SHA-256:

582f276805fd10a13f5254fe3d37aa4eb3c513c4330bdedebdcde2a5dbd98cbc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((start == (nn - 2)) || ((work[(np - 9)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma)))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 306 of bug id Math81
### Patch Diff Hash-SHA-256:

89aec05583ee1d8b878279af3766577ec606983043243e991647fe394e051e93

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[(nn - 3)]) > (work[(nn - 7)])) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 307 of bug id Math81
### Patch Diff Hash-SHA-256:

66242d954ed5bc07742b93758ee39873f1c3da2f29c5c7ff06e2cbd3f3ec0c6b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((tType) >= 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 308 of bug id Math81
### Patch Diff Hash-SHA-256:

4eb6f1be407d592e53287b3ec9fd4ea2982fcf1c7299a008db84158092890c9c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((dMin) == (dN)) || ((dMin) == (dN1))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 309 of bug id Math81
### Patch Diff Hash-SHA-256:

1876feef5096e9c474f6bde40a40f7f8830b0d875b4196e05641046e8e4c2c63

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (np < nn) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 310 of bug id Math81
### Patch Diff Hash-SHA-256:

5d5cb08deaa09d6746fd11ac8fb6a037cfe2cd07a2d11fd32c465553b8a1084a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 311 of bug id Math81
### Patch Diff Hash-SHA-256:

89f0b96aec708786cd72c9202416a05ea872c1a24a661f275b02f9f19e94265e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 312 of bug id Math81
### Patch Diff Hash-SHA-256:

9c29cac45e49b7197b32a43fc078828ec5b556117b3a85b3d820e07184a7680a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (cnst1 < a2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 313 of bug id Math81
### Patch Diff Hash-SHA-256:

668967b1eb9300d39b154728b357b6ddac51e57ab8c96d560fc4c53122655802

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -630,7 +630,7 @@
 				dMin = -0.0;
 			}
 		}
-		if (((dMin) < 0) || (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (qMax)) < (java.lang.Math.min(work[(l - 1)], java.lang.Math.min(work[(l - 9)], ((dMin2) + (work[(l - (2 * (pingPong)))]))))))) {
+		if ((upperSpectra) >= (4 * (eMin))) {
 			computeShiftIncrement(start, deflatedEnd, (end - deflatedEnd));
 			for (boolean loop = true; loop;) {
 				dqds(start, deflatedEnd);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 314 of bug id Math81
### Patch Diff Hash-SHA-256:

4c194a9f094c48d897cd5fb5a3b155c1f540803449856a0548c150e7023c68de

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < end) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 315 of bug id Math81
### Patch Diff Hash-SHA-256:

333ae7135d595dd4db17536e56eb6714cb10485949f4c52551d4bf10f43daf6d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) <= (tType)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 316 of bug id Math81
### Patch Diff Hash-SHA-256:

620a7f061466fe0acfd1a0baf36fbcecb0f1263c90dffd9451353c51ee6de91e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((dN) > (sigma)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 317 of bug id Math81
### Patch Diff Hash-SHA-256:

f9847ce935ecbde2f3d34d1ca63108bc84836437d6679e1318a07cb022f4c108

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[(np - 8)]) > b2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 318 of bug id Math81
### Patch Diff Hash-SHA-256:

19bc65c03825f58a83f001d5bff79a96aad0b5dd721e02283c657645fe24f94c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) < end) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 319 of bug id Math81
### Patch Diff Hash-SHA-256:

c24c8b8b2571227a5f973cd58025aabdebd1c313ad9079a80891f47b7bc9d884

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) <= (tType)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 320 of bug id Math81
### Patch Diff Hash-SHA-256:

13ae944786ea001b0339795fd0fb70fedfac069c7fe660eec8bbb476b4e33a68

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((splitTolerance) < (splitTolerance)) || ((splitTolerance) < ((TOLERANCE) * (java.lang.Math.max(java.lang.Math.abs(TOLERANCE), java.lang.Math.abs(TOLERANCE)))))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 321 of bug id Math81
### Patch Diff Hash-SHA-256:

d88d62bc090c3e27ff6e9966fd470cb2594c86fabc639013ef7b0f84ce4688b2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (nn > (pingPong)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 322 of bug id Math81
### Patch Diff Hash-SHA-256:

26f126cc3ee219c8ebbbb85bb7d0897ff0952dccaa28c7335136ffa3c26d5a75

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (end < np) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 323 of bug id Math81
### Patch Diff Hash-SHA-256:

5fdb5018ab70196860da4c161b6e62407246dbdfcedc5247f641490e70ed3e51

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (nn < 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 324 of bug id Math81
### Patch Diff Hash-SHA-256:

71f8a04cd1bcc031bd70219af4e587451fc4332711b4f306403facd35f164db9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 325 of bug id Math81
### Patch Diff Hash-SHA-256:

732e0d5aaf54a219730508f7e242f988f80489b49595cfdab6b23ea1ab395e6a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (np < (pingPong)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 326 of bug id Math81
### Patch Diff Hash-SHA-256:

4e42eda3bd49701ac7ab83de4d5bf807399c6cdeb7006041ba276ded5ce8fd05

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) == (dN)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 327 of bug id Math81
### Patch Diff Hash-SHA-256:

a93cd42d94b3abdd8c71ad970cc05eb0a74299687c48be0f204ba9c59b41535f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dN) > b2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 328 of bug id Math81
### Patch Diff Hash-SHA-256:

fdd9af2d0c962d6dc9293ac0a6fb744673d8b3f0768140ad3ddfbb4699e89caa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[(deflated + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (dN2))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 329 of bug id Math81
### Patch Diff Hash-SHA-256:

1545d7bd07d122883f971b642f03477ce988501b1cac0b65113bd36886a97ffa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin) >= 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 330 of bug id Math81
### Patch Diff Hash-SHA-256:

d3e5b6b6b025b04811e34c8a572899a5274235429e49788a9334da708044d42d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) < (realEigenvalues.length)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 331 of bug id Math81
### Patch Diff Hash-SHA-256:

ed3edda0c1cd7bb743488e4b3a68a78060035bb7aade88e1973aa6108c41fe42

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) < (squaredSecondary.length)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 332 of bug id Math81
### Patch Diff Hash-SHA-256:

fae3975cb8e6797951ed26d3d1592ab96c1818c681874d92b19a17813cd02a80

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((100 * (java.lang.Math.max(b2, b1))) < (tau)) || (cnst1 < (tau))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 333 of bug id Math81
### Patch Diff Hash-SHA-256:

7c6f1e485b43123d97b83dcfdb5987e139cb94ca5c13c648eb245ee5d0827e35

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) < deflated) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 334 of bug id Math81
### Patch Diff Hash-SHA-256:

d0f965c03f13c33a3299667c633d1425483ddf826232d28689db2b97c2b5d550

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((g) < (g)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 335 of bug id Math81
### Patch Diff Hash-SHA-256:

b7074a65815706da271e9d83b6213b269d87492cde79cc8ae5da255ed2abb49d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((dMin) < 0.0) && ((dMin1) > 0.0)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 336 of bug id Math81
### Patch Diff Hash-SHA-256:

1c5bc5308f3549431bc614673b3030df9606aa4a996da609630046575c8b55df

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((cachedVt) == null) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 337 of bug id Math81
### Patch Diff Hash-SHA-256:

75836d756b558e7c331eb4d26b991c8a924c03b7ef51d99f25c0e0c8199e307b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn == b1) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 338 of bug id Math81
### Patch Diff Hash-SHA-256:

0b3f2f768ba41a8970725a9e8874f0f28c4cd3097c3b9d4076ab1e1ebe703958

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((work[start]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (qMax))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 339 of bug id Math81
### Patch Diff Hash-SHA-256:

b144cd971ec44f92a4d4627117dd7bea69c1335dac9077f006b45e3e6ea972b8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (end < (tType)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 340 of bug id Math81
### Patch Diff Hash-SHA-256:

c65d60266015d99f527e85838a4fbbcab2c21edd341c483b040be0145727b7f1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((end - start) > 2) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 341 of bug id Math81
### Patch Diff Hash-SHA-256:

329c5c1e0afa534145ff1816e863689c62f9553800cf3d51a427465884510d1b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) <= 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 342 of bug id Math81
### Patch Diff Hash-SHA-256:

602691b0e169e582fcdcf7844f726c4b7502e83a40116ee88859abe93e3b7586

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(end + 2)])) < (work[(end - 3)])) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 343 of bug id Math81
### Patch Diff Hash-SHA-256:

51415b75262c81892ae150412886d4824f071d99d9f5c144c141b72d1945da4a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((tType) < 0) || ((tType) >= (cachedV.getColumnDimension()))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 344 of bug id Math81
### Patch Diff Hash-SHA-256:

eff05765167cef91525a1b3915653f95481df02eea73355dad2028bb878a63cf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) <= 0) || (start < end)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 345 of bug id Math81
### Patch Diff Hash-SHA-256:

77533b6fa172616f2f7832d5250b90e8ef20bb305c3438229a38cffaf23657fb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin1) == (dN1)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 346 of bug id Math81
### Patch Diff Hash-SHA-256:

44f472d4ba3c8a47a3a85fded22a1e6ae68bd6b8a35496978e0366f9b2b1594a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (deflated < end) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 347 of bug id Math81
### Patch Diff Hash-SHA-256:

917cb021b35acc9cb7536d26e9e132dc8a986e9998e9ed175c7e743c51a83cbc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (deflated < (tType)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 348 of bug id Math81
### Patch Diff Hash-SHA-256:

9e18def3660e64d9ce24bf1817852a27735a7482ff8525bf7a6d8e4e05f2e70c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((lowerSpectra) > 0.0) && ((lowerSpectra) > ((TOLERANCE_2) * (TOLERANCE_2)))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 349 of bug id Math81
### Patch Diff Hash-SHA-256:

398f631187354e25bde0a8cd6b507499771630fefb60ef972f08273235376ae3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) != end) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 350 of bug id Math81
### Patch Diff Hash-SHA-256:

62b7c87165d5542a0ec695dd2427aa48fa198a552157caf1a31e733f7b515d37

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((tType) == (-18)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 351 of bug id Math81
### Patch Diff Hash-SHA-256:

5c4a3e5085eebb8181899a76b9ee8f3cec23d55ce940dbbcf2a9e4953b2a97e6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (end < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 352 of bug id Math81
### Patch Diff Hash-SHA-256:

b2870223554246194a9e149fbe29d1264b7b38f96beb28a0382e66fa8e3bc74e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (deflated < (4 * (end - 3))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 353 of bug id Math81
### Patch Diff Hash-SHA-256:

d7407682a2a2bb5c5e19926790fd71248aab40de8f2143e573df390c557d763a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) < 2) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 354 of bug id Math81
### Patch Diff Hash-SHA-256:

83375fb382ee13a7e5ffe65cf4b753793b53d9e135d0b5e619b9588a14a1a9b2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((qMax) < cnst1) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 355 of bug id Math81
### Patch Diff Hash-SHA-256:

a619075931637b89611e6bc35aeaf5261b0b0d9028cb079a626b477bf3728201

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (cnst2 < (sigma)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 356 of bug id Math81
### Patch Diff Hash-SHA-256:

e88d19dcf74ca07e671213e9c2aee1df9dd7406bdccd66b453f2c8a47174d22d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) < (pingPong)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 357 of bug id Math81
### Patch Diff Hash-SHA-256:

00cf7e292d24d5eff0edee8e7c1b04f02bd1c6a90909967cc92942264fa8a71b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (nn == (tType)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 358 of bug id Math81
### Patch Diff Hash-SHA-256:

afec0bf504109a9f6d6cf0fc00675af296bdf493dc2b01bc5482cfa6f74da2de

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((splitTolerance) < (TOLERANCE_2)) || ((splitTolerance) < ((TOLERANCE_2) * (java.lang.Math.max(java.lang.Math.abs(splitTolerance), java.lang.Math.abs(TOLERANCE)))))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 359 of bug id Math81
### Patch Diff Hash-SHA-256:

23aa64aba969f185872cb6b717efc674b6395d82efa2e23d6970a4fb8231ae13

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (start <= (4 * (end - 3))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 360 of bug id Math81
### Patch Diff Hash-SHA-256:

dc0b6d371c4175561fa9beb1dd53e24f1ab518c5d6a65941b54a48e2a6fbf062

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * nn) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 361 of bug id Math81
### Patch Diff Hash-SHA-256:

b1c5b75e1bd8c368e8522e27e217d51cebef028ac214da3e35210e25e8ac3f48

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((sigma) < (dMin1)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 362 of bug id Math81
### Patch Diff Hash-SHA-256:

684a006ad87077a317775ca16f87ae59849b5bd68b1ccb4f6608d17c61947e1f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn <= deflated) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 363 of bug id Math81
### Patch Diff Hash-SHA-256:

fd416e14b810a60555cc97cd2764b5140853ffb04645e4ace0c5ec9883018a09

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((lowerSpectra) > 0.0) && ((lowerSpectra) > (b2 * (TOLERANCE_2)))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 364 of bug id Math81
### Patch Diff Hash-SHA-256:

fe92fa9399a905f7b0ffcf877029c851cb95d28c0556b82333d33f10ef3b3994

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((dMin) <= (dMin))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 365 of bug id Math81
### Patch Diff Hash-SHA-256:

3f3814265860c13b43878558a43e55b3539f02b5ee0e29989963ecaa25db0c1d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((pingPong) == (pingPong))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 366 of bug id Math81
### Patch Diff Hash-SHA-256:

eeafe190c9e3a8950631844fba62d539e99bc0e496fafd8756bdc79e3f04fd11

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((pingPong) < (pingPong)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 367 of bug id Math81
### Patch Diff Hash-SHA-256:

ac81bd93a57c6e99e2e37746e700f35fb3b2cacf5d00e26e3487ad7240b35cfb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || ((pingPong) >= 0)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 368 of bug id Math81
### Patch Diff Hash-SHA-256:

0c3339b54e04c90e001cd3bfb9a49f14c700dec9e16ff82db3be3874820b5caa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) != (org.apache.commons.math.util.ResizableDoubleArray.ADDITIVE_MODE)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 369 of bug id Math81
### Patch Diff Hash-SHA-256:

1c3007558a2d2b022acb22b8d5ef297655ccded2c36d140ef7ce91fe31744bb8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Double.isNaN(dMin)) || (java.lang.Double.isInfinite(dMin))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 370 of bug id Math81
### Patch Diff Hash-SHA-256:

63469017ec81760141ad354ee33ef15a321afa0590f62da80ed6a297a70d71fd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((pingPong) == 0) && ((nn - nn) > 3)) && ((work[((4 * nn) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * b2))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 371 of bug id Math81
### Patch Diff Hash-SHA-256:

f6ef56d3efc69bb12839ace96f63518e4fd0a12673b0f873f342ae24e75e46ec

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -632,7 +632,7 @@
 		}
 		if (((dMin) < 0) || (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (qMax)) < (java.lang.Math.min(work[(l - 1)], java.lang.Math.min(work[(l - 9)], ((dMin2) + (work[(l - (2 * (pingPong)))]))))))) {
 			computeShiftIncrement(start, deflatedEnd, (end - deflatedEnd));
-			for (boolean loop = true; loop;) {
+			for (boolean loop = (dMin) <= 2.0; loop;) {
 				dqds(start, deflatedEnd);
 				if (((dMin) >= 0) && ((dMin1) > 0)) {
 					updateSigma(tau);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 372 of bug id Math81
### Patch Diff Hash-SHA-256:

244e2ceff87d01471d799878269cef8400fed76d42d07e8d715737623a7f5880

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Double.isInfinite(dMin)) || (java.lang.Double.isInfinite(dMin))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 373 of bug id Math81
### Patch Diff Hash-SHA-256:

97513b825eb899aa0a3259b9a013d54209b9a72e76fcea739353531cf2257999

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((dMin) >= (-(dMin))) && ((dMin) <= (dMin))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 374 of bug id Math81
### Patch Diff Hash-SHA-256:

114d84a0a10779db90746b19dd60637f1377c17930937448fd12dfe90fd07e56

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 375 of bug id Math81
### Patch Diff Hash-SHA-256:

e621626f0e9c45e1517062341306a9fddd0d8e9f03742a08a822d2a71e5363dc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((dMin) >= 1.0) && ((dMin) > (dMin))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 376 of bug id Math81
### Patch Diff Hash-SHA-256:

715233701061f6a3272aeb1ccd6041238ad11daee46850d53ac6bc3cd3ac20c9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (nn < nn) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 377 of bug id Math81
### Patch Diff Hash-SHA-256:

d121dc1c2da659c1f3f19f5719e8c10a3d8e64f32fa5dc3aace5b21b7694c764

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) == (pingPong)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 378 of bug id Math81
### Patch Diff Hash-SHA-256:

272d719d31e8998ca65b58c5bf17ae670941e99a29d65be2aad3e8f7e355d71c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dMin) <= (dMin)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 379 of bug id Math81
### Patch Diff Hash-SHA-256:

9f2a32c247897e31fd107ff50cdd38a13aa80fef632869dbb706539b9bf6add9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) <= (pingPong)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 380 of bug id Math81
### Patch Diff Hash-SHA-256:

ca4c1a6fd1cd0767010fba407bdabf4a57219e7d1dbf9e3ed8cf43e26e456abc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -630,7 +630,7 @@
 				dMin = -0.0;
 			}
 		}
-		if (((dMin) < 0) || (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (qMax)) < (java.lang.Math.min(work[(l - 1)], java.lang.Math.min(work[(l - 9)], ((dMin2) + (work[(l - (2 * (pingPong)))]))))))) {
+		if ((pingPong) <= (4 * (end - 3))) {
 			computeShiftIncrement(start, deflatedEnd, (end - deflatedEnd));
 			for (boolean loop = true; loop;) {
 				dqds(start, deflatedEnd);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 381 of bug id Math81
### Patch Diff Hash-SHA-256:

45c592ac19580474cdb8c1b69796bf98ea1e135d89ab1d181d41e6d6696b6da3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -585,7 +585,7 @@
 	private int goodStep(final int start, final int end) {
 		g = 0.0;
 		int deflatedEnd = end;
-		for (boolean deflating = true; deflating;) {
+		for (boolean deflating = (dMin) == 0; deflating;) {
 			if (start >= deflatedEnd) {
 				return deflatedEnd;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 382 of bug id Math81
### Patch Diff Hash-SHA-256:

fc468b17148ee664ef504e1b4f048be3f388bf10c40250f4fd6156a7afae8bed

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) > (dMin)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 383 of bug id Math81
### Patch Diff Hash-SHA-256:

cbec5d06cc622cdd3c75e359869f6b83ef2e577e972ac2e2407f9f4bfc6a2105

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((dMin) >= 0) && ((dMin1) > 0)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 384 of bug id Math81
### Patch Diff Hash-SHA-256:

6d68a76ccdd124ab206c1c1d787595e07c1d87a6bbeedd3e848cc898cdbdaf59

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) < (pingPong)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 385 of bug id Math81
### Patch Diff Hash-SHA-256:

18bd4761f48221ccd0c8e1c1a23c6edcfd4662dd51bb17df5328175a673b7339

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 386 of bug id Math81
### Patch Diff Hash-SHA-256:

65bee9c3cbd192b9fda1c507e26aa23eed07fdfa29bf2d4271189cc3806a1ced

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((tType) < (tType)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 387 of bug id Math81
### Patch Diff Hash-SHA-256:

0d71117252a5a754436cc425f1fac7f47ba324c1e706e7787d923122b40d04c6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((dMin) > 0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 388 of bug id Math81
### Patch Diff Hash-SHA-256:

aea423e40b8a2ad9b707ace5639ee64c083c4ffdfec1d3e2222faca2e184651c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((java.lang.Math.abs(dMin)) <= (java.lang.Math.ulp(dMin))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 389 of bug id Math81
### Patch Diff Hash-SHA-256:

b1306f3ba9f5ce9b6ca8ceeef42a8e02c2d32db9c0e43f7ac5d31a018103ee63

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((pingPong) < ((pingPong) - 1)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 390 of bug id Math81
### Patch Diff Hash-SHA-256:

5a2a8b53456230052ec6e8313db7cbc39f7c70c12bfde3a9d7b464d91fe0d49c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((work[pingPong]) != 0.0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 391 of bug id Math81
### Patch Diff Hash-SHA-256:

65073f52f49056bebc05db006bd84309cd920c50d5b2147cc3b51f7ca75b06b9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((pingPong) < start) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 392 of bug id Math81
### Patch Diff Hash-SHA-256:

1d0b64d14e12c5d2e98439d8f0b8cf549f990cef6ad2b1e015a60168ab4e534e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (b2 < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 393 of bug id Math81
### Patch Diff Hash-SHA-256:

86ca9747155aee645c2bb633c24cb217220f2aac66e1e8a533627ab92cc468a2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((java.lang.Math.abs(dMin)) <= 2.2204E-16) && ((dMin) <= 2.2204E-16)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 394 of bug id Math81
### Patch Diff Hash-SHA-256:

2fbe004db51eb0e7e9322bb9d1eb6f7f0f51cbc616efde7627f5829fd2ca3de7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (nn < nn) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 395 of bug id Math81
### Patch Diff Hash-SHA-256:

0c33bf586c5bd9596e3c7f2c86424ce5c3de2868f2a986cb51f7e70ed477c392

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((java.lang.Math.abs(dMin)) <= (dMin)) && ((dMin) <= (dMin))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 396 of bug id Math81
### Patch Diff Hash-SHA-256:

7c519e39a7d6d44d8db6a4566c58d22fcf2c1a0f8754db8dac3ae3615a7c13e7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) <= 2.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 397 of bug id Math81
### Patch Diff Hash-SHA-256:

baa6602305267447a22a5974df0db6fb46e821fe3da0aa45635ad1557ca233b7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((java.lang.Math.abs(dMin)) <= 2.2204E-16) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 398 of bug id Math81
### Patch Diff Hash-SHA-256:

2cb9f88b757125efab4ab93107f930becdcaa8ec227363926b5f216e97046d77

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((dMin) < (dMin)) || ((dMin) < ((dMin) * (java.lang.Math.max(java.lang.Math.abs(dMin), java.lang.Math.abs(dMin)))))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 399 of bug id Math81
### Patch Diff Hash-SHA-256:

bff1dbc67cfb937a07daafe0f5f3ed8831ce1e5d90610a77441e5e1d44ec0a17

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((transformer) instanceof java.lang.Comparable<?>) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 400 of bug id Math81
### Patch Diff Hash-SHA-256:

d0334837ebce7cbca9d2fe0153e04b5f3bc308fd6a11fc9a1a2d96f2a93afcc2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (end < end) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 401 of bug id Math81
### Patch Diff Hash-SHA-256:

dacde3fea06cedc1eb0de80670408ef92f9c2fe778e77267164c7e69b634fdfe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((java.lang.Math.abs(dMin)) <= (0.1 * (dMin))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 402 of bug id Math81
### Patch Diff Hash-SHA-256:

8ca398ffe2f7b8f5d3e3f740fcee2e1597eb96e93f13c44d5d4464356afb71fb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) == 0.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 403 of bug id Math81
### Patch Diff Hash-SHA-256:

85bd0d1ab8a8930553d81adc1ae58484a82ac652737e7acf738b4eca4fc5b5ae

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) <= 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 404 of bug id Math81
### Patch Diff Hash-SHA-256:

9414256503d8b3ae98e4b84e9614b44a8d07855d49aa160f800b07a6e41e92f9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -585,7 +585,7 @@
 	private int goodStep(final int start, final int end) {
 		g = 0.0;
 		int deflatedEnd = end;
-		for (boolean deflating = true; deflating;) {
+		for (boolean deflating = (java.lang.Math.floor(dMin)) == (dMin); deflating;) {
 			if (start >= deflatedEnd) {
 				return deflatedEnd;
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 405 of bug id Math81
### Patch Diff Hash-SHA-256:

0609451e18d23315e8e32c7e1050096bd4b841db4c36059b4067d4f10d1bfca9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((dMin) < 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 406 of bug id Math81
### Patch Diff Hash-SHA-256:

3703e87c95511a227b0ce3f2adcbce4869b24d4b81b65913b12cf7d0db7b186e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((dMin) == (dMin)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 407 of bug id Math81
### Patch Diff Hash-SHA-256:

d953920a127a0c591f93ec7a669789902fca012ff4d7e85f0c9a1fa2bd4814e1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((pingPong) < (pingPong)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 408 of bug id Math81
### Patch Diff Hash-SHA-256:

13225749f180e68e248cd6dc29ab6cc8acc39aeaec4bac0ec2ad06b4cd521640

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 409 of bug id Math81
### Patch Diff Hash-SHA-256:

e680d55e6aba812d765fcacd061238939847d94fbb758c1d811f688f7602fb6d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((java.lang.Math.abs(dMin)) <= (dMin)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 410 of bug id Math81
### Patch Diff Hash-SHA-256:

d3a2bdb03cce111176a6bf090bb1dcb61803b294371674e2edbf92e1f0cfd8d0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start < start) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 411 of bug id Math81
### Patch Diff Hash-SHA-256:

8b8fed9a5866bf8ad212c79b99ea001afb6d9d1a52829de2d49ccc4180046969

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (java.lang.Double.isInfinite(dMin)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 412 of bug id Math81
### Patch Diff Hash-SHA-256:

17fae9483afe8203746eeb5eb0d18d80e77b4c29edea9e3aad6501456efc52d0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) == (pingPong)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 413 of bug id Math81
### Patch Diff Hash-SHA-256:

c4a572664be434260de1bed4f1022a3d33e928d00169e00b7c9c2c0b6cc0dbc5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) < ((pingPong) >> 1)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 414 of bug id Math81
### Patch Diff Hash-SHA-256:

119efa3f681762c401be5adc09b7b38fdf2ed505163867b864e4bb183b60af74

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (start < start) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 415 of bug id Math81
### Patch Diff Hash-SHA-256:

e676000275a475a26ff68113df796f081a2846ef147483030e5e5b6bcebe6a7d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((pingPong) < 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 416 of bug id Math81
### Patch Diff Hash-SHA-256:

86602681861dd2fce2b1d62e541a0178b9ddbdda884329faf2ee054fa9a3a78b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((dMin) != 0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 417 of bug id Math81
### Patch Diff Hash-SHA-256:

88d69bee92b84926809602eef842187c4f225d0cd81f594cd8a37c490670725d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin) > 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 418 of bug id Math81
### Patch Diff Hash-SHA-256:

ab330b1994cc81e3c6ce3109b90ec5f61c1ed2242cedc015f1ba1a879489f3c5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (start > 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 419 of bug id Math81
### Patch Diff Hash-SHA-256:

a0fda565107c70eab11db03ede7433b3853f082642210602665e1335aa9e8e2e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((((dMin) == 0) || ((dMin) == 0)) || ((dMin) == 0)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 420 of bug id Math81
### Patch Diff Hash-SHA-256:

fc9b2a9cd12fba03f5fd64eb909219f0c6415af6ccf5c20a4e6f47361c9e6036

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((java.lang.Double.isInfinite(dMin)) || (java.lang.Double.isInfinite(dMin))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 421 of bug id Math81
### Patch Diff Hash-SHA-256:

4d48b830e5608f49e14d954cb2beee134951e0188feaf2d8953c370f7e2fd228

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Math.abs(dMin)) <= (java.lang.Math.ulp(dMin))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 422 of bug id Math81
### Patch Diff Hash-SHA-256:

ce894393b988f166f14fc81caa998b58158bbdd5f9da5b7ee8fa3ffeb0e24c1e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (nn < nn) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 423 of bug id Math81
### Patch Diff Hash-SHA-256:

247be2157ca7791c808ad34ac1106fb5ca2189248467de70c277e2b6d5563fd7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) == 1) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 424 of bug id Math81
### Patch Diff Hash-SHA-256:

8904ee4d9b9a0c4ad8cd518382e1df1e5f9c4ac95790b30d51908af5a73d61a6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (!(org.apache.commons.math.transform.FastFourierTransformer.isPowerOf2(pingPong))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 425 of bug id Math81
### Patch Diff Hash-SHA-256:

0095222087b2c61d7af27af92ee487bd4b38cab65710870a40d6ea9b15d69bd5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || ((pingPong) <= 6)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 426 of bug id Math81
### Patch Diff Hash-SHA-256:

a7c9a1333a7c211208e7643d07dbebdf3f2dbd814484d8fd7bf069a4ee43e5a6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((dMin) == 0) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 427 of bug id Math81
### Patch Diff Hash-SHA-256:

ca37169a6541b3813bbc575e869879d8ea8f5170ded6560c1930c8a2377c654d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((pingPong) + (pingPong)) >= (pingPong)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 428 of bug id Math81
### Patch Diff Hash-SHA-256:

12bf624d6963acb71639b59635e6b8bdfbe49ce83efd5bf7c3a414716cac86a9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin) > 0.9999) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 429 of bug id Math81
### Patch Diff Hash-SHA-256:

2d19a63b405b9eebe6a235b6d4dfc9dc2fb498cdfb782218bb050f22dd5e2df1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) < 1) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 430 of bug id Math81
### Patch Diff Hash-SHA-256:

8dfd7dfee22e55727084f1f6cd4d88766eccaba39bc31c991c4ee50a7dffdb54

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) >= (pingPong)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 431 of bug id Math81
### Patch Diff Hash-SHA-256:

0231f40ba2595c848b76dc4a0c54a2283ed111b431f67aae058eb156d93866cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((dMin) > (dMin)) && (((dMin) - (dMin)) > (0.95 * ((dMin) - (dMin))))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 432 of bug id Math81
### Patch Diff Hash-SHA-256:

d67c45f0f4d0ea8996f3827d4fe867f30151176c95b191dcb41d432b0d0f603d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((pingPong) <= (pingPong)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 433 of bug id Math81
### Patch Diff Hash-SHA-256:

f76b4e975854912940e8122bd7b6aea2fec39203339e04d008f4b93376401127

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((java.lang.Double.isNaN(dMin)) || (java.lang.Double.isNaN(dMin))) || (java.lang.Double.isNaN(dMin))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 434 of bug id Math81
### Patch Diff Hash-SHA-256:

69c8ef27123e164251685c1dc018fcdb5ae04548ac4cd17ff378c836f630173a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) >= 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 435 of bug id Math81
### Patch Diff Hash-SHA-256:

f3d6e06cf1bf89321633801e5cd2519beb7834ca5d96202dfc3947d4e98d0aaf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((dMin) >= 1) || ((dMin) <= 0)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 436 of bug id Math81
### Patch Diff Hash-SHA-256:

8ee3aaa5347c151fa0492558db2edfb8e2424a59a27eae1384c9e50dc8e0ea11

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((sigma) < (-(sigma))) && ((pingPong) == 0)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 437 of bug id Math81
### Patch Diff Hash-SHA-256:

fd974261e538e8f85b537cb74f7e7984bd8c2549b7c0ac143409df35f6910d7e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((pingPong) > (pingPong)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 438 of bug id Math81
### Patch Diff Hash-SHA-256:

d79390cd9518854eb641237f8395fca961a3e4a151494c963bcc481d4ca42a4e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin) <= (dMin)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 439 of bug id Math81
### Patch Diff Hash-SHA-256:

13f6a287b611a610ac775912df79f0b5cd8c1b312189caaa3d2cad1a22a12152

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((java.lang.Math.abs(dMin)) < (java.lang.Math.abs(((0.5 * (dMin)) * (dMin))))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 440 of bug id Math81
### Patch Diff Hash-SHA-256:

7a47702b8481acdc6b31227aa71e90fb78e78199fb0b0592802f6f6864af11ce

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((pingPong) < 0) || ((pingPong) >= (pingPong))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 441 of bug id Math81
### Patch Diff Hash-SHA-256:

5f11b09d92048cacf9f9c0d481875bfed715528e1e918da05cd9c6d59a92082f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) == (java.lang.Integer.MIN_VALUE)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 442 of bug id Math81
### Patch Diff Hash-SHA-256:

425a1cf34caea6e839dab6ec4bede9498e63c08267c7a4188dab72aed5f5d612

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) != (org.apache.commons.math.util.ResizableDoubleArray.ADDITIVE_MODE)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 443 of bug id Math81
### Patch Diff Hash-SHA-256:

217d73c5157993304697c12f2cfcbc6a2dfc1fd5c3af0decf70898eedbc70462

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((work[pingPong]) > 0.0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 444 of bug id Math81
### Patch Diff Hash-SHA-256:

85af5b272f2a2f0d74c7e3e592ac9983ce90924ffcd42f231eb72382fe6781c0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((0.1 * (dMin)) < (dMin)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 445 of bug id Math81
### Patch Diff Hash-SHA-256:

4da7617d6bba8669df969952fad2d0b7ea9e2f12cf4499bd753849b39ed26cd3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((java.lang.Math.floor(dMin)) / 2.0) == (java.lang.Math.floor(((java.lang.Math.floor(dMin)) / 2.0)))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 446 of bug id Math81
### Patch Diff Hash-SHA-256:

9dec738937d4829249ea89b086574cd6594d303d3224ab0885cf37b2f80bd32f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((pingPong) == (java.lang.Integer.MIN_VALUE)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 447 of bug id Math81
### Patch Diff Hash-SHA-256:

847c988c1458d217eb5c1c0c0d082d7881236b1d3ad40728a72579cdf53ce13a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) == (pingPong)) && ((pingPong) > 1)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 448 of bug id Math81
### Patch Diff Hash-SHA-256:

2db3860dc404bd394a41a36e565b0d81e105df84e03017270cc28d0d6863ec50

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (true || ((work[(np - 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 449 of bug id Math81
### Patch Diff Hash-SHA-256:

2090f64c41cf7098b3cb659c8695a5c06c7b1faca32fdca49a31f19d0995a879

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((dMin) == (dN)) || true) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 450 of bug id Math81
### Patch Diff Hash-SHA-256:

fe308437877f49f718164eff296c2b3d5e7312a13765ff3bf95a1db6afad401f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) <= 2.2204E-16) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 451 of bug id Math81
### Patch Diff Hash-SHA-256:

e4c3b663d06c8ea21f4bb3eca23bcd7654fba8004043ffa0c77cc7e370b135a5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dMin) > 0) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 452 of bug id Math81
### Patch Diff Hash-SHA-256:

0a4689e762ee2412c79ac9702b45a71ba6dd197e360c139d3da21bc7f6d49644

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((((dMin) < (dMin)) || ((dMin) > (dMin))) || ((dMin) >= (dMin))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 453 of bug id Math81
### Patch Diff Hash-SHA-256:

ed2496b89c5659d25600e2f7779fb075cc421c0f34cfe13d05b6ac11bf03814e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) < (java.lang.Math.min(pingPong, pingPong))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 454 of bug id Math81
### Patch Diff Hash-SHA-256:

b567effbe430da143b913c8e48fc5061dd89f66650ed5aa05a76781effff4697

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) < 1.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 455 of bug id Math81
### Patch Diff Hash-SHA-256:

8210320fe34eecbc527b9c71056f3853683cfb940423655458f89fc2db3238d4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) % 2) == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 456 of bug id Math81
### Patch Diff Hash-SHA-256:

544b5de265e9d4982323be31e97c3df5d89960c21b9d927ad8168e2e65e81f15

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) >= (java.lang.Math.min(pingPong, pingPong))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 457 of bug id Math81
### Patch Diff Hash-SHA-256:

ff85de8f0bd9093f14ca41e7e736a910d4bf8297c3202c9b11b4ad773bde4873

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) <= (pingPong)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 458 of bug id Math81
### Patch Diff Hash-SHA-256:

cc4d51f8bb4c266ed7a530889ca412da32e460b60e3500d064411fb3330a9f9e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((transformer) instanceof org.apache.commons.math.linear.FieldMatrix) == false) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 459 of bug id Math81
### Patch Diff Hash-SHA-256:

587023ea82d96b80169cc9870b63cc4cadb4b8e039b78e502f1c504410f43a79

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (start != ((pingPong) - 2)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 460 of bug id Math81
### Patch Diff Hash-SHA-256:

d9b17abd747b3f453e525f7aa8b546b7b6839407d6d6a43c9c4cc2e399fd2976

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((pingPong) == 0) || ((pingPong) == 0)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 461 of bug id Math81
### Patch Diff Hash-SHA-256:

cf5b6494e5203b90832c142fd6bf477833a5599761e0d5bac696337edbfa1109

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((pingPong) < start) && ((work[pingPong]) >= (tau))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 462 of bug id Math81
### Patch Diff Hash-SHA-256:

7d6d1806d05a30bac7065215d7f8db49b5900fd5a16db3695b3aaa5499bcc794

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((pingPong) == (pingPong)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 463 of bug id Math81
### Patch Diff Hash-SHA-256:

0764b0a3e04ebcbb5ce02a7a044605d5365a464a724f25604d6dd71a14621c23

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((dMin) == 0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 464 of bug id Math81
### Patch Diff Hash-SHA-256:

bea1022b1270c87574c8636c5f40b1a3cdb89cdd07b3242b0be54e13461311eb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (start == start) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 465 of bug id Math81
### Patch Diff Hash-SHA-256:

38d7ff35b01798175fbbd8ae45377f2ec368a263925cded4591a7dfd25f50557

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (java.lang.Double.isInfinite(work[pingPong])) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 466 of bug id Math81
### Patch Diff Hash-SHA-256:

2545be8cfe9a63d527863f8e7d6ed5689779ca4e7e422a5bdf14d43073424c9e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((dMin) > 0) || ((work[(np - 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 467 of bug id Math81
### Patch Diff Hash-SHA-256:

c680abda92cdc0d1ee66b5917eea4b08ccc19937ced92c64e134b04376c6aca5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (np < end) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 468 of bug id Math81
### Patch Diff Hash-SHA-256:

ca23f68e3cd8353ebd428569413e61128ace90a2f3ec28874b8ae10278e94466

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((cachedD) instanceof org.apache.commons.math.linear.RealMatrix) == false) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 469 of bug id Math81
### Patch Diff Hash-SHA-256:

d9e0447285f19613ca10d77bb43f8abff0fdf034cecb4f77c3c3497105865da3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((g) < (dN1)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 470 of bug id Math81
### Patch Diff Hash-SHA-256:

3bbaf33955d2185c2af78f7d5b3037237c0330c226a060ed86ed5a745a454182

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((upperSpectra) < b2) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 471 of bug id Math81
### Patch Diff Hash-SHA-256:

eb0f1120c1e02e404f3eecfbf9406dd11d8d3284f125039a0ac201e37b9a46a1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * end) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 472 of bug id Math81
### Patch Diff Hash-SHA-256:

bd205685f2a2534461eefe40bb2c2511c13d97854771899400ebebd897482521

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated != nn) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 473 of bug id Math81
### Patch Diff Hash-SHA-256:

75cfb91b84d624d90acc80d94ff9a057fcb7c848ae39b8f9a6d94d074bee11d2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start < (tType)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 474 of bug id Math81
### Patch Diff Hash-SHA-256:

5eb1fe18b98d005ba4e10aac548ba491379a3776a8b4143e1c885dd3bbb866b6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((tType) == (-6)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 475 of bug id Math81
### Patch Diff Hash-SHA-256:

d3f20742b2e35f4a6a7be0f1e98c7f20eb082a8f928462e32c7c1a2dc9d7cd97

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[(np - 4)]) > (work[(np - 2)])) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 476 of bug id Math81
### Patch Diff Hash-SHA-256:

c9d0540db29ad3d1b5b46560c170e242c583eb5b8bb95f404242a72739671df3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (nn < ((4 * start) - 2)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 477 of bug id Math81
### Patch Diff Hash-SHA-256:

0e889151de22c4635f3ee31a681fc8d05c62c54bc91dd351d0f4fdde59d87688

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((dMin) <= 0) || (start < end)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 478 of bug id Math81
### Patch Diff Hash-SHA-256:

3ec7efa1ca7edc23d7a0727a47b6b8ec6523f6cb91e72d4f3fd448f2001ee627

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (deflated < end) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 479 of bug id Math81
### Patch Diff Hash-SHA-256:

41935fa049ae2b0ec9c21f54245e2367121285785976d0090f414cb9c50d3c92

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((tType) - 1) >= (end - deflated)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 480 of bug id Math81
### Patch Diff Hash-SHA-256:

a97d51056ea1abece6151ad23b6b4dd6f63fb786eefc27e2bb12ae01110ea7fc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((tType) < np) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 481 of bug id Math81
### Patch Diff Hash-SHA-256:

655e9b77c7d668a95b43aec53d7735b83ddf24ab6e60e9c9ddf72deb98c9fddc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((eMin) < (sigma)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 482 of bug id Math81
### Patch Diff Hash-SHA-256:

74d80a2779ec1481eea6457f354688365d6123b569d242cf8972880a077aab3a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((cachedD) == null) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 483 of bug id Math81
### Patch Diff Hash-SHA-256:

7407b237ababcfb1c4ad49026ed8601495f64477150fe7046e659169bfbac15c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((dMin) < 0.0) && ((dMin1) > 0.0)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 484 of bug id Math81
### Patch Diff Hash-SHA-256:

5c20ddeaba60c29bb045f44b06f5de5a5b76ece415dfc9780df9ddeac3011eb5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((dMin) == (dN)) && ((dMin1) == (dN1))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 485 of bug id Math81
### Patch Diff Hash-SHA-256:

2d2e9041deeda851e5488914e7d7efd42cc31c2d54fce308ecbe6c726d456db8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dMin) < (sigma)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 486 of bug id Math81
### Patch Diff Hash-SHA-256:

a7b83148caf25df48e52b4b65edc242d6ba37c0143e0e45b244f207807bef788

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((pingPong) > nn) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 487 of bug id Math81
### Patch Diff Hash-SHA-256:

40e8ef8083497051745f80b83d0c6a39a84ca4bc345e7c83c925b5d387795929

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated <= 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 488 of bug id Math81
### Patch Diff Hash-SHA-256:

44d2a5906313cf2a6c8b8e2b2f419e8985e7e086ac78da69bd07e4f4b692264e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((tType) != (tType)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 489 of bug id Math81
### Patch Diff Hash-SHA-256:

63827ddcc015b25975aa64b0cadd3db9ba44450d7b51c226b2b021555c9b3ff7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated < (realEigenvalues.length)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 490 of bug id Math81
### Patch Diff Hash-SHA-256:

2e1c956cc2145b482f92dcc72274c61e164b888f41165a33a1b2961d396084d1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((cachedVt) instanceof org.apache.commons.math.linear.RealMatrix) == false) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 491 of bug id Math81
### Patch Diff Hash-SHA-256:

f8722bca816e0144ed68e3f45e100d32b6526a790ec82cc7c3219155295a8a8d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated < nn) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 492 of bug id Math81
### Patch Diff Hash-SHA-256:

0c3973b1b79eab8261555884f475814aa7e6baa70cd53b212c69f10259d3e778

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 493 of bug id Math81
### Patch Diff Hash-SHA-256:

4fa3e6e7be1d8c7e68ef5713d0c2075f1f3415697d6ec945447a387a9a974861

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (end < (tType)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 494 of bug id Math81
### Patch Diff Hash-SHA-256:

9b5bf2aaf3d004a4cb78fc5421250e8485bd66e2efbe8815ad905497ef38fddd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) < (4 * (end - 3))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 495 of bug id Math81
### Patch Diff Hash-SHA-256:

829c87705cb2be5db6539bae6f3e51aad8f5b13da025a096075b4cedc557661f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((pingPong) < (secondary.length)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 496 of bug id Math81
### Patch Diff Hash-SHA-256:

6742f5250fd34511d0a3d6078fae6a69e5671e006b849cbaaf1b9f50d09a83d3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (end != deflated) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 497 of bug id Math81
### Patch Diff Hash-SHA-256:

1e6b0c9a56ba1ea64e4838297f0feb7045261a14da5d610f747a87aea89f573d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -797,7 +797,7 @@
 		work[(j4 - 2)] = (dN1) + (work[j4p2]);
 		work[j4] = (work[(j4p2 + 2)]) * ((work[j4p2]) / (work[(j4 - 2)]));
 		dN = ((work[(j4p2 + 2)]) * ((dN1) / (work[(j4 - 2)]))) - (tau);
-		dMin = java.lang.Math.min(dMin, dN);
+		dMin = java.lang.Math.min(898215297400035290L, dN);
 		work[(j4 + 2)] = dN;
 		work[(((4 * end) - (pingPong)) - 1)] = eMin;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 498 of bug id Math81
### Patch Diff Hash-SHA-256:

f034c146b842cbf3808b2681596c10a099553f1d84165aed24549ba96453cf39

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							dMin = dMin;
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 499 of bug id Math81
### Patch Diff Hash-SHA-256:

c073031864bac4fc484c19b80f0e2acfcc454f5c0691844f74594854524d9786

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							dMin = (dMin) + (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 500 of bug id Math81
### Patch Diff Hash-SHA-256:

59e0cd1c303012a3a264a6c0f807da99adda6feb0ac8476a2cda7295888a0f69

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -980,7 +980,7 @@
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
+						double b1 = (-1.324889724104E12) - (3.18801444819E11 * (java.lang.Math.sqrt(6.0)));
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 501 of bug id Math81
### Patch Diff Hash-SHA-256:

11680471f969219ef0e6d3bb9616c6df1eccf040d981e2da96999c7962367eab

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -778,7 +778,7 @@
 				work[(j4 - 3)] = d + (work[j4]);
 				final double tmp = (work[(j4 + 2)]) / (work[(j4 - 3)]);
 				d = (d * tmp) - (tau);
-				dMin = java.lang.Math.min(dMin, d);
+				dMin = java.lang.Math.min(1237, d);
 				work[(j4 - 1)] = (work[j4]) * tmp;
 				eMin = java.lang.Math.min(work[(j4 - 1)], eMin);
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 502 of bug id Math81
### Patch Diff Hash-SHA-256:

9750b2e83b5d19266e59b3ca05df99cd5cb48e9ef3a23ba5a3ecfbabdd0a8104

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((start <= end) || ((dMin) == (dN1))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 503 of bug id Math81
### Patch Diff Hash-SHA-256:

b6bebf93cdde80c6a8f28b36fc816f8c1ca88966f64b3c46e8a7c7eaa80f3a88

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((work[(np + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 504 of bug id Math81
### Patch Diff Hash-SHA-256:

691f2c7a00d19645f27f623c3633bdc80b29752619d2dbb04ab15eccccc06853

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((pingPong) == 0) && (((pingPong) - (pingPong)) > 3)) && ((work[((4 * (pingPong)) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (TOLERANCE_2)))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 505 of bug id Math81
### Patch Diff Hash-SHA-256:

4a2251ce63c4b11bc1f0bfbfb0ede9aff3419fe47c11b62bd03b9809b1874ccb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((eMin) < (dN1)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 506 of bug id Math81
### Patch Diff Hash-SHA-256:

424272584ee6a75b222ced206846f500d70dc8da48ea8126776d76dc36eaabea

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((tType) <= 0) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 507 of bug id Math81
### Patch Diff Hash-SHA-256:

8790feacdb16e05de68492ec9ed7047cbdb7a0fc9915aadb647adf8228650f33

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(end + 2)])) < (work[(end - 3)])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(end - 3)])) < (work[(end + 2)]))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 508 of bug id Math81
### Patch Diff Hash-SHA-256:

215e2cd5bbd27aba64da1b640129b4c0da38db66442c65ed0e3f5981923cf1e8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((dMin) == (dN2)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 509 of bug id Math81
### Patch Diff Hash-SHA-256:

d568cf0f8224a5c4aab67d217c9383ede43f9a37ebca7bc0df52406d77f616c9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (nn <= end) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 510 of bug id Math81
### Patch Diff Hash-SHA-256:

f76e8faf1abcd62e2343198c628427e37f8c4e2ac737b4be2df98cb61d66a714

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(end + 1)])) < (work[(end - 2)])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(end - 2)])) < (work[(end + 1)]))) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 511 of bug id Math81
### Patch Diff Hash-SHA-256:

b8989ff38cf529aab808c8d79e83bb75d1375a253b9bccc5c94ea8702cde934b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (end < (pingPong)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 512 of bug id Math81
### Patch Diff Hash-SHA-256:

d210a7848c1e62293e93efecbe3a44d9191f65c04338b4f5652abfc93caa9fb8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((100 * (java.lang.Math.max(splitTolerance, upperSpectra))) < (minPivot)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 513 of bug id Math81
### Patch Diff Hash-SHA-256:

87aeabf650a51acf133616ea92858e60b2a6c3799594ccfae247ae0f516fb962

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((cachedD) instanceof org.apache.commons.math.linear.RealMatrix) == false) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 514 of bug id Math81
### Patch Diff Hash-SHA-256:

2503287555c860ce4c93aef7e97edb01dc6c3b3975607794650493390d4f49d3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((((dMin) < 0.0) && ((dMin1) > 0.0)) && ((work[(((4 * deflated) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((sigma) + (dN1))))) && ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma)))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 515 of bug id Math81
### Patch Diff Hash-SHA-256:

62b1d3f783daddb6c4f7625606f32d83a701bbf27dc72ea398a1e05ecd150a6d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((tType) * (pingPong)) <= 4096) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 516 of bug id Math81
### Patch Diff Hash-SHA-256:

6d27b80fbf2d49b7e227654876b504691b6e3706fa91420feb684a11337621ee

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (cnst1 < b2) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 517 of bug id Math81
### Patch Diff Hash-SHA-256:

74671fe6dc5ea9f94f360a0067284c22dc40e8dc829b23532c587b832b87d983

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin1) > 0.0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 518 of bug id Math81
### Patch Diff Hash-SHA-256:

9db94292d8429fd5285031fba47b2ac210aeababa2afe96834860a2e91365a48

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((100 * (java.lang.Math.max(b1, g))) < b2) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 519 of bug id Math81
### Patch Diff Hash-SHA-256:

617afe0275f70015ed2b301346cb05bb375cb671e105b9137651757670f9111e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((tType) < (-22)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 520 of bug id Math81
### Patch Diff Hash-SHA-256:

027c30e6a9e73b64620737269c9956b2bcccb030e6bc198f3216cdf30a4894e5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (cnst1 < 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 521 of bug id Math81
### Patch Diff Hash-SHA-256:

38dd883e3b7d4fc0591586d94370e7a1ce7e5c82ab19f30a25135d992cb1eb47

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((java.lang.Math.abs(dN)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (sigma))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 522 of bug id Math81
### Patch Diff Hash-SHA-256:

6d9de70cff2e71a496b24e6c55f05486598de3845144526b690e223269292be9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((tType) == (-6)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 523 of bug id Math81
### Patch Diff Hash-SHA-256:

fd739d6d9c08cb3dcaaceeb18e79d29bf4fcb1048f6d74c95b7c700bf8fc728e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 524 of bug id Math81
### Patch Diff Hash-SHA-256:

954a1cd3fda6b284e027116a8cd0ef63bdeb82d0185e8162d5e1ab9971593b0d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (start != ((pingPong) - 2)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 525 of bug id Math81
### Patch Diff Hash-SHA-256:

eca9f871e431e0713451f040a63e2940dfc3d1fbc48b058a8fe583b9059974f0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (start == (nn - 2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 526 of bug id Math81
### Patch Diff Hash-SHA-256:

9ea86306a3410fdec50f5c09322a1d27ecd223bde087fd9fb2744c60e1bd0d5a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((dMin) < (qMax)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 527 of bug id Math81
### Patch Diff Hash-SHA-256:

006d41c1b527d3e02b2f046417fb3c1038fb7ad186aafb5b9ea518faf1741f6a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (start < end) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 528 of bug id Math81
### Patch Diff Hash-SHA-256:

a92d575552f35fcc4fb12467d6d3ed49fe7256fd1cbc7f7a8e1197342f70fbbe

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((dMin) < (dMin2)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 529 of bug id Math81
### Patch Diff Hash-SHA-256:

b68c24140f2cdcb7492c725adba4bf103d3e74c25f99db1946ac503562f5104c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((realEigenvalues[0]) > 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 530 of bug id Math81
### Patch Diff Hash-SHA-256:

3be58a44e2c3a8d2c471d6d79345fda865e44d55165e5368522cf231bbe30c84

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((tType) <= deflated) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 531 of bug id Math81
### Patch Diff Hash-SHA-256:

24385b6fe5c1fa1ff3b618218ca30b0d6dc6ac5bc60c457576064754ca969b14

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (np != end) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 532 of bug id Math81
### Patch Diff Hash-SHA-256:

14acff2c2a92c4c1df6809f46aad84f62400e33a34e3114c5bc763ce07cf7bd5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (deflated < start) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 533 of bug id Math81
### Patch Diff Hash-SHA-256:

639c571c89b92c30e0241e3fffb734be6f5d84a39cd742599c7f8baa0e04ce44

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((TOLERANCE_2) < (splitTolerance)) || ((TOLERANCE_2) < ((TOLERANCE) * (java.lang.Math.max(java.lang.Math.abs(TOLERANCE_2), java.lang.Math.abs(splitTolerance)))))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 534 of bug id Math81
### Patch Diff Hash-SHA-256:

c695562f8c476a61dadf3d45a067edc59810514805ce0f9d5c9ab672aebfdf61

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 535 of bug id Math81
### Patch Diff Hash-SHA-256:

7d891c9f623e18f099bc52ce4f20e3af005beb596a9fdd0b836ce79c511e9123

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((g) == 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 536 of bug id Math81
### Patch Diff Hash-SHA-256:

ab0ac2d7f954974d8cadc639f81e7aad98db1126d7e4a9c755c8d27868f3a7ac

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (deflated != (tType)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 537 of bug id Math81
### Patch Diff Hash-SHA-256:

3e6f4431c96f60cc9ce862755175d7af93204be494269d6a2325a9bc6c5f8547

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[(end + 2)])) < (work[end])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[end])) < (work[(end + 2)]))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 538 of bug id Math81
### Patch Diff Hash-SHA-256:

c5ac874ba71935a95122b718165fd43f09f3ccdac2e51031f470c4579651a050

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((2 * (work[(nn - 5)])) < (work[(nn - 7)])) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 539 of bug id Math81
### Patch Diff Hash-SHA-256:

d0a1b2a8232d9271410e2a9240e820301413e0bf738870717dd069e961c2dcf9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((pingPong) < (tType)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 540 of bug id Math81
### Patch Diff Hash-SHA-256:

5c5848976a2fff87a26bb7722341c77faad703c6f15111b0b9cc4f8bdfc70883

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin1) > 0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 541 of bug id Math81
### Patch Diff Hash-SHA-256:

6d60ef830f736981885d5cf3b624aa6288d65db7221214140b00bdab10964da8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((minPivot) < (sigma)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 542 of bug id Math81
### Patch Diff Hash-SHA-256:

62fceb99d1cc68dc6ea4e015190c1b0b39ef2dc69d62a433e2c6a3c56968ba77

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (start < (end - 1)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 543 of bug id Math81
### Patch Diff Hash-SHA-256:

e4b0f1d4f267d9014494fed87209d53110dcf437b987172cb01c6f459567aeb8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (start != ((pingPong) - 2)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 544 of bug id Math81
### Patch Diff Hash-SHA-256:

85d22e8ef90c580ca1e4999c60b2baeac5bcca74520a1475f5be18b88170f8c8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (nn >= (((4 * start) + 2) + (pingPong))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 545 of bug id Math81
### Patch Diff Hash-SHA-256:

8f6349fbdad6ae5cb3711eeeb0fcbc36bc5955ee5ab1df9b45610828b4001ec6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 546 of bug id Math81
### Patch Diff Hash-SHA-256:

e9a58c6c2c0d55aa0fbb74414c1fa4421d2d9e3678e5a94c92b3894f97c6c0c9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((deflated * deflated) <= 4096) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 547 of bug id Math81
### Patch Diff Hash-SHA-256:

51f7f5d87d8ee376aed07fabe8d01d1476ea890509213ab2c4388125f01f81c7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -981,7 +981,7 @@
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
 						double b1 = work[(np - 2)];
-						double b2 = work[(np - 6)];
+						double b2 = (org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (dMin);
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
 							return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 548 of bug id Math81
### Patch Diff Hash-SHA-256:

9438848e4940e01925249509bfeb3cc766d1c8f4e246325b320c531310495c4d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = (work[(nn - 5)]) / (((10 * (pingPong)) * (pingPong)) * (org.apache.commons.math.util.MathUtils.EPSILON));
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 549 of bug id Math81
### Patch Diff Hash-SHA-256:

e67d8f6d9a6f30a33e5348610fecce3a33daeff078ace31a261707bcc701b99f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((dMin) > 0.0) && ((dMin) > (dMin))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 550 of bug id Math81
### Patch Diff Hash-SHA-256:

cb1903b28915941d3fcd707291c0cf99f696cb16e53efbc0d50a4dcf397697e9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[pingPong])) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 551 of bug id Math81
### Patch Diff Hash-SHA-256:

33060257bac98b7ba397e8320f7e7e19b05959a341ca04818297b64bf3462bf1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = ((work[nn]) - (b2 * b2)) / (work[(nn - 7)]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 552 of bug id Math81
### Patch Diff Hash-SHA-256:

fa20ce919f0a607b2caa1d369c7967d7cf09b1b2db746650be65565dafbf1b07

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -979,7 +979,7 @@
 					if ((dMin) == (dN2)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
-						final int np = nn - (2 * (pingPong));
+						final int np = nn - (1 - (pingPong));
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 553 of bug id Math81
### Patch Diff Hash-SHA-256:

420e6023a9f910c5038f123eaf57634c4485116bf277178464f9d71e81252fcd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = work[((pingPong) + 2)];
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 554 of bug id Math81
### Patch Diff Hash-SHA-256:

622e2abad51363c3dd96c02701f823d8f6662b3d0753bbb0b27d5f5d29e86ea7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (work[pingPong])) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 555 of bug id Math81
### Patch Diff Hash-SHA-256:

842c445cccc6167cb2af24ddbf3d6f65e57fdc51e0fcb2fc46bc68def264bc62

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -969,7 +969,7 @@
 								break;
 							}
 						}
-						a2 = cnst3 * a2;
+						a2 = (dMin) / (dMin);
 						if (a2 < cnst1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 556 of bug id Math81
### Patch Diff Hash-SHA-256:

eaa507c77d9b00eae963dba88fcb6d10eb75abffc59282d73519d543b87733cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((dMin) < 0.0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 557 of bug id Math81
### Patch Diff Hash-SHA-256:

14e9ef633f42fcedfa8d8c9f1e849ef855ede18b030463df9f57237d4ce33414

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -980,7 +980,7 @@
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
+						double b1 = work[(((pingPong) + (pingPong)) + (pingPong))];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 558 of bug id Math81
### Patch Diff Hash-SHA-256:

e28bcd3caaec8a5bb9740ae775f5bfb4cbf5fda47ca6be06711959ddfd554f17

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -963,7 +963,7 @@
 							if ((work[i4]) > (work[(i4 - 2)])) {
 								return ;
 							}
-							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
+							b2 = (work[pingPong]) + (work[pingPong]);
 							a2 = a2 + b2;
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 559 of bug id Math81
### Patch Diff Hash-SHA-256:

ba1fd71c242e4984209ce627d58226766d85b118426231b44d19022748b787fb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = (work[((4 * (pingPong)) + (pingPong))]) / (work[(nn - 7)]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 560 of bug id Math81
### Patch Diff Hash-SHA-256:

eeddcd191e1f8f691fa60eb0a8e8822e96f421af75e1b09d666fb0dc3ad37a2d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (java.lang.Math.max(java.lang.Math.abs(dMin), java.lang.Math.abs(dMin))) * (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 561 of bug id Math81
### Patch Diff Hash-SHA-256:

9710dac3af2fb48971b5b8de49f3a29fe900f7cf79cf428a112bf633e77dbbce

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = (sigma) + (work[pingPong]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 562 of bug id Math81
### Patch Diff Hash-SHA-256:

ce40b5b00553fcf2554da86487bbe910541696feb20f0759ed55ca67423f3673

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 563 of bug id Math81
### Patch Diff Hash-SHA-256:

6c0fdbf363b139d39e7e9012dda4f19646286763317040203a5697d3dfbaba88

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = 1 - (java.lang.Math.sqrt(dMin));
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 564 of bug id Math81
### Patch Diff Hash-SHA-256:

649c0a5395829e23d48aef7f3274e70487950b0466da918de23bf91c6ad74a47

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = (sigma) + (work[((pingPong) + 2)]);
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 565 of bug id Math81
### Patch Diff Hash-SHA-256:

1d1bba4f83b11b0c8bf3ecfa909632a291b83cb9d0c916643d9e1fe9473d944a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) == 0) && (((pingPong) - (pingPong)) > 3)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 566 of bug id Math81
### Patch Diff Hash-SHA-256:

0f0b7769cdf7862a4dfd8e0d1227959d39f982de0cd1b96898ce3d0fe19281a6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((dMin) + (dMin));
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 567 of bug id Math81
### Patch Diff Hash-SHA-256:

afa107c9714478214924f9f1b7b30d93c8b79ecefe1b9274062996f9e8c42e4d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((dMin) > 0.0) || ((work[(np - 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 568 of bug id Math81
### Patch Diff Hash-SHA-256:

219aed648bded1453d70883a48c63758fef362338348d7906d250d699698df90

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || ((work[((pingPong) + 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 569 of bug id Math81
### Patch Diff Hash-SHA-256:

62e8bdc7fcc333ed673dacd8ba0fa28f9a3554c2cc555c48a250bf6547e61c27

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[pingPong])) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 570 of bug id Math81
### Patch Diff Hash-SHA-256:

106b4457ab0f228378fb3f909efff076d510d3b93e1e017fed071be7e7cfcf78

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((pingPong) * (pingPong)) <= 4096) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 571 of bug id Math81
### Patch Diff Hash-SHA-256:

32b5600ca70494e93f37245e44df47ae615bc86ebad34719eab25fc48c498a4c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (sigma) + (work[pingPong]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 572 of bug id Math81
### Patch Diff Hash-SHA-256:

219d218a06cf1d11950e17286da0ffe9485e5d32fea4a430f5c3db4e0f8f3b9d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = ((work[pingPong]) * (work[pingPong])) / (work[pingPong]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 573 of bug id Math81
### Patch Diff Hash-SHA-256:

cd38fedcaa468c42dec1bde5c84e25dfa6cb12967114983fa1b9a8d43ab2511c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = 0.25 * ((work[0]) + (3 * (work[1])));
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 574 of bug id Math81
### Patch Diff Hash-SHA-256:

f412040d643714bf4f32c5e8d3405072de3464860606ec8559c5ed110f96c8e0

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((dMin) >= 0) && ((dMin) > 0)) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 575 of bug id Math81
### Patch Diff Hash-SHA-256:

585af4927485d37a4615be8d92d4aace686f6434f394a147e2333d7302738047

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((4 * (pingPong)) - (pingPong)) - 1) > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 576 of bug id Math81
### Patch Diff Hash-SHA-256:

b88c85cd7f095d14d04aa27115ec5267089d39bba57a46315da14f53d4212601

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || ((work[((4 * (pingPong)) + (pingPong))]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 577 of bug id Math81
### Patch Diff Hash-SHA-256:

38a0f34ea6cd2f3a6fa72ca5f1f7d76f25171aa2e3dace92e5b477429d171842

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || (((dMin) == (dMin)) && ((dMin) == (dMin)))) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 578 of bug id Math81
### Patch Diff Hash-SHA-256:

dac318bece00b5153e2997a74eae27930ae90ad559fa3ed43bd0806c8c68ab1a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -979,7 +979,7 @@
 					if ((dMin) == (dN2)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
-						final int np = nn - (2 * (pingPong));
+						final int np = nn - ((pingPong) - 7);
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 579 of bug id Math81
### Patch Diff Hash-SHA-256:

99b7a11a6cc01bd4a5e4ec5e7aabed902b979ea15ba5a65f1b23808857693735

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (2.0 * (org.apache.commons.math.util.MathUtils.EPSILON)) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 580 of bug id Math81
### Patch Diff Hash-SHA-256:

303e9f3e44680e9c82edf8eeaf60defec9967c4fd12f4c20a8a300f0210f4ac2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -979,7 +979,7 @@
 					if ((dMin) == (dN2)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
-						final int np = nn - (2 * (pingPong));
+						final int np = nn - ((pingPong) - 1);
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 581 of bug id Math81
### Patch Diff Hash-SHA-256:

d44a0c23e51751bfefab303e5e5bf40c136e96e790576e5102be31146f4d6ea9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -969,7 +969,7 @@
 								break;
 							}
 						}
-						a2 = cnst3 * a2;
+						a2 = (sigma) + (work[(4 * (pingPong))]);
 						if (a2 < cnst1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 582 of bug id Math81
### Patch Diff Hash-SHA-256:

028f77287a3082d2bf11f2aa4e0cad81672b9e56a83fef17d5b8a513c6997b83

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = (3 * (work[0])) + (work[1]);
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 583 of bug id Math81
### Patch Diff Hash-SHA-256:

0b4a48d3c13c4a4610cd05742107ce433c99860acaf0610b11b0f6c12dbcfc76

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if ((((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[pingPong])) && (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[pingPong])) < (work[((pingPong) + 2)]))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 584 of bug id Math81
### Patch Diff Hash-SHA-256:

0ac8997028ea51f9ad76834621f27e2e5557c95b460f5d8b2047f074f85bb589

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -963,7 +963,7 @@
 							if ((work[i4]) > (work[(i4 - 2)])) {
 								return ;
 							}
-							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
+							b2 = (((sigma) * (org.apache.commons.math.util.MathUtils.EPSILON)) * (pingPong)) + (2 * (sigma));
 							a2 = a2 + b2;
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 585 of bug id Math81
### Patch Diff Hash-SHA-256:

73ef7ddffed96db37d2f21e9cdf3c34c24d37f1f8bbdca12af45c73e477e5001

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((dMin) > 0.0) && ((dMin) > (dMin))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 586 of bug id Math81
### Patch Diff Hash-SHA-256:

de24fcebf3084cb5d7c46f44d49a13583a0c419dfce1d0b7013e20b0ca7b03cb

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((dMin) < 0.0) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 587 of bug id Math81
### Patch Diff Hash-SHA-256:

598697777e8686efc8ff67aeebeaafbbb1c632fa54028f36c51d243612a5068e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -980,7 +980,7 @@
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
+						double b1 = work[((pingPong) + 9)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 588 of bug id Math81
### Patch Diff Hash-SHA-256:

03854f258ec2d67465f9b65ee4095cc4a7000edab2f438d532edc69d77e5cbc4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -980,7 +980,7 @@
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
+						double b1 = work[((pingPong) + 1)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 589 of bug id Math81
### Patch Diff Hash-SHA-256:

b708d829219558f748bbe58d5c5e58e69c6a5e8f591d83c56ac9c696ab396cd2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (work[pingPong]) * (sigma);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 590 of bug id Math81
### Patch Diff Hash-SHA-256:

0c6336cee12b5e81fa88b4f95f5ececd0653a0f279a5570a3ce69ac935f7693a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = 0.25 * ((work[0]) + (3 * (work[1])));
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 591 of bug id Math81
### Patch Diff Hash-SHA-256:

0ea6a8f3c9b330aedd4a77cf0558128ed4fcf64882c728838fb6c7abe8e503f7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (work[0]) + (3 * (work[1]));
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 592 of bug id Math81
### Patch Diff Hash-SHA-256:

ec79dc4a81dff7b8957832e2ab610b8720c3bcbfe9c29d6f1d28d9f029686d6c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (gam * (100 * (java.lang.Math.max(dMin, dMin)))) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 593 of bug id Math81
### Patch Diff Hash-SHA-256:

9b64e3ab427c264e4cb61c802c3c98125feb5ac1d517cc5f7cf88ddfd015dba6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || ((work[0]) > 0)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 594 of bug id Math81
### Patch Diff Hash-SHA-256:

182b348ea388a29e17faea46140745b56252989431d2b987643c7eb3e15622e6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (((dMin) * (dMin)) - ((dMin) * (dMin)));
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 595 of bug id Math81
### Patch Diff Hash-SHA-256:

aa0701674edaf3391b45fbad08b7d0858370f2e30863a109cb28ac73bd393d1b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if ((java.lang.Math.abs(dMin)) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * (dMin))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 596 of bug id Math81
### Patch Diff Hash-SHA-256:

7e4e301abd1fc019038e3a3e66eea5e53b486d5138f8df792a7a712b373e4032

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 1)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 597 of bug id Math81
### Patch Diff Hash-SHA-256:

57912e8116d79250803ab9927986a3ed24911ac2fd19be64e90f5595c9aabf03

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (((dMin) * (dMin)) + ((dMin) * (dMin))) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 598 of bug id Math81
### Patch Diff Hash-SHA-256:

21d0620a97da1f8b621b073dd8030cb153183c95e70d4fca376c3d714da3fcda

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((pingPong) - (pingPong)) + 1) > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 599 of bug id Math81
### Patch Diff Hash-SHA-256:

372e5f21fdc3eaf2db03b87272d664c08a2911ead395f72c8a9a2e02157df542

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (work[nn]) - (b2 * b2);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 600 of bug id Math81
### Patch Diff Hash-SHA-256:

8694ee77d5c78f1919bcbd1cf86d5a754d42d4158ddb8a473f7fa718842e6f2a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (work[pingPong]) + (work[pingPong]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 601 of bug id Math81
### Patch Diff Hash-SHA-256:

258e5c53c2ec0cf49ffeb42d13b97c3ed017c36f782ae863622925d71cc6e2ce

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) / 4) > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 602 of bug id Math81
### Patch Diff Hash-SHA-256:

b9414dab5296e0835a863d6f1984e170a0ac9317b14b21f20cde29f0859e3d34

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) - 6) > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 603 of bug id Math81
### Patch Diff Hash-SHA-256:

1426a6b30c4d1cc094915ea9f3d141e58874ff449459bd0c4b96ceddd98e75bc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((work[((pingPong) + 3)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (work[pingPong]))) && ((work[((pingPong) + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma)))) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 604 of bug id Math81
### Patch Diff Hash-SHA-256:

94dda1f9c3abce6727206fae26ec7e5edeb5669222e004d107c4d4e4f082d30f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 605 of bug id Math81
### Patch Diff Hash-SHA-256:

24b3403dd7e748cff65902b7a9601256af306c8369f7a02eaf8509b9415d4af1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = 3 * (work[0]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 606 of bug id Math81
### Patch Diff Hash-SHA-256:

f54365ddb6ae66030ae27de44e9bb29c05c764a0a81632f890799bad294f30e9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -969,7 +969,7 @@
 								break;
 							}
 						}
-						a2 = cnst3 * a2;
+						a2 = 2 * ((((sigma) * (org.apache.commons.math.util.MathUtils.EPSILON)) * (pingPong)) + (2 * (sigma)));
 						if (a2 < cnst1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 607 of bug id Math81
### Patch Diff Hash-SHA-256:

c3c91223ddd1aa68f489a04ec37c0579ca0c00c25448d286958499c7c5e76182

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = ((dMin) * (java.lang.Math.cos(((dMin) / 3)))) - (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 608 of bug id Math81
### Patch Diff Hash-SHA-256:

a94d1bfab5c6ad911110e1dce3d3b25f3150491c686fb3b11a68d4457ea9362c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) - 17) > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 609 of bug id Math81
### Patch Diff Hash-SHA-256:

a03f16a26b66c08421c29866d0f0ea26ae5fa48c28d329611d896aa1d989c825

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = ((dMin) * (dMin)) * (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 610 of bug id Math81
### Patch Diff Hash-SHA-256:

e833a4b9962e5b6375d3f9f8d5bbf853208750e27b73d3bdedc5e67bce828b1d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[((pingPong) + 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 611 of bug id Math81
### Patch Diff Hash-SHA-256:

20e8b7bc583ffef97c0367cd50fa4e8c8d04f290ac2a1b7cbde2712c378d84f7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (dMin) * (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 612 of bug id Math81
### Patch Diff Hash-SHA-256:

a9d596f69fd7648ba10b93b1c47f4bbacfeeadfe28b657adac5c609cc16aaf07

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -981,7 +981,7 @@
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
 						double b1 = work[(np - 2)];
-						double b2 = work[(np - 6)];
+						double b2 = work[(3 + nn)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
 							return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 613 of bug id Math81
### Patch Diff Hash-SHA-256:

152e396019dff26f8efbce1084c85eacd6b94a23cfb71996876bf59aff06b9a6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((work[pingPong]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 614 of bug id Math81
### Patch Diff Hash-SHA-256:

c41f20d23e58e8fb93ea089d1f4d4d6f7b200824be1cb7d7df8fa0e526742fd5

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -954,7 +954,7 @@
 							b2 = (work[(nn - 9)]) / (work[(nn - 11)]);
 							np = nn - 13;
 						}
-						a2 = a2 + b2;
+						a2 = 1 + (dMin);
 						for (int i4 = np; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 							if (b2 == 0.0) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 615 of bug id Math81
### Patch Diff Hash-SHA-256:

c1d6222bb317d877773cfea06308ef7d4d5f1585d6b651b9c391ca460aeecf69

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[pingPong]) == 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 616 of bug id Math81
### Patch Diff Hash-SHA-256:

b3396c4df3becd4365ba981d5e9e7f0186cb1fb5ab3f4dbfaebad255dc26c247

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (b2 * b2) - (work[(nn + 1)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 617 of bug id Math81
### Patch Diff Hash-SHA-256:

bd93bab2b905d3a89280dfdfcd937f12db3ef3372b6cf4004a1e2b981e329845

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = 1.0 / (java.lang.Math.sqrt(dMin));
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 618 of bug id Math81
### Patch Diff Hash-SHA-256:

2e2f8f3b979ae468d958275150dcfc08c290ebc32453a6c946ab457d51db1375

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || ((pingPong) < 4)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 619 of bug id Math81
### Patch Diff Hash-SHA-256:

e8367b494656b56552a463604e67a73b93b7c3bd1f877dc1c7d286baeacb39f2

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((dMin) < 0.0) && ((dMin) > 0.0)) && ((work[(((4 * (pingPong)) - 5) - (pingPong))]) < ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE) * ((dMin) + (dMin))))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 620 of bug id Math81
### Patch Diff Hash-SHA-256:

bc04011abb02d81437875235b1a1168b2223508ea2cb0e4cf8861f9ddf6c263c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -906,7 +906,7 @@
 		int nn = ((4 * end) + (pingPong)) - 1;
 		switch (deflated) {
 			case 0 :
-				if (((dMin) == (dN)) || ((dMin) == (dN1))) {
+				if ((pingPong) != ((pingPong) - 2)) {
 					double b1 = (java.lang.Math.sqrt(work[(nn - 3)])) * (java.lang.Math.sqrt(work[(nn - 5)]));
 					double b2 = (java.lang.Math.sqrt(work[(nn - 7)])) * (java.lang.Math.sqrt(work[(nn - 9)]));
 					double a2 = (work[(nn - 7)]) + (work[(nn - 5)]);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 621 of bug id Math81
### Patch Diff Hash-SHA-256:

17687c66ed8fbbbd092611425164fbb667773b6ef90826715f8aaf2bfe126038

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = (work[((pingPong) + 7)]) / (work[(nn - 7)]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 622 of bug id Math81
### Patch Diff Hash-SHA-256:

fbd46b373f0ab29fb591ed1fa152c4145de89fde96898a30347eafced78b17d9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = (work[(6 * (pingPong))]) + (work[((6 * (pingPong)) + 3)]);
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 623 of bug id Math81
### Patch Diff Hash-SHA-256:

04252bf81b118d3f969a5da594ff8effecbee4a54f91aaa78ba5de4b57b48dee

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = ((sigma) * (org.apache.commons.math.util.MathUtils.EPSILON)) * (pingPong);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 624 of bug id Math81
### Patch Diff Hash-SHA-256:

be84ff590e5e3b9cbae1f139c1f426a725615e323e85f894e0255ee50e8eef7b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (gam * ((dMin) / 3)) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 625 of bug id Math81
### Patch Diff Hash-SHA-256:

4251f920f4f926276a8d748e503b8264698e28eda498a43ca7b965d6c0704490

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if (((dMin) < 0.0) && ((dMin) > 0.0)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 626 of bug id Math81
### Patch Diff Hash-SHA-256:

a34aba763a1abc99113c564214455e1b0adfc28b98720d06440e844278457d3a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (((10 * (pingPong)) * (pingPong)) * (org.apache.commons.math.util.MathUtils.EPSILON)) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 627 of bug id Math81
### Patch Diff Hash-SHA-256:

1929aa40d892c25932e1216d99eb0976483582583188d2aa7c9b5c0b740fa5f8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = 1 - (java.lang.Math.sqrt(dMin));
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 628 of bug id Math81
### Patch Diff Hash-SHA-256:

5906353c693596051cf1958395374c06aa273d682362d2bbe6626781329e6a3c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = ((dMin) / (dMin)) * (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 629 of bug id Math81
### Patch Diff Hash-SHA-256:

9eebf35cd3e75664ef55ae096463c67480d552f230a64249627b45d5d11aa8d9

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = 1.0 - (2.0 * (org.apache.commons.math.util.MathUtils.EPSILON));
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 630 of bug id Math81
### Patch Diff Hash-SHA-256:

584498eb52a560b23e31ff990632011f5cc9b26633e4f3c153d9d46bc064a8c4

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / ((work[(nn - 3)]) * ((work[(nn - 5)]) / b2));
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 631 of bug id Math81
### Patch Diff Hash-SHA-256:

0fd9eefd7f1276decaddf1a1564790462d9eb2bdff47ea32beb6fb424f0436a3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1058,7 +1058,7 @@
 						tType = -8;
 					}
 				}else {
-					tau = 0.25 * (dMin1);
+					tau = (sigma) - (work[(4 * (pingPong))]);
 					if ((dMin1) == (dN1)) {
 						tau = 0.5 * (dMin1);
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 632 of bug id Math81
### Patch Diff Hash-SHA-256:

04a6c6a6b076f94f3956249331bf667e8cb35f3dd2dd3b6cc774849ab09d7124

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((pingPong) != ((pingPong) - 2)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 633 of bug id Math81
### Patch Diff Hash-SHA-256:

121c64e2a8f04d5d35e97745142bc27d5124cf0169ba6eb35581f33b40f60efc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -954,7 +954,7 @@
 							b2 = (work[(nn - 9)]) / (work[(nn - 11)]);
 							np = nn - 13;
 						}
-						a2 = a2 + b2;
+						a2 = (sigma) + (work[(4 * (pingPong))]);
 						for (int i4 = np; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 							if (b2 == 0.0) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 634 of bug id Math81
### Patch Diff Hash-SHA-256:

6274546635a5dbae81489afe2ad5dad735ce0f75955be6195dc476bb003b0403

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -954,7 +954,7 @@
 							b2 = (work[(nn - 9)]) / (work[(nn - 11)]);
 							np = nn - 13;
 						}
-						a2 = a2 + b2;
+						a2 = 0.25 * ((work[0]) + (3 * (work[1])));
 						for (int i4 = np; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 							if (b2 == 0.0) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 635 of bug id Math81
### Patch Diff Hash-SHA-256:

9b23d8f20685e0634900a505ea2b0f8819218a24cd0cd9f0b67e683eb93dcc93

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -981,7 +981,7 @@
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
 						double b1 = work[(np - 2)];
-						double b2 = work[(np - 6)];
+						double b2 = work[((pingPong) + 9)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
 							return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 636 of bug id Math81
### Patch Diff Hash-SHA-256:

1933070e2c3320909c31091641005b6d14951bcae31fd9b9fe8f3b2677102b1b

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -976,7 +976,7 @@
 						tau = s;
 					}
 				}else
-					if ((dMin) == (dN2)) {
+					if (((dMin) < 0.0) && ((dMin) > 0.0)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 637 of bug id Math81
### Patch Diff Hash-SHA-256:

d3c35a2194503722f37d6f95f4504b104494cbc69c2438efec66d56a818429ab

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((work[(np - 8)]) > b2) || ((work[((pingPong) + 10)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 638 of bug id Math81
### Patch Diff Hash-SHA-256:

3f851d8bc724e497ef75eeb5e5b0780a30e276e40c317f71e4a98e657c2cd712

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = (((dMin) * (dMin)) * (dMin)) - (dMin);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 639 of bug id Math81
### Patch Diff Hash-SHA-256:

be344e7d56e2d42965a8c2a262e76912540f08734398ff0d82a886d15d9ce7aa

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -969,7 +969,7 @@
 								break;
 							}
 						}
-						a2 = cnst3 * a2;
+						a2 = 0.25 * ((3 * (work[0])) + (work[1]));
 						if (a2 < cnst1) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 640 of bug id Math81
### Patch Diff Hash-SHA-256:

bb673ef2c568e2ec50e5a2588913e91529aa984b615924211d1e6265750cbbb6

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = ((dMin) - (dMin)) - (((dMin) > 0.0) && ((dMin) > (dMin)) ? ((dMin) / (dMin)) * (dMin) : (dMin) + (dMin));
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 641 of bug id Math81
### Patch Diff Hash-SHA-256:

f5b54d2b4906f0c349465d38ec16fe41221a73cad43077c11df69ade0d7467cc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = ((dMin) * (java.lang.Math.cos((((dMin) + (4 * (dMin))) / 3)))) - (dMin);
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 642 of bug id Math81
### Patch Diff Hash-SHA-256:

829b38fed61a3d726ff2bd27ac2042d198c6fcb924601365f7cdb823130371d7

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((work[(nn - 8)]) > b2) || ((work[(nn - 4)]) > b2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 643 of bug id Math81
### Patch Diff Hash-SHA-256:

f3d73f4ea51725c69d290cce7cce3562ed68f307fbdd379b36cd23fb92e5ce39

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[pingPong])) < (work[((pingPong) + 2)])) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 644 of bug id Math81
### Patch Diff Hash-SHA-256:

abfcb13f4ede1ebdf050d264e165e47f5fe9a50592f91205c67f3f18aa02cea1

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = (work[pingPong]) - (sigma);
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 645 of bug id Math81
### Patch Diff Hash-SHA-256:

6578d4254d620e02195dd996da2fa031d8dc6a318f9da639552ec6aa4daf2063

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if ((dMin) > 0.0) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 646 of bug id Math81
### Patch Diff Hash-SHA-256:

552c0713bf073a6256276c18a07a49ed8ba57d2124ad693f1c1456e070262392

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = ((3 * (work[0])) + (work[1])) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 647 of bug id Math81
### Patch Diff Hash-SHA-256:

bf29875d9b4daa4acfd621a02c1e283d3ec5efc8dea9b67c45df61f34aec6ccc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[pingPong]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (sigma))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 648 of bug id Math81
### Patch Diff Hash-SHA-256:

4823e4de87c84f81031e18c49a0b41109521eb19d1ccce99b5de8a04ff2fb650

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -963,7 +963,7 @@
 							if ((work[i4]) > (work[(i4 - 2)])) {
 								return ;
 							}
-							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
+							b2 = (work[pingPong]) + (sigma);
 							a2 = a2 + b2;
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 649 of bug id Math81
### Patch Diff Hash-SHA-256:

a6e838ba1af0fee0048a82bae60de6dde9564ee54a123fe4c8c270bd74ad326a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -980,7 +980,7 @@
 						tType = -5;
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
-						double b1 = work[(np - 2)];
+						double b1 = work[((pingPong) + (pingPong))];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 650 of bug id Math81
### Patch Diff Hash-SHA-256:

24d7e14cbe516b935571d34219a2b4836ef63af50b031b8e2242dee2f3e73f43

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (0.5 * (dMin)) - (dMin);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 651 of bug id Math81
### Patch Diff Hash-SHA-256:

d33c723634c1cffb2df18e503afe5682aac844f4559d9eb00477e19886ed0941

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 2)])) < (work[pingPong])) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 652 of bug id Math81
### Patch Diff Hash-SHA-256:

77a7a3c492c7d7015fdba495744f75f2d3ad86b2ce1ec5171e7c715d040c36b3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = ((work[pingPong]) * (work[((pingPong) + 9)])) / (work[((pingPong) + 10)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 653 of bug id Math81
### Patch Diff Hash-SHA-256:

69849ba55a8e8819f80281f69e8c522204fd451683205693c278dcd1416ac43c

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -954,7 +954,7 @@
 							b2 = (work[(nn - 9)]) / (work[(nn - 11)]);
 							np = nn - 13;
 						}
-						a2 = a2 + b2;
+						a2 = (((dMin) * (dMin)) * (dMin)) - (dMin);
 						for (int i4 = np; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 							if (b2 == 0.0) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 654 of bug id Math81
### Patch Diff Hash-SHA-256:

61077c9cc4618ddc44fffb13460e39bdb42ed97b2c7d66bcc49329db95379fdf

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b2)) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 655 of bug id Math81
### Patch Diff Hash-SHA-256:

5e23030ad1389c6564cb4dfef2f872c5abaf13b97c30e368429318756a6e7abd

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -979,7 +979,7 @@
 					if ((dMin) == (dN2)) {
 						tType = -5;
 						double s = 0.25 * (dMin);
-						final int np = nn - (2 * (pingPong));
+						final int np = nn - (((4 * (pingPong)) - 3) - (pingPong));
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 656 of bug id Math81
### Patch Diff Hash-SHA-256:

af69e20c80f9ec68ff58dbda03ce183fff307682513ae4ca468244797c658865

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -938,7 +938,7 @@
 							if ((work[(nn - 5)]) > (work[(nn - 7)])) {
 								return ;
 							}
-							b2 = (work[(nn - 5)]) / (work[(nn - 7)]);
+							b2 = (work[(1 - (pingPong))]) / (work[(nn - 7)]);
 							np = nn - 9;
 						}else {
 							np = nn - (2 * (pingPong));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 657 of bug id Math81
### Patch Diff Hash-SHA-256:

76815bd9571f6ee5b1822dd0e0abcaff0eeb43128160ac0fe3df513f367cb83a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((((4 * (pingPong)) - 5) - (pingPong)) > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 658 of bug id Math81
### Patch Diff Hash-SHA-256:

4ced557c377fd88426955fcae73f81849c8291c82467f7eeba803e2ee2672f54

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((pingPong) * (pingPong)) > 2) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 659 of bug id Math81
### Patch Diff Hash-SHA-256:

336bde537dee2dbd6e1568d186fa5d2e2ba244038c3efdc54337af731644e9de

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((transformer) instanceof org.apache.commons.math.linear.RealMatrix) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 660 of bug id Math81
### Patch Diff Hash-SHA-256:

29d7482d0d4aaab837b233746827a1d152ebf4203eea9beadb61e72e7d8f4f8a

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -778,7 +778,7 @@
 				work[(j4 - 3)] = d + (work[j4]);
 				final double tmp = (work[(j4 + 2)]) / (work[(j4 - 3)]);
 				d = (d * tmp) - (tau);
-				dMin = java.lang.Math.min(dMin, d);
+				dMin = java.lang.Math.max(d, (0.333 * d));
 				work[(j4 - 1)] = (work[j4]) * tmp;
 				eMin = java.lang.Math.min(work[(j4 - 1)], eMin);
 			}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 661 of bug id Math81
### Patch Diff Hash-SHA-256:

acbb7820710c0af68e691b70d64cf0a0259a96d1a5eb6480e25b3ec6da8b4ea8

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -1027,7 +1027,7 @@
 				
 				break;
 			case 1 :
-				if (((dMin1) == (dN1)) && ((dMin2) == (dN2))) {
+				if (((dMin) == (dMin)) && ((dMin) == (dMin))) {
 					tType = -7;
 					double s = 0.333 * (dMin1);
 					if ((work[(nn - 5)]) > (work[(nn - 7)])) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 662 of bug id Math81
### Patch Diff Hash-SHA-256:

161e781f9d4204273aa6dd8846db40afa10428f486ffecac279ff18dd6c0f064

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = ((((9 * (dMin)) - (2 * (dMin))) * (dMin)) - (27 * (dMin))) / 54;
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 663 of bug id Math81
### Patch Diff Hash-SHA-256:

a8d65ca0bb3a76dca499a82a71f1c5dc56bab4a3093e698fbe5168ccab0277ca

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((pingPong) > (pingPong)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 664 of bug id Math81
### Patch Diff Hash-SHA-256:

7b30064dcfb6645dbdd04ba74bd27cf8803b651f0775a699077f943bea91307d

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = 1.5 * (work[pingPong]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 665 of bug id Math81
### Patch Diff Hash-SHA-256:

418501df5af2153f77fcab023a28513ead39d2ffedcafdf34648319bdb6b59ba

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -964,7 +964,7 @@
 								return ;
 							}
 							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
-							a2 = a2 + b2;
+							a2 = (work[pingPong]) + (sigma);
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
 							}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 666 of bug id Math81
### Patch Diff Hash-SHA-256:

a576d1f09161f85bd002f02f4d109dcd9f484794139e61a23a0a8001405a3554

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = (dMin) + (java.lang.Math.sqrt(((dMin) * ((dMin) + (dMin)))));
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 667 of bug id Math81
### Patch Diff Hash-SHA-256:

8feb21c2490f75921783f4fd573781f2e5f869a3b30150d69acd48726325f596

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if (((((pingPong) == 0) && (((pingPong) - (pingPong)) > 3)) && ((work[((4 * (pingPong)) - 1)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (dMin)))) && ((work[((4 * (pingPong)) - 2)]) <= ((org.apache.commons.math.linear.EigenDecompositionImpl.TOLERANCE_2) * (dMin)))) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 668 of bug id Math81
### Patch Diff Hash-SHA-256:

cb64054d6dee3206d8dbedd68434da9cc81354230896b742c145b176f16f907f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((pingPong) == ((pingPong) - 2)) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 669 of bug id Math81
### Patch Diff Hash-SHA-256:

d61d44d35c7ef2c93c013f5628fdb804ec5b7e50bfd2cc41e7d5e748cae80d3f

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -971,7 +971,7 @@
 						}
 						a2 = cnst3 * a2;
 						if (a2 < cnst1) {
-							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
+							s = (gam * ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[pingPong]))) / (1 + a2);
 						}
 						tau = s;
 					}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 670 of bug id Math81
### Patch Diff Hash-SHA-256:

fc3e31b9b8c2924b315cdf6bcd474730aa0d21e4071d27036ffa5eaad6633922

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -983,7 +983,7 @@
 						double b1 = work[(np - 2)];
 						double b2 = work[(np - 6)];
 						final double gam = dN2;
-						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
+						if (((27 * (dMin)) > b2) || ((work[(np - 4)]) > b1)) {
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 671 of bug id Math81
### Patch Diff Hash-SHA-256:

2ee65b77de5ee5310d794c1b5e81e4111f90eaf6c532ffd608ec87690920cd5e

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -963,7 +963,7 @@
 							if ((work[i4]) > (work[(i4 - 2)])) {
 								return ;
 							}
-							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
+							b2 = b2 * ((work[i4]) / ((org.apache.commons.math.util.MathUtils.SAFE_MIN) * (work[((pingPong) + 1)])));
 							a2 = a2 + b2;
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 672 of bug id Math81
### Patch Diff Hash-SHA-256:

5014732c53f951c7120d72d731637998884baaa8658e8636f01954b484bcd0a3

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -988,7 +988,7 @@
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
 						if ((end - start) > 2) {
-							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
+							b2 = java.lang.Math.sqrt(org.apache.commons.math.util.MathUtils.EPSILON);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
 								if (b2 == 0.0) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 673 of bug id Math81
### Patch Diff Hash-SHA-256:

cbbbdb1968cbb0d31f0e15ce98f0bf5fc98e391f15acb9f7f3c20262ecabb589

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -987,7 +987,7 @@
 							return ;
 						}
 						double a2 = ((work[(np - 8)]) / b2) * (1 + ((work[(np - 4)]) / b1));
-						if ((end - start) > 2) {
+						if ((work[((pingPong) + 2)]) <= 0) {
 							b2 = (work[(nn - 13)]) / (work[(nn - 15)]);
 							a2 = a2 + b2;
 							for (int i4 = nn - 17; i4 >= (((4 * start) + 2) + (pingPong)); i4 -= 4) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 674 of bug id Math81
### Patch Diff Hash-SHA-256:

db4a70553ec1c9cfe3e71328f77db0c19199cfa372c26e34317b0afa6bb518cc

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -963,7 +963,7 @@
 							if ((work[i4]) > (work[(i4 - 2)])) {
 								return ;
 							}
-							b2 = b2 * ((work[i4]) / (work[(i4 - 2)]));
+							b2 = (((dMin) * (dMin)) * (dMin)) - (dMin);
 							a2 = a2 + b2;
 							if (((100 * (java.lang.Math.max(b2, b1))) < a2) || (cnst1 < a2)) {
 								break;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 675 of bug id Math81
### Patch Diff Hash-SHA-256:

4fea23aa4a5c454e247f128bbe8996503770c730557004beed14cd9fe67dd387

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -981,7 +981,7 @@
 						double s = 0.25 * (dMin);
 						final int np = nn - (2 * (pingPong));
 						double b1 = work[(np - 2)];
-						double b2 = work[(np - 6)];
+						double b2 = (dMin) * (1 - ((dMin) * (dMin)));
 						final double gam = dN2;
 						if (((work[(np - 8)]) > b2) || ((work[(np - 4)]) > b1)) {
 							return ;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 676 of bug id Math81
### Patch Diff Hash-SHA-256:

90aa0fbca6acc8f7382e87c4fb9a559c59fbe51a8c79a840bc07b94a35d333ed

### Patch Diff:
```
--- /original/org/apache/commons/math/linear/EigenDecompositionImpl.java	
+++ /fixed/org/apache/commons/math/linear/EigenDecompositionImpl.java	
@@ -970,7 +970,7 @@
 							}
 						}
 						a2 = cnst3 * a2;
-						if (a2 < cnst1) {
+						if ((dMin) > ((dMin) + (dMin))) {
 							s = (gam * (1 - (java.lang.Math.sqrt(a2)))) / (1 + a2);
 						}
 						tau = s;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---