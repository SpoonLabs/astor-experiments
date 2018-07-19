
# Patches of Math85 from Defects4J 
Total patches 109
## Patch 1 of bug id Math85
### Patch Diff Hash-SHA-256:

b7039f1232042e8e03186c25247db3f272ceb5fc21562050da2084cc22656482

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations <= 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math85
### Patch Diff Hash-SHA-256:

b23b299e721cf3a62f5702a29cfa1d017e4d637ebd95510c807479f097c84faf

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (initial > upperBound) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math85
### Patch Diff Hash-SHA-256:

f6781847fe9e2740f4699bf06c5871b8d9a600c67e1233e1e46580defd5c6948

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((initial < lowerBound) || (initial > upperBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 4 of bug id Math85
### Patch Diff Hash-SHA-256:

0e808a9b486c79ec4f0d344d15f97469c1bf117815d529289aa03270fad5bb1b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 5 of bug id Math85
### Patch Diff Hash-SHA-256:

5e7740793077138089a55557af2f54277cf4b40800f320cd9a851b1cef6f4b7a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((initial < lowerBound) || (initial > upperBound)) || (lowerBound >= upperBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 6 of bug id Math85
### Patch Diff Hash-SHA-256:

e5b42750e20d2fe5abd587c4cc0fb40db83fd138a2fc98015021df8c803e81d9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function == null) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 7 of bug id Math85
### Patch Diff Hash-SHA-256:

0745c8e45045b44570db0ba991fcec47f8cdfeea3f6b6682d3efc29d4037240c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (lowerBound >= upperBound) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 8 of bug id Math85
### Patch Diff Hash-SHA-256:

27b6413ab73fb3a99685e6d560179eab576ae762160fd0442e8ce4d6b52f66eb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (initial < lowerBound) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 9 of bug id Math85
### Patch Diff Hash-SHA-256:

6c2bb2e06363de0b60441b31bbc1ac1419ed4f5feabc9e1ac984df16ff666153

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((fa * fb) > 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 10 of bug id Math85
### Patch Diff Hash-SHA-256:

bc0326b10093b08260ae43c33c11c94174e9c46e0e1df7d7d50096a6a7643ed7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((fa * fb) > 0.0) && (numIterations < maximumIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 11 of bug id Math85
### Patch Diff Hash-SHA-256:

92301b295426e7787d03562e77a5e93c540ac2402776f91d49c9aa1494e997c4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations < 1) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 12 of bug id Math85
### Patch Diff Hash-SHA-256:

4d9c40ce7e0759d4c59778249e521d3477b5116b648bb3309c56bed451cdb066

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (upperBound == 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 13 of bug id Math85
### Patch Diff Hash-SHA-256:

a52ce2f618ee4206e2cf6e13d312ae02b55b8b3fdf3a841aaf4c57c807795bed

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (false) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 14 of bug id Math85
### Patch Diff Hash-SHA-256:

f84226ddabcb761ae6ce952a2bf9cb4246ddf4c0336be304cbace230746e93b5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((java.lang.Math.abs((fb - lowerBound))) <= fa) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 15 of bug id Math85
### Patch Diff Hash-SHA-256:

40c162b4558547db5348cae4705ffbd40534b89019f72667b40adbc1b24d41c6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (fa == 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 16 of bug id Math85
### Patch Diff Hash-SHA-256:

798fac151457e8e47bdff26e188d42037848ce5457541e06acf662dc4917e7f9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (upperBound < a) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 17 of bug id Math85
### Patch Diff Hash-SHA-256:

bfc0a9a8a72dcd078151ad492d57c557411044e743f9b121c1fbd7e58ff0e4ed

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (fa > 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 18 of bug id Math85
### Patch Diff Hash-SHA-256:

939cb8f03f0790f996bc0809e7fc9d631ff21c32de5d16b1b8243893930111dd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (b < 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 19 of bug id Math85
### Patch Diff Hash-SHA-256:

64cb7c0546a2a9d6cb7683667ddbd4bf8f29dbf78e3783e88218585d4500951d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((maximumIterations >= numIterations) && (maximumIterations < maximumIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 20 of bug id Math85
### Patch Diff Hash-SHA-256:

9ea37f5aed1d7ceb934f8a82215283ca8cfef9df70c1b786e7f9257797cb7607

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations <= 6) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 21 of bug id Math85
### Patch Diff Hash-SHA-256:

18058d3a2cb9282f1e604f12ed5d85c95efa8b989eadf7a6ef1e4d6a59bfcf84

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations >= maximumIterations) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 22 of bug id Math85
### Patch Diff Hash-SHA-256:

cb6ae19a18cc6b616f5a3b36452bbe91b076286d5cef550d7239ef3d744faa4f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (lowerBound > a) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 23 of bug id Math85
### Patch Diff Hash-SHA-256:

025d14b2e2c35e1b60e41596394f1aa127f92f70f78e98d561d44cb006aba136

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations < numIterations) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 24 of bug id Math85
### Patch Diff Hash-SHA-256:

974324933571a5f12f39cd3ba7b80d9fa3c4deca2639197245ff16767a21e3e8

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (initial >= b) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 25 of bug id Math85
### Patch Diff Hash-SHA-256:

7e012602f1fc6064d0529faf8165591b0463984a786f48f5c4cd931c8fa922b5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((100 * (java.lang.Math.max(b, upperBound))) < upperBound) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 26 of bug id Math85
### Patch Diff Hash-SHA-256:

c5a03bf0c592a9fbee97bfbacf24f74825498b74a76018e20066b33c1c74f3e2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function instanceof org.apache.commons.math.analysis.polynomials.PolynomialFunction) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 27 of bug id Math85
### Patch Diff Hash-SHA-256:

bb97bf3c185075afde586d6bc54fedf9ee317cfb16d1c3a5404a1e814795a7b5

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (fa > 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 28 of bug id Math85
### Patch Diff Hash-SHA-256:

d72e7397ca83d728a377633ce3eb34db418c05f518802a3940c8cf97fdd150f9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations == 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 29 of bug id Math85
### Patch Diff Hash-SHA-256:

be5d8b22b0618d18c9cebe8974446bc90ba1f0f342eb092cf250188ae046d518

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((((maximumIterations & 1) == 0) && ((numIterations & 1) == 0)) && (numIterations < 31)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 30 of bug id Math85
### Patch Diff Hash-SHA-256:

f8c676f57c62dd3f5f07250980eb7ff0de30dcab859e8e70af7e62cae4046a0d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((a - b) > (0.95 * (b - b))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 31 of bug id Math85
### Patch Diff Hash-SHA-256:

b6579e1a5ec5a8273d581578ae0ceaaf932323aba27afa00f64e34b6abcc516f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations < 1) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 32 of bug id Math85
### Patch Diff Hash-SHA-256:

db9bd363539e129e330addcbe1b218c8024b54b222533cd196267ad2d93f899a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function instanceof org.apache.commons.math.linear.SparseFieldVector) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 33 of bug id Math85
### Patch Diff Hash-SHA-256:

a3bb8e6b1a4875e41e5c6b6ca28fc176ee9235eeeb98a245c8a0f061b8ab9241

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((lowerBound > initial) && ((lowerBound - initial) > (0.95 * (lowerBound - lowerBound)))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 34 of bug id Math85
### Patch Diff Hash-SHA-256:

566d0bdd86668c1a5f2810324e993aa00ba228e7317eda2e3bce0c600a72e24a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (upperBound < 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 35 of bug id Math85
### Patch Diff Hash-SHA-256:

2d6003142d6d964dd25eebc1cc866a7eeb63d49884436e723ac4c5edff07f7d0

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((fa > 0.0) && (fa > a)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 36 of bug id Math85
### Patch Diff Hash-SHA-256:

7d364788202c9bb9cb408cb44cdb8b571586c7423887ffb93e4f4dcb0c371090

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations == 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 37 of bug id Math85
### Patch Diff Hash-SHA-256:

ec24d98277dc5cc0de54250a377fb75ed9df730c8b2219a9caee76f7c3c06c26

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (upperBound <= 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 38 of bug id Math85
### Patch Diff Hash-SHA-256:

e38c5ba239786b96ee8b670f1390be95e80259c89c2d70ded533ad316e484e86

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function instanceof org.apache.commons.math.stat.descriptive.AbstractStorelessUnivariateStatistic) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 39 of bug id Math85
### Patch Diff Hash-SHA-256:

173301a70be9a5ce6d398301ef5dbeed547377ad684c525d1a07eceb43771c3f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (b == 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 40 of bug id Math85
### Patch Diff Hash-SHA-256:

2f9bff573f224a396c924af6b973dfe5691b6b03adc84158aaba969977d2d2b4

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations <= 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 41 of bug id Math85
### Patch Diff Hash-SHA-256:

4b768c57442e5c1311bcf88adaebe544bf2804cf642877fcdf51bdf51f4c4cce

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations < (maximumIterations - maximumIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 42 of bug id Math85
### Patch Diff Hash-SHA-256:

5d54b8ffcfbb582b50d99f517a06cf597a7b45744164a20bec5c732b8dd8488f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((100 * (java.lang.Math.max(b, initial))) < initial) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 43 of bug id Math85
### Patch Diff Hash-SHA-256:

a8dbdfbf737d43f612ccc0219514520cc98002b2740a6d996e25ace2a4c734dd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (initial < 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 44 of bug id Math85
### Patch Diff Hash-SHA-256:

4f87a51df406a32e1d37954a9dea668e0d646ec099af1b23e8c1abaea726eea1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations < (4 * (maximumIterations - 3))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 45 of bug id Math85
### Patch Diff Hash-SHA-256:

94093bb1c604210d73beb0088221041ed9a6f2af3f079c85c0fde0cafd3e9abb

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((initial == 0) && (upperBound <= b)) && (b < 0)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 46 of bug id Math85
### Patch Diff Hash-SHA-256:

d8c41d03bd2460a391a7215e1cf44b807804b8e42e041338229cabc1a7a51d4d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function instanceof java.io.BufferedReader) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 47 of bug id Math85
### Patch Diff Hash-SHA-256:

2a0b98a8c3576db68ba86c4559fddda73484a43a365a5aed28fde2f5dcb5bfba

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((initial == 0) && (fb <= fa)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 48 of bug id Math85
### Patch Diff Hash-SHA-256:

e31da1237ed7b5e7c61ea3f246db89a3b96254ddc7a1340c3ed2f55cd75880da

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (fb > 1) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 49 of bug id Math85
### Patch Diff Hash-SHA-256:

dd064567a94a2d7102b6d987a8c931671b6e3ae612089040b75f1e55402731a2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations < 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 50 of bug id Math85
### Patch Diff Hash-SHA-256:

6a0c4445a832ce840ded4c58872aacf9c6d871f6a3d38b240933c6854c6319d9

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (lowerBound > b) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 51 of bug id Math85
### Patch Diff Hash-SHA-256:

d45ff0c008810434725801fd7a69a1df0d6415448776db13ee03c893d9516ada

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations < numIterations) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 52 of bug id Math85
### Patch Diff Hash-SHA-256:

b8f320a11a2841dfe474b41687e280f4ac63106648a7a4643a0fb57f420ee10d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function instanceof org.apache.commons.math.stat.Frequency) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 53 of bug id Math85
### Patch Diff Hash-SHA-256:

15f52249ea6ec9dfa13c394709a68b66b9d4cae8aef06c1a3f71614359b623de

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (java.lang.Double.isNaN(upperBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 54 of bug id Math85
### Patch Diff Hash-SHA-256:

4840b07a55c4536f21abb735c0694d22bf3fcd56aea952a697fc886a77b00ded

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((java.lang.Math.abs((upperBound - a))) <= (1.0E-12 * (java.lang.Math.max(java.lang.Math.abs(a), java.lang.Math.abs(upperBound))))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 55 of bug id Math85
### Patch Diff Hash-SHA-256:

f7958d29b9ea9a0634be7ead96dc7acb0432169c3d9a07d4f3ff3345752c076e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (numIterations < 0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 56 of bug id Math85
### Patch Diff Hash-SHA-256:

a375a4ab6843401d641dc850fd09440937fe39d4257ff0d8b67f7bc516afc85b

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((maximumIterations == 0) || (numIterations == 0)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 57 of bug id Math85
### Patch Diff Hash-SHA-256:

feee5629f1bd3e5c8816d3d43f8dfa8587edc3e8bb09fc6734e3c7a0344fad93

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (java.lang.Double.isInfinite(initial)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 58 of bug id Math85
### Patch Diff Hash-SHA-256:

03abab1b794cf9926c2ccb54c856748c4a3fb8676bcd1c46c432dd144e00904e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((java.lang.Double.isNaN(a)) || (java.lang.Double.isNaN(b))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 59 of bug id Math85
### Patch Diff Hash-SHA-256:

03cf0f9cc6fa5bc000fa33ff01aa7a87fbb87dcb65f4b3ce244bfe601d720f3a

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((initial > 1.0E15) || ((maximumIterations > 1) && (initial > initial))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 60 of bug id Math85
### Patch Diff Hash-SHA-256:

f8fbed6e476ccd42fb89a1ac7cb0112facd09122e37174d66bfd5bd26c332633

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (fb > 999.9) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 61 of bug id Math85
### Patch Diff Hash-SHA-256:

78de42e10c13e7f9919ee7a2dca7c757d2615af9388710d8e77940a253dc3703

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations == (-1)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 62 of bug id Math85
### Patch Diff Hash-SHA-256:

9e4af4f4f5001dd35168c5782be541a39295e4cbca9868a3c6968d6f5d1aa2a6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations == (maximumIterations - 1)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 63 of bug id Math85
### Patch Diff Hash-SHA-256:

1a4118102391b8fbc4ac53804b80430234513230efb74f8ed2d309a014205885

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((numIterations < numIterations) && (b > lowerBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 64 of bug id Math85
### Patch Diff Hash-SHA-256:

542bbdd28ef26d6fd6524c95056fa7a29b91aa0488e0f31258e6c45735537a06

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((function.value(lowerBound)) == 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 65 of bug id Math85
### Patch Diff Hash-SHA-256:

86a26bc8515351d615e98140067c1bbce538ac287c529aecf0ec84ff53057b24

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations < (maximumIterations + maximumIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 66 of bug id Math85
### Patch Diff Hash-SHA-256:

5e1649ea414ab55eca7fe9f71cb227409e6c1e0399ee8a22b95d86c9382b59c2

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((lowerBound > 0.0) && (lowerBound > lowerBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 67 of bug id Math85
### Patch Diff Hash-SHA-256:

e5163fb62ddd5ac238263cacbb980ae10c732e063117258821c0f5a18b7dbc8e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (lowerBound > initial) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 68 of bug id Math85
### Patch Diff Hash-SHA-256:

ec150cc6cd2ced18ac5b95b6d6cefe3eb82a8ce344c5314b395d3a300c2ee774

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((lowerBound == initial) || (lowerBound == upperBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 69 of bug id Math85
### Patch Diff Hash-SHA-256:

4b8db185ea7e005cf8e26ceab2ca48a49ce1c90e15cc254880a910d923ec8e50

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function instanceof org.apache.commons.math.linear.BigMatrixImpl) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 70 of bug id Math85
### Patch Diff Hash-SHA-256:

7984712fb65a54a38dc96b8449a39982115e9c22d590d246ec3fc97a48a9de70

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (a > 10.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 71 of bug id Math85
### Patch Diff Hash-SHA-256:

c9378705a47016d07949f0278efdc1c6cbd8b8462916dbf496cfbeafc9c79efe

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((2.0 * lowerBound) >= (((1.5 * initial) * initial) - (java.lang.Math.abs((lowerBound * initial))))) || (lowerBound >= (java.lang.Math.abs(((0.5 * initial) * initial))))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 72 of bug id Math85
### Patch Diff Hash-SHA-256:

0d1e0b9d5f68a009745db9b6d9d39c0c6a7f62036bd196d690c9fa879704f574

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((java.lang.Math.abs(fa)) <= (0.1 * fa)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 73 of bug id Math85
### Patch Diff Hash-SHA-256:

19ed06b63ca0874762816b12aa9ce14df72b9649e5b535f3c1e16974b54d976f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (function instanceof java.lang.Comparable<?>) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 74 of bug id Math85
### Patch Diff Hash-SHA-256:

8662e5db792ebcd20259ad3b06fc5c95dfede7800446b91cef027dec8c35efb1

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (java.lang.Double.isInfinite(a)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 75 of bug id Math85
### Patch Diff Hash-SHA-256:

8fe64c2983cb3752cd8393c40779302e413288a11507ed935e4a03b70cd4666e

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations < (java.lang.Math.min(maximumIterations, maximumIterations))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 76 of bug id Math85
### Patch Diff Hash-SHA-256:

cd08124133713e02dcd6d5f660fcc9ada932fe392e527b90b56bc597722cfe3c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations < maximumIterations) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 77 of bug id Math85
### Patch Diff Hash-SHA-256:

1fb1ded12d6641af4ca210e08d9df469c99dd848dcc848ae37b7256e300a132d

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (maximumIterations != maximumIterations) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 78 of bug id Math85
### Patch Diff Hash-SHA-256:

4804a8dcc9c33ce18dcabc8349465d52bcd549a4f9ecd282e95a833fcac497cc

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (a > a) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 79 of bug id Math85
### Patch Diff Hash-SHA-256:

5ec3aa4ee65421dfc56b492bec5da00c0db7ca6a61fe9a8e6a1dab3a46248f93

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((++maximumIterations) > maximumIterations) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 80 of bug id Math85
### Patch Diff Hash-SHA-256:

63146cc8819ea556c444640f082802f2101ee46db749d4c55be9f90968513707

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (java.lang.Double.isNaN(b)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 81 of bug id Math85
### Patch Diff Hash-SHA-256:

8974b67275483b2c730058f9e772287b03a3ab1ec7c3a3872b20b9741f015bbd

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((a < a) || (a > a)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 82 of bug id Math85
### Patch Diff Hash-SHA-256:

dbcf9cb388c3cec186dbae7d73474d1b2272dbeed966ef57c64fb1028589c965

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (a < a) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 83 of bug id Math85
### Patch Diff Hash-SHA-256:

5f922028fe1b3dc705699e189cf20796e3a99ce9611e82ed9ff85772985778a7

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((((a * a) > 0.0) && (maximumIterations < maximumIterations)) && ((a > a) || (a < a))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 84 of bug id Math85
### Patch Diff Hash-SHA-256:

8c62f5f188c43e59838ebb951b8ed97f1ea1ca2ec3dde335dc8e8aac2bea960f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((a > a) || (a < a)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 85 of bug id Math85
### Patch Diff Hash-SHA-256:

851982d1088f9cf0f64ed8d8fcdd5214683356458025bcd5ff9c461cbe668aef

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (b < b) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 86 of bug id Math85
### Patch Diff Hash-SHA-256:

7a29b5fed5f81df0a22434cbb196021d55d80c0b8d8eb1321a4c8c580481fa31

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((b < b) || (b > b)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 87 of bug id Math85
### Patch Diff Hash-SHA-256:

04d750b310952b8161f2d25ccde622275cda40dceaf2e9941335542c49bfaf92

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((initial < initial) || (initial > initial)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 88 of bug id Math85
### Patch Diff Hash-SHA-256:

5979c84cce41fedeb2d22628fbf5a0265dd1085162150346574d0cfa10619292

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((a * a) > 0.0) && (maximumIterations < maximumIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 89 of bug id Math85
### Patch Diff Hash-SHA-256:

06ef5f0c00784910a7c271f5ec5624e6946e4e8f0b8b215b1e5d75c1b8195e15

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((b > b) || (b < b)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 90 of bug id Math85
### Patch Diff Hash-SHA-256:

b2111e89f7b4ef0abfe1911c3fc8b2161fe4f57e87164cc0f5fb17a71311cf8f

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (initial < initial) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 91 of bug id Math85
### Patch Diff Hash-SHA-256:

72db4561900814864740c7322606b90796e933692b60091c7afa87f46a5abf63

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((initial > initial) || (initial < initial)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 92 of bug id Math85
### Patch Diff Hash-SHA-256:

f7f7112f8f70b476cb586f0cfd3cf3ad62c6d78e9e7428cc211247cf556a9d3c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((((b * b) > 0.0) && (maximumIterations < maximumIterations)) && ((b > b) || (b < b))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 93 of bug id Math85
### Patch Diff Hash-SHA-256:

fdc375a19e8e08a690b553e4b7463244420ae11b1332ce25e42ec0387dbbf259

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (b > b) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 94 of bug id Math85
### Patch Diff Hash-SHA-256:

b73084502453174a1a37e75394a33362418600f759e77ab4fcd1828575f549f3

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (initial > initial) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 95 of bug id Math85
### Patch Diff Hash-SHA-256:

5eb1fddfaaba69b557efd4570f42ffbd3258d43636420f4963e4e99c4428d671

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((a * a) > 0.0) && (numIterations < numIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 96 of bug id Math85
### Patch Diff Hash-SHA-256:

9d176ae61e5cff5f2bbcd2ecc73a2a7581e233ccb5977be7891e58fca1eec3be

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((b * b) > 0.0) && (maximumIterations < maximumIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 97 of bug id Math85
### Patch Diff Hash-SHA-256:

65aa43edd3f14982ba4298776dce9e281fae74faf9befa4be8bce855fc25041c

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (((b * b) > 0.0) && (numIterations < numIterations)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 98 of bug id Math85
### Patch Diff Hash-SHA-256:

fbd1ffe1fabba35fb3c1bc571d56d7391bd4d008a2928443b318deff38f300b0

### Patch Diff:
```
--- /original/org/apache/commons/math/distribution/NormalDistributionImpl.java	
+++ /fixed/org/apache/commons/math/distribution/NormalDistributionImpl.java	
@@ -79,7 +79,7 @@
 		if (p < 0.5) {
 			ret = -(java.lang.Double.MAX_VALUE);
 		}else {
-			ret = getMean();
+			ret = ((mean) - (mean)) / ((mean) * (java.lang.Math.sqrt(2.0)));
 		}
 		return ret;
 	}
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 99 of bug id Math85
### Patch Diff Hash-SHA-256:

c56ced7e19e65ef9e18777e52ad1bc3cc75e02c8d34cbc7d0f3205c7dc86f0e6

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((function.value(a)) >= 0.0) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 100 of bug id Math85
### Patch Diff Hash-SHA-256:

a9cd7f4870e59a3ec06dcf4534722333a44d8d4f6828ff7f47c202856e0e96ae

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((((a * a) > 0.0) && (numIterations < numIterations)) && ((a > a) || (a < a))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 101 of bug id Math85
### Patch Diff Hash-SHA-256:

d2d3e54cca556b9ce131d3532f112e9d509018b1c589dbc4f6c9d3e7c0f99392

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((lowerBound > lowerBound) || (lowerBound < lowerBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 102 of bug id Math85
### Patch Diff Hash-SHA-256:

67cf5716226b38a78b8dde3c6e979788a60959a5a2ecbac00cbdcb07eb6a1456

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((upperBound > upperBound) || (upperBound < upperBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 103 of bug id Math85
### Patch Diff Hash-SHA-256:

22b5bacce3442be9038966df31e1d88f54bc63dce3ab2e77217f1089a11bf743

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((lowerBound > upperBound) || (lowerBound < lowerBound)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 104 of bug id Math85
### Patch Diff Hash-SHA-256:

df43eed1070ce8ef2216c89cf9e8d8c2e835854562d8b272fdfe018f07ab4f67

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((((b * b) > 0.0) && (numIterations < numIterations)) && ((b > b) || (b < b))) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 105 of bug id Math85
### Patch Diff Hash-SHA-256:

471e8a0f13c032383e80afbd275692de6cec976af19b44ced7c919a4b3370164

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (lowerBound < lowerBound) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 106 of bug id Math85
### Patch Diff Hash-SHA-256:

6bdb1e36c0d5790ce2224f62a13080bde0ec032173adfc043cc4597fa16dc802

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (lowerBound > lowerBound) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 107 of bug id Math85
### Patch Diff Hash-SHA-256:

064c275b25fda918286f85b4edf4b532a6c771983411eeaae168ebbc13706c69

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if (upperBound < upperBound) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 108 of bug id Math85
### Patch Diff Hash-SHA-256:

05e1618a3b91d31ff76aafa42e3bd722a3344c3a7eef34081aa44c399d008c37

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((a < 0) && (a > 0)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 109 of bug id Math85
### Patch Diff Hash-SHA-256:

8d92198f275a48f5c0d98c47fb066e6ac74a7ef4d72655f9bb45ee740b989169

### Patch Diff:
```
--- /original/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
+++ /fixed/org/apache/commons/math/analysis/solvers/UnivariateRealSolverUtils.java	
@@ -46,7 +46,7 @@
 			fb = function.value(b);
 			numIterations++;
 		} while ((((fa * fb) > 0.0) && (numIterations < maximumIterations)) && ((a > lowerBound) || (b < upperBound)) );
-		if ((fa * fb) >= 0.0) {
+		if ((a > 0) && (a < 0)) {
 			throw new org.apache.commons.math.ConvergenceException(("number of iterations={0}, maximum iterations={1}, " + ("initial={2}, lower bound={3}, upper bound={4}, final a value={5}, " + "final b value={6}, f(a)={7}, f(b)={8}")), numIterations, maximumIterations, initial, lowerBound, upperBound, a, b, fa, fb);
 		}
 		return new double[]{ a , b };
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---