
# Patches of Math8 from Defects4J 
Total patches 6
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