
# Patches of Math8 from Defects4J 
Total patches 82
## Patch 1 of bug id Math8
### Patch Diff Hash-SHA-256:

86269e866dc956db8587d7c19c0b4da7237acf49ad86d93e8b93274850c9b4f8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons.get(sampleSize)) == null; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math8
### Patch Diff Hash-SHA-256:

65bde5106b23f553b24f8898feb12001b01ae8f998b8fcab6ee0ef612df5f89b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize <= 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math8
### Patch Diff Hash-SHA-256:

319a6c3a72f3b02bfcdc1fdbaa5d8528e2d13ba91114744bf9bf077cca6c7d16

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < sampleSize; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math8
### Patch Diff Hash-SHA-256:

ba1e33fa150256b537cf4650c767711500bebada2377fbcb333ac2b0b76a4ecf

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (probabilities[0]) != 0.0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math8
### Patch Diff Hash-SHA-256:

9c6a1c05fa226f88eedbaecc1ba98c37840a70b1be779f4fdf1749de44a41e90

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > 1; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math8
### Patch Diff Hash-SHA-256:

542f49e6216550274810307fa57caca0b3fb874fcdd5ca93a5bd57242e1f76b5

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (-2098); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math8
### Patch Diff Hash-SHA-256:

faf550806740a0dc34c6d28f21d651165ebba300a0f20e61f64f5b3fb3148c36

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize == 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math8
### Patch Diff Hash-SHA-256:

b052ff047c29401adb8b7c2184f079784ebf673b1bb6ade9097383c7a11d459d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; java.lang.Double.isInfinite(probabilities[0]); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math8
### Patch Diff Hash-SHA-256:

61959a1a9f03fe35d44cc6dbf8d447c5657da109c103b6f07fbdb1a298a3df59

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (sampleSize - 1); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math8
### Patch Diff Hash-SHA-256:

6be70887b5bb1e5173619aeb842589a503c9d0efc16450ae4d83ff5ab8353a1d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize >= 5000; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math8
### Patch Diff Hash-SHA-256:

cddf059f249cb2c145fb2fb7b994d3b588ff9a7b9d498ebad6fb1982cca0f71c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < 1; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math8
### Patch Diff Hash-SHA-256:

5993b8d53b5c93319e1706039651ea8cf11998d68d4381de27ffbc8e6e5530c4

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize + 1) < sampleSize; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math8
### Patch Diff Hash-SHA-256:

9b5e1adf3ace8c1a37f9b4399dab109ebee0257684adf1f993bacc318b950467

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (sampleSize * sampleSize); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math8
### Patch Diff Hash-SHA-256:

cfcbdd681b1e2046e3e6098f811e5ed9367b1481efbc8768431486c0549f3df1

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; ((sampleSize >> sampleSize) & 1) == 1; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math8
### Patch Diff Hash-SHA-256:

95b86a302d76b8de0d61bc0200dd151303d2487a134ae84a3be94538573a531d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > 709; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math8
### Patch Diff Hash-SHA-256:

ab74db721166f0cf665181edd27779530c8774e2e854694b6c72f3b37b2d3c98

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize != sampleSize; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math8
### Patch Diff Hash-SHA-256:

727cb3e27b13e6c715c727ce7f2eeae2889faf2fae7010a190fd34e8e77c0c27

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.util.DefaultTransformer; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math8
### Patch Diff Hash-SHA-256:

f2dcca68aabf45a3aafaa54363ddb5c417f7f379adcbdcf1150da2f6cc7847d7

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; !(org.apache.commons.math3.analysis.polynomials.PolynomialFunctionLagrangeForm.verifyInterpolationArray(probabilities, probabilities, false)); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math8
### Patch Diff Hash-SHA-256:

887acd5e5f8fe941e58c13d7a0dfb86c3142b5c062db45e9ba4fcd0aad891c8d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > 2; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math8
### Patch Diff Hash-SHA-256:

69a5eaf9751ca540171b62f78b521ae57072713d3c53a45743be2193be627eaa

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize == 2; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math8
### Patch Diff Hash-SHA-256:

1dcc27f4687c9ee886e8065cd1a4d6f2d5877eb74d07a32bcf40ea85cf9a4c4d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize >= 2) && (sampleSize <= (sampleSize + 1)); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math8
### Patch Diff Hash-SHA-256:

4082d191400e0260a46b96d3ad01b45806315693f1b7a97fe01e2285a9702fca

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; java.lang.Double.isInfinite(probabilities[sampleSize]); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math8
### Patch Diff Hash-SHA-256:

fb2b7ffec23ef7764905d31129cf6bc92bfb49f0eb20fdaffb02beb66ef85443

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize < 0) || (sampleSize > 1); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math8
### Patch Diff Hash-SHA-256:

5a21532dfbae6c699af2e6e4e33581c2c149605ae6b177576d91f0faf7544c7c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize == 709; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math8
### Patch Diff Hash-SHA-256:

ca936c01c890125d098d1b599faa74844e9674d2383ce0da9efeb5068b6ae49a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.geometry.euclidean.twod.Vector2D; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math8
### Patch Diff Hash-SHA-256:

9c0d560c4ef5c54874ca60c9219cbf27f9fbe8197e8840973f74573429e09c2d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > 1023; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math8
### Patch Diff Hash-SHA-256:

51559003f0a47b323b6f948b5727927a5a411916ae947a7b735ee1c0c2d6f313

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (sampleSize % 4); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math8
### Patch Diff Hash-SHA-256:

79fb6a93ef61ebdc36cfc713efbd1d4f41c3b3aee096377ffa1a196cb8acccf4

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math8
### Patch Diff Hash-SHA-256:

d888243b52b2f3a46a8b4aae0704c72cf526057f687075f99c0c214b85d65df6

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; !((probabilities[sampleSize]) >= (probabilities[sampleSize])); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math8
### Patch Diff Hash-SHA-256:

4ddb1071138cb1484cd5e66ab7d9d320c43f8445ab8d49c836defa452f256223

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize == 10; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math8
### Patch Diff Hash-SHA-256:

029097e2a1e25c13a2041ba8267c895faf4bb014b71ee062f94338fba0ee4d8b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (++sampleSize) < (--sampleSize); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math8
### Patch Diff Hash-SHA-256:

021374345a2c2c2689924c58c496564e7f36447e03223ef43eadaf6d1dfbdbe9

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize & 131072) != 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math8
### Patch Diff Hash-SHA-256:

c94b0c865857ff664135ac8fee729ab61091c5180f8c8dd8a3780b1456e36f6f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize == (-1); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math8
### Patch Diff Hash-SHA-256:

caf08cdfbbd1059b36e01b75bebab58df16e0abaf501edef0b61bffb62510ec2

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; ((probabilities[0]) * (probabilities[1])) < 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math8
### Patch Diff Hash-SHA-256:

7e2495f7249757c0fe2a9a5e2a707b9eb3db17e97ada99208670439a35a16e97

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize == (sampleSize - 1); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math8
### Patch Diff Hash-SHA-256:

ede90e5eb33f5f8def2ba33d93ca1db86abc28a612f26b207b2b2b00415ba98f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (probabilities[sampleSize]) < 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math8
### Patch Diff Hash-SHA-256:

cbccec95060a0d6cc83c17dce1911cd3da398ad9a1c05608fc66e9c426f757ce

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > 5000; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math8
### Patch Diff Hash-SHA-256:

525a3f75455c80ebd48b61690854329c2671ef1f47ff0cda389a275c9d9705dd

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.util.Decimal64; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math8
### Patch Diff Hash-SHA-256:

ed0bdc8986e9646a7657e338d73a71f30fc93d95866f2f2c83d11e3bde3bdd0a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons.size()) == 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math8
### Patch Diff Hash-SHA-256:

27964ae9cd745431f7b7906a86b1d3e7ff61a9fa56cd1249307fb6cc542c902e

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (probabilities[1]) != (probabilities[1]); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math8
### Patch Diff Hash-SHA-256:

3165fe74ec1f398a9b095479c868080dea97afa349c4afa3002a9904ca757bb5

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (sampleSize - sampleSize); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math8
### Patch Diff Hash-SHA-256:

4862cce6647f44d753ae0391d2118021cd33cf760fbd3fbec6ede197f8df0875

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize - sampleSize) > 5; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math8
### Patch Diff Hash-SHA-256:

ed8f2d733ee88f070c8a2af71f60317df44b648656cb854f5b44df0299209bf8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize == 0) || (sampleSize == 0); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math8
### Patch Diff Hash-SHA-256:

53b5be39aba4dd66b0797df7b2c2a21a6bc30bf50648c65721d4a64c32d906a1

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > 20; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math8
### Patch Diff Hash-SHA-256:

2d0af0fd85fb47e4733df8720180fd1e4832bd8101a4fd4ea0e24cfe3086768b

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize > 5) || ((sampleSize == 5) && (sampleSize != 0)); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math8
### Patch Diff Hash-SHA-256:

a6bc3253a2603876f6725e5ee24ec3f919d5bd0eb7b0e073755a3511d96b5253

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; org.apache.commons.math3.util.Precision.equals(probabilities[1], 0.0, 1); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math8
### Patch Diff Hash-SHA-256:

2901972c089973d2529036b63bd032bd2e473a9aa7d74e411d1fd32ecf7c7521

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (random) == null; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math8
### Patch Diff Hash-SHA-256:

c68cb38cfa2f366dd4c603fd6863a420355904e769913f6e69937fad58058e60

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (++sampleSize) < sampleSize; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math8
### Patch Diff Hash-SHA-256:

31b50bf62316d1a776c3bc0041be1eb789954e561d09e77271132f88ec2ee1be

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize <= (org.apache.commons.math3.util.FastMath.min(sampleSize, (sampleSize - 1))); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math8
### Patch Diff Hash-SHA-256:

55bb60ae0682ff54cd0dfe091824ec47ec3e7ab306bfd5f0a4a8db4c348ca4a8

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (probabilities[sampleSize]) == 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math8
### Patch Diff Hash-SHA-256:

637344480d08dea47b02ab6f0a469be77edb7428c285b39a3b75a9d0845a26bb

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (random) instanceof org.apache.commons.math3.util.TransformerMap; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math8
### Patch Diff Hash-SHA-256:

528524ad87a6bb826c9abee2d149ec470c9b34111143e3dac3364df88a68bee5

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (random) instanceof org.apache.commons.math3.fraction.BigFraction; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math8
### Patch Diff Hash-SHA-256:

cee475c49d16cdd3ddc74f94eb2c6ab36b3b1a0a6badc983d7237c9da05d7f95

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; ((probabilities) != null) && ((probabilities[sampleSize]) > (probabilities[sampleSize])); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math8
### Patch Diff Hash-SHA-256:

a2eb100db4eb897e119c6ba507490a5ab26e2d0aa894b6589faa1490f36430d6

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (probabilities) == null; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math8
### Patch Diff Hash-SHA-256:

86b155cc598392a4631d232a0e7cf57da3f2ad1af45a7d816dec4e38d7a78542

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize - sampleSize) > 1; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math8
### Patch Diff Hash-SHA-256:

531b47221761a3050090a33524140f966248629c472b85ca5da709753c1c0708

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons.get(sampleSize)) != (singletons.get(sampleSize)); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math8
### Patch Diff Hash-SHA-256:

7df80025c4c9ee9e277d78a625f8c6b71c586a1a778668cabe1109e803c6df3d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize >= 7; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math8
### Patch Diff Hash-SHA-256:

42b15df52c0bfb8b40e3f8d89ca83379f96575e99fece5a50a70658dfa55f2bc

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > sampleSize; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math8
### Patch Diff Hash-SHA-256:

298a99710dafbbc17467a3c90491b967f967f13c6b81cffe217b1aa3b1add0c5

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize > 1) && (sampleSize > sampleSize); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math8
### Patch Diff Hash-SHA-256:

d5871256420cddc6b4764b615537f8e8414d3023ba42cffec435a6711a83a877

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > (org.apache.commons.math3.dfp.Dfp.MAX_EXP); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math8
### Patch Diff Hash-SHA-256:

a5a977616a1c0688c5261a27f19840dab2ad50c34f1149f38cd2c1e4e1a2dbfc

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.stat.descriptive.moment.VectorialMean; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math8
### Patch Diff Hash-SHA-256:

051baa93ffefb35ab329217ddad44b571e281184d77d5b00e3c6d16961e4d83a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize & 1) == 0; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math8
### Patch Diff Hash-SHA-256:

ac9dd9e005e629cf56c2dd9a05e9c66337a464982396fb73d49f35387b2ad857

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize == (sampleSize - 2); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math8
### Patch Diff Hash-SHA-256:

1ed58425efb9e4c38b51bd02fd54ea9f927c392be2e8cafff7ef0e361e1a9747

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; java.lang.Double.isNaN(probabilities[sampleSize]); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math8
### Patch Diff Hash-SHA-256:

cd52ea3e51c68a7236e77c53c3c886f7f0e322cba1f202cc906e00327b9dc47a

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.geometry.euclidean.threed.FieldVector3D; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math8
### Patch Diff Hash-SHA-256:

8ae8d647be465cfc403123bb7e3dfd1ade4ac2609ec410bdb7d791f6a650d6e4

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.util.TransformerMap; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math8
### Patch Diff Hash-SHA-256:

9d823a5f64c50a504a4cef1a1d6d71a0df93e7492053d99a11bcc5033bb0365e

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (sampleSize >= sampleSize) && (sampleSize < sampleSize); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math8
### Patch Diff Hash-SHA-256:

9b2995b0837af9188e8b34a50a6917977e293b36224d52cecd0a0d2ea7d516b3

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (-277); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math8
### Patch Diff Hash-SHA-256:

c2622405b7b6a90f6260f657124bf645794232b1a8cd3cad7cb68eb0e4692526

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.util.BigReal; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math8
### Patch Diff Hash-SHA-256:

af2a745ac2976529cc03f39266d7eeb78d0a2a1bd214002c0e2bf81e2033ed61

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize >= (org.apache.commons.math3.dfp.Dfp.RADIX); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math8
### Patch Diff Hash-SHA-256:

9812a4605f25c1e0d03e9907572da2d07d880ba68c9faa59eb4fab5f3a28842f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) == null; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math8
### Patch Diff Hash-SHA-256:

2978e6ae8c5f3237c590decb0ccc79bcbc38d322e32819bb93a3ce9525620b67

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize <= (sampleSize - 1); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math8
### Patch Diff Hash-SHA-256:

6b816e1b92e72ea484a34a2c07a22cf9499c3e0e9cbf95ee246365de1a5c308e

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize > 5; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math8
### Patch Diff Hash-SHA-256:

972c4810b17ec6c78b8b2fa5044a51966c0a2712cddf3a8b13d60ecc00edb0d7

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (sampleSize - 3); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math8
### Patch Diff Hash-SHA-256:

199956ffc7a0c57670be5888f9c52845d83af3515ba2d9cf0556cfcbfb5ca290

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof java.lang.Number; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math8
### Patch Diff Hash-SHA-256:

c52b2704a2144c7d755e1c847d22f47a152560d75fded2a3b982c4b469121d29

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; sampleSize < (-1074); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math8
### Patch Diff Hash-SHA-256:

539f22a89b8554bb7e96fe41b25b7e53a8fa2d10b72c1f274a6076a87cb99fd5

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; ((probabilities[sampleSize]) < (probabilities[sampleSize])) || ((probabilities[sampleSize]) > (probabilities[sampleSize])); i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math8
### Patch Diff Hash-SHA-256:

a8861dcb1bfb69553f709b2e01f7941808d12278bb1f766f56d2c3a43cab33eb

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,7 +68,7 @@
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
-		for (int i = 0; i < sampleSize; i++) {
+		for (int i = 0; (singletons) instanceof org.apache.commons.math3.geometry.euclidean.threed.Vector3D; i++) {
 			out[i] = sample();
 		}
 		return out;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math8
### Patch Diff Hash-SHA-256:

aca670d6d85826b821f069dcb52623375374df06f4655bb9cdc7677dab335ca1

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -67,7 +67,7 @@
 		if (sampleSize <= 0) {
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
-		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
+		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(sampleSize).getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
 			out[i] = sample();
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math8
### Patch Diff Hash-SHA-256:

75adbf470bc6fe38635948e4fcac6c6b20ff078a294234378adedae5d65e176e

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -69,7 +69,7 @@
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
+			out[i] = singletons.get(0);
 		}
 		return out;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math8
### Patch Diff Hash-SHA-256:

68bfbb237dcc74dcef10d565660431ce5d0ce72a0eaf3924c9dfeadca064011f

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -67,7 +67,7 @@
 		if (sampleSize <= 0) {
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
-		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
+		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(sample().getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
 			out[i] = sample();
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math8
### Patch Diff Hash-SHA-256:

f6cf1f3b7e77ae9acdd0bd8fe4608733c3fc9729d5b8627e383717d48ab6d01c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -67,7 +67,7 @@
 		if (sampleSize <= 0) {
 			throw new org.apache.commons.math3.exception.NotStrictlyPositiveException(org.apache.commons.math3.exception.util.LocalizedFormats.NUMBER_OF_SAMPLES, sampleSize);
 		}
-		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
+		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(((singletons.size()) - 1)).getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
 			out[i] = sample();
 		}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---