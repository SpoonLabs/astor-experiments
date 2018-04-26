
# Patches of Math84 from Defects4J 
Total patches 149
## Patch 1 of bug id Math84
### Patch Diff Hash-SHA-256:

ebfdeef8416277d78d5ffc3fb1e5fd2154822031fb4dd215336970fe84fa0d64

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) > (gamma)) && (((khi) - (gamma)) > (0.95 * ((khi) - (khi))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math84
### Patch Diff Hash-SHA-256:

c8f56b8875c4d8ec870ab7321e10b4b041c8eb92dfbce3f12b649a2b64725349

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (contracted != null) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math84
### Patch Diff Hash-SHA-256:

d84b9ebd307c65e2f01fd115ca90df1931af0b750c0c1148377e6093d181d507

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) - (gamma)) < (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math84
### Patch Diff Hash-SHA-256:

7b57180e5f56b70c8079190d22b458f9b83e9b7d463b3a3c0b87b72e914574a6

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math84
### Patch Diff Hash-SHA-256:

a2dd6c257a6c8e4d6c3753ef79e5434935a17e882b7da8667fdf877059909300

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((reflected instanceof org.apache.commons.math.linear.RealMatrix) == false) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math84
### Patch Diff Hash-SHA-256:

4d4096bd1672ea368c380de45e8e6772e72704f7e1ec21fb39ed5eaf65b1ee12

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((java.lang.Math.floor(khi)) / 2.0) == (java.lang.Math.floor(((java.lang.Math.floor(khi)) / 2.0)))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math84
### Patch Diff Hash-SHA-256:

8e06c2d00787f1a5eb8e9aabe42840b5a3679974c313d3b7517c2185cd572e6a

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > 0.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math84
### Patch Diff Hash-SHA-256:

3f5ce887a4fb81babaec967a2b3ff6fe470365ba88c94bdd1a48963b635541a7

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) - 1) != 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math84
### Patch Diff Hash-SHA-256:

2547624e6ef641305777cecae81d84ec47f52805bf68b4046edfa6f1c28cab47

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((((khi) < (khi)) && (((khi) - (khi)) > (0.95 * ((khi) - (khi))))) || (((khi) > (khi)) && (((khi) - (khi)) > (0.95 * ((khi) - (khi)))))) || ((khi) == (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math84
### Patch Diff Hash-SHA-256:

4f6067360554e6f16b3eacd90e1f6d5aa3e9f4778f2a48c09ecffb9a187d15bb

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((org.apache.commons.math.util.MathUtils.equals(khi, khi)) || ((java.lang.Math.abs(((khi) - (khi)))) <= (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math84
### Patch Diff Hash-SHA-256:

4006c5313cf98d3bc849c90c790a0ad52c0d1129082f7ea5fcd115a35a8a7f6c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (true) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math84
### Patch Diff Hash-SHA-256:

33793f1d2fc71c13f297b0bfea24b90ebc62e93409f96290a05c26cfb902609f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((org.apache.commons.math.util.MathUtils.equals(khi, khi)) || ((java.lang.Math.abs(((khi) - (khi)))) <= (gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math84
### Patch Diff Hash-SHA-256:

872d3fd620e5b36b16a064dae4d21e48377dfc6d152cc94c340c5b745e6c5933

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator instanceof org.apache.commons.math.stat.descriptive.MultivariateSummaryStatistics) == false) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math84
### Patch Diff Hash-SHA-256:

0ac80a5f2faefdb96ea6d7f93789fabb44d2b8d8fd9d77ecd51521139867f7bf

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math84
### Patch Diff Hash-SHA-256:

d408ceea536579b96aa6c236acf9494024335215d986912ffe9d965658578dee

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (!(comparator instanceof org.apache.commons.math.linear.OpenMapRealVector)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math84
### Patch Diff Hash-SHA-256:

2edf5ec54bdc2063e88ef9026b572a6c9f4a378a028bcebfa856bc8540bb55d7

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > 1) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math84
### Patch Diff Hash-SHA-256:

e6584b3b8781512f7a1447615d003b0c50567c019ab4994e380fc1083ae1f5f1

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) <= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math84
### Patch Diff Hash-SHA-256:

bea901289298777225deb1eada6e931b71d3e3727a423b0353b83ee9fc447e4e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) > (gamma)) && (((khi) - (gamma)) > (0.95 * ((khi) - (gamma))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math84
### Patch Diff Hash-SHA-256:

3ed39de475aff8df9ec0989ff528a081cf37f79c6da5b3cc17c3cd95c1223083

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (best != null) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math84
### Patch Diff Hash-SHA-256:

04c0d89b5860bd478be1d9d20a963f98a0a01d96893bc89174c55eab48a55b31

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) < 1.0E-4) || ((khi) > 0.9999)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math84
### Patch Diff Hash-SHA-256:

c81224fbe66f76c8ef2f892895764b6309c565a85302945be4b30e3c945cfa71

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) > 0) == ((gamma) > 0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math84
### Patch Diff Hash-SHA-256:

17729f51dfa6f018a5f2b9b68f552558920d213c8df2d5ad1a1546ad52076d21

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) < (gamma)) || ((gamma) < 1.0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math84
### Patch Diff Hash-SHA-256:

dc5a8c156c5cfc10480323882ebec53b4451bd82bcfacfac974051900cbea48b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math84
### Patch Diff Hash-SHA-256:

7ccf6b7373430fc759555c34b8c151c6a9fb08cdfaca16ca788054be326afbbc

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) > 0) == ((khi) > 0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math84
### Patch Diff Hash-SHA-256:

9463c137431d01682825d48dc27476b3071e7f11a61c81af9d7f0562cbb3644e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((100 * (java.lang.Math.max(gamma, gamma))) < (khi)) || ((gamma) < (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math84
### Patch Diff Hash-SHA-256:

220ecdc430e7a94e314cf95b85228fced9625660c7317b4780709abfa09c3f2c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) * (gamma)) >= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math84
### Patch Diff Hash-SHA-256:

2339802fe75184b1bc3fd444b9f81f1d220f46028d2ad47f0de2341804cb79c4

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((((((java.lang.Double.isNaN(khi)) || (java.lang.Double.isNaN(khi))) || (java.lang.Double.isNaN(khi))) || ((khi) < 0)) || ((khi) > 1)) || ((khi) <= 0.0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math84
### Patch Diff Hash-SHA-256:

830b5e9e4aed60a88095d451acbc6c3c0e3bb572ae15e26a84ba2fcab8804b6e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(reflected, reflected)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math84
### Patch Diff Hash-SHA-256:

e284832a63252fe324af77f4864a4a7002ae955409b138ccf747eabd5fdfc124

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) >= 0.5) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math84
### Patch Diff Hash-SHA-256:

7147820317b56406c3094c00faae32bfab47cba6478b8ae4192e8c77976e3d88

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) >= (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math84
### Patch Diff Hash-SHA-256:

2df5a1f99a73756d0dd2286bc9abf7a83807fff2edb65e27386bad734381fc3a

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) != 0.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math84
### Patch Diff Hash-SHA-256:

89a7ff00bd400810ad0ffc12ee845ef50da95a417239f83543b7bed9a14d5597

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) < (khi)) || ((gamma) < ((khi) * (java.lang.Math.max(java.lang.Math.abs(khi), java.lang.Math.abs(khi)))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math84
### Patch Diff Hash-SHA-256:

61da3812ff648b17fd85073d9f5a2b5816b978a0606f1acd955c6d349c0fa0ae

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) == (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math84
### Patch Diff Hash-SHA-256:

a6205819023be25281cad6f5dd1f41aa94576b897cae0b03d20dd9d5e5d1b732

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) <= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math84
### Patch Diff Hash-SHA-256:

535433e7e4d96fac3207f34a95f5313a67be54acd709074434a273e27650e8cd

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((khi) - (khi)))) <= (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math84
### Patch Diff Hash-SHA-256:

4501f9e8e9ea49e8a83a833f61551ad25c30ff79df808e2fa2ed67f573c03dc3

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) <= (khi)) || ((gamma) == (gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math84
### Patch Diff Hash-SHA-256:

cf5f878a8b2c4698dfc6b83d180f17be4f211a6e758f9acd6fdefafc17970623

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math84
### Patch Diff Hash-SHA-256:

cf7a95844859c6a676e58bea94966f015e27aa4e774a5e6201bbd3084cac5459

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= 0.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math84
### Patch Diff Hash-SHA-256:

abd3d922f6000fa376ce0aa9a38365ad581b53d580732888f31457f1d4ca100c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(gamma)) <= (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math84
### Patch Diff Hash-SHA-256:

7a5effc074f89d308f0cf6677e572df53c20622948e073d35eb149f0ef1d0ee0

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) < 1.0001) || ((gamma) > 999.9)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math84
### Patch Diff Hash-SHA-256:

926021acde8ab83f91df19d7c3b7075e7c230bd32f36a900a4905235d50f1971

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) <= 2.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math84
### Patch Diff Hash-SHA-256:

b5f0e0eb88a439fcb0da71cf19b5ce23c682728c53f5c44d1d618facb91b0e7c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) > 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math84
### Patch Diff Hash-SHA-256:

7c921d1415b7e32923c48968710eb96f356dbd16a7add993443f763c9f069cc5

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= 0.5) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math84
### Patch Diff Hash-SHA-256:

e8d56df57b3949044bed48d4333b7b4efcbb00f5fa58d7d39c793ec90f873846

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) == (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math84
### Patch Diff Hash-SHA-256:

2f57385192d12737848df2f2b8d4ac4cb4db0ddeb592f75f8eb73789e4ffdab4

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) < (khi)) && ((khi) <= (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math84
### Patch Diff Hash-SHA-256:

6ee65924c8b2d7c21fb2abfe4d1a15cd68c247d4bb6188961e4a1d145ab3b5e0

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((contracted instanceof org.apache.commons.math.linear.RealMatrix) == false) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math84
### Patch Diff Hash-SHA-256:

2c71822ea5699a670a3860e7bd84a1b547d67ace5f7ad274a27e0cbc3d636d6e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) < 0) || ((khi) > 1)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math84
### Patch Diff Hash-SHA-256:

16d32ee5996dba0f826e3b2a008646b99f5337baeaec9385087d954bfd98386a

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) * (gamma)) > 0.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math84
### Patch Diff Hash-SHA-256:

664a3d8c139ab5b95b0d0946c1f9f46e136b0bf7a5d24cf66c5ad435bd2c94ed

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) >= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math84
### Patch Diff Hash-SHA-256:

9ccce79751c2636be4b0de75e8acd39a5fb03e4ff9adad890d6c98addc0ba3e3

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math84
### Patch Diff Hash-SHA-256:

b1113d45e2ab7a65dc0db9fb7c426d8cb88c36ecb45f3fa8516eee178ceadbdf

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) - (gamma)) > (0.95 * ((khi) - (khi)))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math84
### Patch Diff Hash-SHA-256:

914912de7017b8886627bc9f38631fb55f942c576ccb8a32ab5ae8de3e98fcbc

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= 0.75) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math84
### Patch Diff Hash-SHA-256:

0c7a4d44a0af37903e12f83be77f78895d162135554e44a1b0e8070e2ef2b655

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (!(comparator instanceof org.apache.commons.math.stat.clustering.EuclideanIntegerPoint)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math84
### Patch Diff Hash-SHA-256:

e5e63ad68a9275016eacecd8f3aca1d234848b4efaca6f1611d98de5376cb668

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((java.lang.Math.abs(((khi) - (gamma)))) < 1.0E-6) || ((java.lang.Math.abs(((khi) - (khi)))) < 1.0E-6)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math84
### Patch Diff Hash-SHA-256:

373ea19eafdbd5a0ecfd722496f82482ac6fd2345810839b8304e9e45715085c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) < 1.0001) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math84
### Patch Diff Hash-SHA-256:

205dae5ce23611046eb7cce3084c1cb9d8f2d9f8cb40ca247b3aeaad3a575ce7

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= 1) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math84
### Patch Diff Hash-SHA-256:

e302bd1d8927eec53f15cbccbf6515aef7e44eddaaaf8b97329af7a1e4653075

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) != 0.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math84
### Patch Diff Hash-SHA-256:

8b04373135a17f000ed270b48930809b8b9a93776148d6891d5f8b2f1f2fab9d

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) <= (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math84
### Patch Diff Hash-SHA-256:

422848774dac7d35b9960a3781364687e41def4d7d99d8b964b1acb5041fe08f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator instanceof org.apache.commons.math.linear.BigMatrixImpl) == false) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math84
### Patch Diff Hash-SHA-256:

d16b92cd06c8f03cea290b0b61bb83b56ca30185e618c8eb894889ed6c693ca5

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((((((java.lang.Double.isNaN(khi)) || (java.lang.Double.isNaN(khi))) || (java.lang.Double.isNaN(gamma))) || ((khi) < 0)) || ((khi) > 1)) || ((khi) <= 0.0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math84
### Patch Diff Hash-SHA-256:

42e4617d769a44f53afeb99c724959a43ff09a5447bc10cf666d1765872b8ee5

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) - (khi)) < (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math84
### Patch Diff Hash-SHA-256:

4458d76b30027b744ed23dcc939fe1c380ea468cff967bc12d7b25608e731a75

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((((gamma) <= (gamma)) || ((khi) == (khi))) || ((khi) == (gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math84
### Patch Diff Hash-SHA-256:

c3e5927e20a57f9e23335a86b80a8727472e9e183c676c637cb4736afe581bb6

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((2.0 * (gamma)) >= (((1.5 * (khi)) * (gamma)) - (java.lang.Math.abs(((gamma) * (gamma)))))) || ((gamma) >= (java.lang.Math.abs(((0.5 * (gamma)) * (gamma)))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math84
### Patch Diff Hash-SHA-256:

dee9b2e309f7a299c28a0d6a642511e7b2f09d2ee7cbcdcd01226a3b4aa83713

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) <= 2.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math84
### Patch Diff Hash-SHA-256:

b6938a84f376c1c066b2c285c68f7746ab5cd80df64f46e6871253b17e38b8de

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) * (khi)) >= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math84
### Patch Diff Hash-SHA-256:

2616e62f465aa7489f12cdadd597346fa800fa099f85fac99be828829961de21

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) != 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math84
### Patch Diff Hash-SHA-256:

652adc4fd4cbc4c078a412af961706d2ffc22cc5e66be4e6bdd2715bf759ed95

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((((java.lang.Double.isNaN(khi)) || (java.lang.Double.isNaN(khi))) || (java.lang.Double.isNaN(gamma))) || ((khi) < 0)) || ((khi) > 1)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math84
### Patch Diff Hash-SHA-256:

4d097db6ef2c2ca9ebf18bcfc1aa1f81592f747cb60dfeb739465491af7ca87c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) < (khi)) || ((khi) < 1.0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math84
### Patch Diff Hash-SHA-256:

245c6f84ca6259a14c4714ffa94e3ee8ab3d0bf5ce82d06a81c313e37ae9d55d

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (org.apache.commons.math.util.MathUtils.equals(gamma, khi, khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math84
### Patch Diff Hash-SHA-256:

3428b0ac317ae24b971160fb4071f8d42191f2212459e6e80cb078ecf24b9e30

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) - (gamma)) > (0.95 * ((khi) - (gamma)))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math84
### Patch Diff Hash-SHA-256:

21d7d2766ebebebe4bb1cd8d330e813637a5a6f27282c2fc1b59464dc2337820

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) != (java.lang.Math.floor(gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math84
### Patch Diff Hash-SHA-256:

aa587ca6b1ddc77d51411ee9719a6299ae58595b84eab676f0a8c099ce622615

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) < 0.0) || ((khi) > 1.0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math84
### Patch Diff Hash-SHA-256:

d484a64cbbb97634ce54a29e0a8f1376c79a1ed002d3ff6d78c9f78e34d09d54

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (!(comparator instanceof org.apache.commons.math.stat.Frequency)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math84
### Patch Diff Hash-SHA-256:

13af8ecb245652e8cde0c4ed118c9a227a1a27e6dd13473986216c03ce1a4ec9

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > 1.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math84
### Patch Diff Hash-SHA-256:

fcb15f43f47f6e40238944788a25a37175cba2e22476b69e085dd36668fb626f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= 1.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math84
### Patch Diff Hash-SHA-256:

e9678c3f93b6913e26be16767e93292755e4a826e16f915004501fcffa0c1242

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= (java.lang.Math.abs(((0.5 * (gamma)) * (gamma))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math84
### Patch Diff Hash-SHA-256:

ae8282cff896976160e912f1a490b7f73a9bf02700597245fdeef180092006ab

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > ((gamma) * (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math84
### Patch Diff Hash-SHA-256:

64b58360d1111505a13a94fc9ed0555d8f4ad76e2c35e8660b9f0e1e6cc20c9c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) < 1.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math84
### Patch Diff Hash-SHA-256:

2c1b03ea44269ae63ddafd1dc38d95da39171ac11726098dd72499e84fdded99

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) <= 0) || ((khi) > 0.5)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math84
### Patch Diff Hash-SHA-256:

f38fabd7815641d9f93ab1cc4382a4b6e0e9e2787cca57876eb75b5d00eb6502

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (org.apache.commons.math.util.MathUtils.equals(khi, khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math84
### Patch Diff Hash-SHA-256:

4bf3dc787596574d86e4f4851583926d4333f6043c65b131b67026dc4cb1f52e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((khi) - (gamma)))) > (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math84
### Patch Diff Hash-SHA-256:

58655729ec930aac5ac9b2a426c83e861a65a8a112f0ac4a78db49310c885bf1

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) < (gamma)) || ((khi) > (gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math84
### Patch Diff Hash-SHA-256:

b4faf4f82ab41226d058afecfdd88a5ef81893cc02ab23423acd60d61263d59d

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) != 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math84
### Patch Diff Hash-SHA-256:

b9aa86d73cca9614882f6296b89d19a001c6727b4bacdc49ac77d507b05746a3

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > ((gamma) * (gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math84
### Patch Diff Hash-SHA-256:

2c2931d2d81866d958b2e380c30eba8ecfe57466e772eb3a56dec67dc46a9576

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) <= (khi)) || ((gamma) == (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math84
### Patch Diff Hash-SHA-256:

1c5ad03eb13b757a251c4e0ff5e1ac2d2f44d07e25201f4b32ea9a81fb2b8e6b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) < (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math84
### Patch Diff Hash-SHA-256:

f237e10c023276c0ef62b6370ddfe67bb71b80f65c9353f488aa4f2eda8713d1

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) > 0.0) || (java.lang.Double.isNaN(gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math84
### Patch Diff Hash-SHA-256:

1b84bdf223e616ccfd51a1e3214ef30e0c5c245849eaa645d3cae56a760dc26b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((khi) - (khi)))) <= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math84
### Patch Diff Hash-SHA-256:

4c5f79d0a3142c8dc5425dd41bb10d62145c78a2b50bf1ea4b00c98f08b61c2e

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (reflected != null) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math84
### Patch Diff Hash-SHA-256:

87127c0ce6a6cd837f466b75020e604ca900997475c4523d85f177050d0eec49

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(gamma)) <= (java.lang.Math.abs(gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math84
### Patch Diff Hash-SHA-256:

154e6b8a08d1052592b6dba2bcad25dc917b3035e6a0a631ea5abba420f6a9c4

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((((java.lang.Double.isNaN(khi)) || (java.lang.Double.isNaN(khi))) || (java.lang.Double.isNaN(khi))) || ((khi) < 0)) || ((khi) > 1)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math84
### Patch Diff Hash-SHA-256:

b6521084fa43a4f694fb6899a8c6b5107606f7ddf23993ec9385e91d6c5a0451

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(gamma)) > (0.001 * (java.lang.Math.abs(khi)))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math84
### Patch Diff Hash-SHA-256:

ab3d6590ce91fbc386a3eb303c56aa7f9c4aacbc559b073200c73f56e545906b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((gamma) - (gamma)))) <= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math84
### Patch Diff Hash-SHA-256:

7f1ae4d48791c394c0b2e924ace5012ad625ae498061aa3bbe4322d01584ec62

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(khi)) > (java.lang.Math.abs(gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math84
### Patch Diff Hash-SHA-256:

130d0268230792a9105142fb915c4a40375d8e9ddad92758f23f3de9160afb50

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) * ((gamma) - (gamma))) >= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math84
### Patch Diff Hash-SHA-256:

d6f890aea9c9995ef457d55b22e13e449db0082f949cd0ab21919aaafff01146

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((gamma) - (gamma)))) < 1.0E-6) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math84
### Patch Diff Hash-SHA-256:

9b83c09e77ba98afd513744b6f728ee8754502b8a833551a20dee2e37d8fcdfd

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) == (gamma)) || ((gamma) == (gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math84
### Patch Diff Hash-SHA-256:

401e01edd211ff5709c2482b2c4f30c4d019abf5cc20f912d6cc29f3f5a716ed

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > 0.5) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math84
### Patch Diff Hash-SHA-256:

fdd4208bb057e2dbcae727b6d75d4eb30f09cc907ba4bdfbd81e119fb4d4bc12

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(khi)) > (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math84
### Patch Diff Hash-SHA-256:

7af57c3eedb80aea07acb33789a6d310f1ea3969e48e3127bd60a3601a2e7ae1

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > (((gamma) + 1.0) / (((gamma) + (gamma)) + 2.0))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math84
### Patch Diff Hash-SHA-256:

1770c23eb7e9514dd74fa4f302acbd813f1fda81ded0b1a7e36bf9ee6fd3f2bb

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) < (-(gamma))) || ((khi) > (gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math84
### Patch Diff Hash-SHA-256:

004eaf38e5b9adeed1eec46f0992392cad6c89388e2654c266ce3dc775f6714b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) < 1) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math84
### Patch Diff Hash-SHA-256:

929b87e6d64548a52b7e42fa976e66b0f6f3d503b7b6d1140eefd232ae8ec49f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((gamma) - (khi)))) <= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math84
### Patch Diff Hash-SHA-256:

1f611e0030b489df02b81a366716e468248a8d86b6d8c7d2e1f21695b017e2c6

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator instanceof org.apache.commons.math.stat.descriptive.StatisticalSummaryValues) == false) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math84
### Patch Diff Hash-SHA-256:

18ff0572b535133d7830dfc42eecc87f57db6c315851a50e2762a3669af790fd

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((gamma) - (gamma)))) <= (gamma)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math84
### Patch Diff Hash-SHA-256:

7b6e5bd63f84d0e079a57d4ef625ba2f6e747f5a6092c3ff02ff7137912825da

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((java.lang.Math.abs(gamma)) < (gamma)) || ((java.lang.Math.abs(gamma)) <= (java.lang.Math.abs(gamma)))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math84
### Patch Diff Hash-SHA-256:

7b82465173893aeacaaf610503d78515443f4e643c4923a64501ea3eae4975e7

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((java.lang.Math.abs(((khi) - (khi)))) < 1.0E-6) || ((java.lang.Math.abs(((gamma) - (khi)))) < 1.0E-6)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math84
### Patch Diff Hash-SHA-256:

6606152e450cff0453a4862a983ac7eb0c5575dab2d806fa2026c310dac760a2

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) < ((khi) * ((khi) - (gamma)))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math84
### Patch Diff Hash-SHA-256:

18b3adfabc357c08fe5e26b738f314f999e7c3a88a5611a289e26affe6f5a9d6

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) >= 1) || ((khi) <= 0)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 110 of bug id Math84
### Patch Diff Hash-SHA-256:

79d22aea22cfd4e8c4fa06fce602282111ceac185279fa6d72897da9331cdd32

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((((khi) <= (gamma)) || ((khi) == (khi))) || ((khi) == (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 111 of bug id Math84
### Patch Diff Hash-SHA-256:

7f6838cfcb393dbe0da0aa16ecc84bbe350c4bf2298ed8e4da407aa607f27016

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) >= (java.lang.Math.abs(((0.5 * (gamma)) * (gamma))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 112 of bug id Math84
### Patch Diff Hash-SHA-256:

692e30a2e7a99be512c778defb6ea4c6cfc9b4bbfc2377ecd9f7c589e8bab057

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) / (gamma)) > 1) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 113 of bug id Math84
### Patch Diff Hash-SHA-256:

0b1a8633163e2f731640875d4dca4a6810c6ea1f6813b8fed3aeaeefa6005562

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((2.0 * (gamma)) >= (((1.5 * (gamma)) * (gamma)) - (java.lang.Math.abs(((khi) * (gamma)))))) || ((gamma) >= (java.lang.Math.abs(((0.5 * (khi)) * (gamma)))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 114 of bug id Math84
### Patch Diff Hash-SHA-256:

836393c2e613b0e46be90776e06f3cdfce91a7cf169bd2aabe2f55c8aab37eea

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((gamma) < (khi)) || ((gamma) < ((khi) * (java.lang.Math.max(java.lang.Math.abs(gamma), java.lang.Math.abs(gamma)))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 115 of bug id Math84
### Patch Diff Hash-SHA-256:

1d7fcc0186eaf0a94b871c85904472a6960259227cf55806034a284bc78f8e71

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(reflected, best)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 116 of bug id Math84
### Patch Diff Hash-SHA-256:

709e4134d072bf6e515fbce0a2824411c2c4eaf229249fb12f6946654a13270f

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(reflected, contracted)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 117 of bug id Math84
### Patch Diff Hash-SHA-256:

760bde4f5f10b10128d88d350c5384148b1d02292bcd105df71bc428222cb7ea

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) == 0) || ((khi) >= 0.75)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 118 of bug id Math84
### Patch Diff Hash-SHA-256:

db38001b873965a7731c518f3bd73d93ad38929a22183431d3793769a3dc8f7a

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((khi) - (khi)))) <= (1.0E-12 * (java.lang.Math.max(java.lang.Math.abs(khi), java.lang.Math.abs(khi))))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 119 of bug id Math84
### Patch Diff Hash-SHA-256:

8c7c45a08c9c8053f9a6a741120cfe674da56b9374a4d3e6291c42093541bd23

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(khi)) <= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 120 of bug id Math84
### Patch Diff Hash-SHA-256:

81573c02edc4c26db648162b2d7dd4b8a8c316560b0c38dc24a9cf64f6f7c278

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(best, reflected)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 121 of bug id Math84
### Patch Diff Hash-SHA-256:

203ac354f2545b6e33801e88321b397c0b89ad1e9d4511e9d33870e9561eea5d

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (!(comparator instanceof org.apache.commons.math.analysis.polynomials.PolynomialFunction)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 122 of bug id Math84
### Patch Diff Hash-SHA-256:

31d2dd11948b60495fc7c9917e578d0f93339fec2cd3570b12fdb38f0ef55dd8

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(gamma)) <= (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 123 of bug id Math84
### Patch Diff Hash-SHA-256:

99a199605967facb378ec48e6fef54437759328813cba0ee8efc92ecedb6d2ce

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= (-(khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 124 of bug id Math84
### Patch Diff Hash-SHA-256:

d4f6e5ce39e6f93a1cfbd4c939d2963f0bcf7c2bd411a279fa1cf6dcf7f49bf1

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((java.lang.Math.abs(khi)) < (khi)) || ((java.lang.Math.abs(khi)) <= (java.lang.Math.abs(khi)))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 125 of bug id Math84
### Patch Diff Hash-SHA-256:

5d677fb9d7a795698d1bcdd574d951ab075473a2c233a7e529639ae789ed3c13

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator instanceof org.apache.commons.math.stat.descriptive.SummaryStatistics) == false) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 126 of bug id Math84
### Patch Diff Hash-SHA-256:

bea91038980817addbdba88e7ddafda47077ce47a02a158c265fd35266b15343

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) == (khi)) || ((khi) == (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 127 of bug id Math84
### Patch Diff Hash-SHA-256:

adff94c14300658fb5c3a6a02c36b7a83bb2cdcabf33a632a0aca2bb2f9557aa

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((0.1 * (khi)) < (khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 128 of bug id Math84
### Patch Diff Hash-SHA-256:

9868cfede4ae411c3a8703032e3cb2e29bf908c2e689eca49ca5dd50fe2a70e7

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > (-(khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 129 of bug id Math84
### Patch Diff Hash-SHA-256:

8af493b3377c262a93700e70dc60bedb3ac16f36b191c96c9acd7b7efbfd4c6c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > 0.9999) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 130 of bug id Math84
### Patch Diff Hash-SHA-256:

77693e445040e8601c5e7974875bb0562f315bb37c16a59464b2ab12eb085107

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((gamma) > 0.0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 131 of bug id Math84
### Patch Diff Hash-SHA-256:

0643dbf7afea8d223e4b3a905d44fe26da13133c01b0e35dc2d7aa2c4f2f7268

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) >= (-(khi))) && ((khi) <= (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 132 of bug id Math84
### Patch Diff Hash-SHA-256:

8c54feb71dc744e7cf26477a5a8b6a047f7607e3f323037265d6639b6cc05569

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) > 0.1) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 133 of bug id Math84
### Patch Diff Hash-SHA-256:

c798e49585a4e2807c76858b3b7386f398e87034d32644ad94366cd32d9fcb24

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) <= ((khi) * (khi))) || ((khi) <= (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 134 of bug id Math84
### Patch Diff Hash-SHA-256:

4c914c29c291bb61a25fd6e7b52fc59157a13ee42c2bba7e1a3d2106167cf838

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) >= 1.0E-4) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 135 of bug id Math84
### Patch Diff Hash-SHA-256:

479ee637e23f12caeaa03079bf938ac6fe72ff0bf7164a58c6639d4eef44983b

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (!(java.lang.Double.isNaN(khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 136 of bug id Math84
### Patch Diff Hash-SHA-256:

ffde81832818bf53a44e5c3d668184194c9044bd187f5ad621a389c1fa2525a4

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (!(java.lang.Double.isNaN(gamma))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 137 of bug id Math84
### Patch Diff Hash-SHA-256:

0ba09d95108a61848989fdccf92d80ae83fabe929af2b6d7211dd1762a227533

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) <= (khi)) || ((khi) == (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 138 of bug id Math84
### Patch Diff Hash-SHA-256:

776cdcfcadcc409271db0e14fb43354cc135fd757f2d6d10ef32a8175a53ce50

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (!(comparator instanceof org.apache.commons.math.linear.SparseFieldVector)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 139 of bug id Math84
### Patch Diff Hash-SHA-256:

4dc57a077764adeb751958adf5303d4acc34c09bfb4afa170c29a5c966e7a9b6

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((java.lang.Math.abs(((khi) - (khi)))) < 1.0E-6) || ((java.lang.Math.abs(((khi) - (khi)))) < 1.0E-6)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 140 of bug id Math84
### Patch Diff Hash-SHA-256:

dbf96d1dc5487e6a01e319a0f631712d8cae5ab12662de0696e77bdc4c177127

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((((khi) <= (khi)) || ((khi) == (khi))) || ((khi) == (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 141 of bug id Math84
### Patch Diff Hash-SHA-256:

7f9d034e0deba8c59ffcd98ca439e0da5572baa9a3128fe7d2dc4f552812286c

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (((khi) == (khi)) && ((khi) == (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 142 of bug id Math84
### Patch Diff Hash-SHA-256:

00a98c33d8c4803650319b263306e95b829f2f402347058e4599a388dda00735

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((java.lang.Math.abs(((khi) - (khi)))) < 1.0E-6) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 143 of bug id Math84
### Patch Diff Hash-SHA-256:

ff54fca9db712fe4ebc79971a2bfea63de7a415e3bb586671a2fd75632b77ab2

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((khi) <= ((khi) * (khi))) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 144 of bug id Math84
### Patch Diff Hash-SHA-256:

6b970dbd32f97e1a7ea9b9547aed805b3fb62621adc1876be6bab2f8de9a595d

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if (org.apache.commons.math.util.MathUtils.equals(khi, khi, khi)) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 145 of bug id Math84
### Patch Diff Hash-SHA-256:

8b275f9ed777066a2214a120ef7b4a2e0ae6c5e2fd3199b7222c50b77fc47655

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(best, best)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 146 of bug id Math84
### Patch Diff Hash-SHA-256:

2a008f709ee63081e3e2c51925db0299bde15d3f7be590e56ab7021300435701

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(contracted, best)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 147 of bug id Math84
### Patch Diff Hash-SHA-256:

da8d8aac31c7a3000799c790dcb2cf3e15c553257e55b60de8079e1878dceaf3

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(best, contracted)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 148 of bug id Math84
### Patch Diff Hash-SHA-256:

0e6a1d64a962ff731e3d9cfe80b62314ca140b6b46e11d652457efc65cfbca9d

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(contracted, contracted)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 149 of bug id Math84
### Patch Diff Hash-SHA-256:

2fb828526d6fb8a33e329d05a5c77b9a51b1d8a337ca9f17d4ac6ee201a2c6f0

### Patch Diff:
```
--- /original/org/apache/commons/math/optimization/direct/MultiDirectional.java	
+++ /fixed/org/apache/commons/math/optimization/direct/MultiDirectional.java	
@@ -34,7 +34,7 @@
 				return ;
 			}
 			final org.apache.commons.math.optimization.RealPointValuePair contracted = evaluateNewSimplex(original, gamma, comparator);
-			if ((comparator.compare(contracted, best)) < 0) {
+			if ((comparator.compare(contracted, reflected)) <= 0) {
 				return ;
 			}
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---