
# Patches of Math41 from Defects4J 
Total patches 46
## Patch 1 of bug id Math41
### Patch Diff Hash-SHA-256:

1db6adf5f6012cb2c0be493ba6f18e5b3cdad50322c23fd0796912623586d5d2

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length & 2) != 0) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math41
### Patch Diff Hash-SHA-256:

22df080d524f11a3fee3120900aedc89f45ae0174141b850c76c2edce5ae5dae

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length & 1) == 0) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math41
### Patch Diff Hash-SHA-256:

5b1ce51fc9378a7cf7765851aa5cbd68e9bcbbbdfee7f315ed3a667adc4141dd

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if ((length == 5) && (length != 0)) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math41
### Patch Diff Hash-SHA-256:

d3cc83480a46b992e093b92dc63c24f9d76fa3c6f288f4821c8b16ac4d18449a

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if (mean >= length) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math41
### Patch Diff Hash-SHA-256:

7e075cd4347cc842d6e8f2583a4838779729d398d236fd22e676658a124b5f73

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length & 1) == 0) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math41
### Patch Diff Hash-SHA-256:

43e60444a6a7f99d3e083cd6bbe188a614e33315aed0ce401770f1e6e9aae844

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((((length & 1) == 0) && ((begin & 1) == 0)) && (begin < 31)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math41
### Patch Diff Hash-SHA-256:

db59406912289340a9092ad6d9fb6be7d7a515607b02fdb128affee287c6a1a3

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if (length < 7) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math41
### Patch Diff Hash-SHA-256:

498f7b5f3d0c9b9709fed90b8121a8d1129a8c83d9c6ac7ce541d0681ad04df3

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if (length <= 6) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math41
### Patch Diff Hash-SHA-256:

e113743473208a230ba1d20c676d46c1b928722cb3033e6c6bfe0135a51dd384

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (length >= mean) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math41
### Patch Diff Hash-SHA-256:

70de3aedc43213173f383d1c1c0eb15c4fa0666417016d097758d5fefdc38cb9

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if (length < 7) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math41
### Patch Diff Hash-SHA-256:

6a2c17dd0c463f98aaffaecce1c7d731d0aaef9612f7daea0698bd6ae615ada0

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((((length & 1) == 0) && ((length & 1) == 0)) && (begin < 31)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math41
### Patch Diff Hash-SHA-256:

f6b14302b29091a6aa03004d8f605b11e7f1b79e340007b1f4bb28d5d2a9b046

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (length > 5) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math41
### Patch Diff Hash-SHA-256:

9417ea3e123f89880a7ae5cc59b47ae017ea8d261e0200a713b4e61fb4ccf046

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length & 2) != 0) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math41
### Patch Diff Hash-SHA-256:

694706dee938d95c090610fbf0c59320d6150fab32f516cdd23246e3b9a86b48

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length - begin) > 5) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math41
### Patch Diff Hash-SHA-256:

4a718a18590bb6bcdd58189f9c6cbb9325a80369cde0af7f48f44c0592cf9fc2

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (length > 5) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math41
### Patch Diff Hash-SHA-256:

91ac8c2cb6013bb1cfb9638728594e273ab6336254d8a82990521b9b0a0ebfaf

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if ((length <= 6) || ((length % 2) != 0)) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math41
### Patch Diff Hash-SHA-256:

5084e19d81f384c499f6f423cf313d9493ff675ebd18561ec9015dd168567c4e

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if ((length == 5) && (length != 0)) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math41
### Patch Diff Hash-SHA-256:

1a89628fab013660d7d27c6f26cd658533feb4e5884cd1cad7d569b6eae12c17

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (((length & 1) == 0) && ((begin & 1) == 0)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math41
### Patch Diff Hash-SHA-256:

141e847026594b65948380338e9b77284927eb88f3a73ad337f6608c477637a9

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if (length == 5) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math41
### Patch Diff Hash-SHA-256:

c9fd8899ea7aec302efe40d08a2d8b7ab05e38c3b53cb2771a30e734eb2878e3

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if ((length <= 6) || ((length % 2) != 0)) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math41
### Patch Diff Hash-SHA-256:

8b0b3dc8b388726d6cdfdf887770b23a8584e0652f51c7d4049f422690659054

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length % 2) == 0) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math41
### Patch Diff Hash-SHA-256:

6d110b1d44aa09eaf51a9d3ae0e1c914ff8ecdf05ad4154b627d72a3842c2923

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((((length & 1) == 0) && ((begin & 1) == 0)) && (length < 31)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math41
### Patch Diff Hash-SHA-256:

78781acd04fb7d2060665c45342b29ce4c1f9156cd8aececee1f445eb031e8af

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length <= 0) || (length >= 7)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math41
### Patch Diff Hash-SHA-256:

1fdb25bef8855469cb406cf8815ea773ae40dad0febf3b2337e9a474b12a2b69

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if ((length & 1) == 1) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math41
### Patch Diff Hash-SHA-256:

a6fdb5204c6177f315f15371f6fa7bd8239d530a1ba2ddc137d5ccb092a847a9

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length - begin) > 5) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math41
### Patch Diff Hash-SHA-256:

8153e16dd187c89692fa6d9968d4d5fdacfc36a725870e6db1a21b85f3f8e690

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (((length & 1) == 0) && ((length & 1) == 0)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math41
### Patch Diff Hash-SHA-256:

9fa67cc66da159ea5ca5c0c9b20080c1cdec2c951625aec67cb07e66c6b612a0

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if ((length % 2) != 0) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math41
### Patch Diff Hash-SHA-256:

9ff11962bb4207154b1771806c043f5aa38dcecb3dff560b92798ede9280cb15

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((((length & 1) == 0) && ((length & 1) == 0)) && (begin < 31)) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math41
### Patch Diff Hash-SHA-256:

d65efc912073a2f0251e4e2033a2ebf9bc81c7760e8edaf3458b8fe655f2c450

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if ((length % 2) != 0) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math41
### Patch Diff Hash-SHA-256:

5cf09b436061c2e73144d312c7fa6d72dfa2725f60e1c1157501d429af2f5fda

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (incMoment = length > 5) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math41
### Patch Diff Hash-SHA-256:

aaf6ca3c266405636f2fe21eb1c5aa81fcd1bc9962080614372ca7dd3e6915e4

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (length >= 7) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math41
### Patch Diff Hash-SHA-256:

acc6248ae1388589faab8d162d89906eda63235adb7ecc20a80c270ec2098139

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (((begin & 1) == 0) && ((length & 1) == 0)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math41
### Patch Diff Hash-SHA-256:

4f7b0474fb818f7dc48af4d4f8b294071b4ca14c84f25b586f5d673ff9b2f21d

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if (length == 5) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math41
### Patch Diff Hash-SHA-256:

804449563eaebae72c65131f2de440602a95380c2b89c495dc7e750ce44975d4

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length <= 0) || (length >= 7)) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math41
### Patch Diff Hash-SHA-256:

93288d275d02adfb203ca0c9da2ea665428dfb3c81410bff95134969fae69737

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (((length & 1) == 0) && ((begin & 1) == 0)) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math41
### Patch Diff Hash-SHA-256:

fad899cb3ca744b0fdc2b5e492feafb95d99a7a54e9d26643bbaca855d18e136

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((((length & 1) == 0) && ((begin & 1) == 0)) && (begin < 31)) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math41
### Patch Diff Hash-SHA-256:

7814e4a35b35cf04b59cd714459157a72d745dbab745a5533e4390382aa6feea

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((length % 2) == 0) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math41
### Patch Diff Hash-SHA-256:

54c80b4a20520948ba1bdf6b07ef39b17632bef5256d392ddc48de5d85f52704

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if ((length & 1) != 0) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math41
### Patch Diff Hash-SHA-256:

ed813a353e47f1cc90af7a6e455054342d2a7aab7b1a9cfda792c544a4251c95

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -101,7 +101,7 @@
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
 			clear();
-			if (length == 1) {
+			if (length <= 6) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math41
### Patch Diff Hash-SHA-256:

1ab7c3c6867d61b6f900d14446b471c11b560615d96c69d6e71a53591b35bcbb

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if ((length & 1) != 0) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math41
### Patch Diff Hash-SHA-256:

f3ad508fae483d331f9ee4c0ead90b9ffdd67645c1bd371f8cc017f42afd7e84

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (length >= 7) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math41
### Patch Diff Hash-SHA-256:

3cb750923603efd1b4d2d7c1e14eb56cc726b0bb2ae0ee6a4a5935b01d8b3b66

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (isBiasCorrected = length > 5) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math41
### Patch Diff Hash-SHA-256:

03d49a66f6df536a255a6a82ec33e3076be688c28e813e128fa1a9e1ea79c135

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -152,7 +152,7 @@
 	public double evaluate(final double[] values, final double[] weights, final double mean, final int begin, final int length) {
 		double var = java.lang.Double.NaN;
 		if (test(values, weights, begin, length)) {
-			if (length == 1) {
+			if ((length & 1) == 1) {
 				var = 0.0;
 			}else
 				if (length > 1) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math41
### Patch Diff Hash-SHA-256:

0d59813ccd7d5e7afd1ca16cb1c4a6fa11a93bfe91d3ed60a57b4b86653af409

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -104,7 +104,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((((length & 1) == 0) && ((length & 1) == 0)) && (length < 31)) {
 					org.apache.commons.math.stat.descriptive.moment.Mean mean = new org.apache.commons.math.stat.descriptive.moment.Mean();
 					double m = mean.evaluate(values, weights, begin, length);
 					var = evaluate(values, weights, m, begin, length);
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math41
### Patch Diff Hash-SHA-256:

81664e24138ab247103ee2aff957cef2f805f8808a1a602851efcb8f8e8dcd5f

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if ((((length & 1) == 0) && ((length & 1) == 0)) && (length < 31)) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math41
### Patch Diff Hash-SHA-256:

6695e0a2b614c18bd2f2f2581fb751915de63e8a279335bb83b6928399497033

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/descriptive/moment/Variance.java	
+++ /fixed/org/apache/commons/math/stat/descriptive/moment/Variance.java	
@@ -155,7 +155,7 @@
 			if (length == 1) {
 				var = 0.0;
 			}else
-				if (length > 1) {
+				if (mean < length) {
 					double accum = 0.0;
 					double dev = 0.0;
 					double accum2 = 0.0;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---