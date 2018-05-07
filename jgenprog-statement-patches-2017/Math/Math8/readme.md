
# Patches of Math8 from Defects4J 
Total patches 2
## Patch 1 of bug id Math8
### Patch Diff Hash-SHA-256:

c2a62f636361bfeb7c6add9f084790d1addf32a1e32667167caddddd2411af9d

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -68,9 +68,6 @@
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
## Patch 2 of bug id Math8
### Patch Diff Hash-SHA-256:

cf6e0a4996f72a7bfd9bbc0f7499576e89634309fc8094cb86c4ab8f95a91c3c

### Patch Diff:
```
--- /original/org/apache/commons/math3/distribution/DiscreteDistribution.java	
+++ /fixed/org/apache/commons/math3/distribution/DiscreteDistribution.java	
@@ -69,7 +69,6 @@
 		}
 		final T[] out = ((T[]) (java.lang.reflect.Array.newInstance(singletons.get(0).getClass(), sampleSize)));
 		for (int i = 0; i < sampleSize; i++) {
-			out[i] = sample();
 		}
 		return out;
 	}
```


---