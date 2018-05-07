
# Patches of Math74 from Defects4J 
Total patches 5
## Patch 1 of bug id Math74
### Patch Diff Hash-SHA-256:

9d7e5ad75c19c4e91c90412ab28e4324d7e590ffd3354bd4a3b331f4775281d7

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -36,7 +36,7 @@
 		interpolator.reinitialize(stepStart, stepSize, scaled, nordsieck);
 		interpolator.storeTime(stepStart);
 		double hNew = stepSize;
-		interpolator.rescale(hNew);
+		setMaxGrowth(10.0);
 		boolean lastStep = false;
 		while (!lastStep) {
 			interpolator.shift();
```


---
## Patch 2 of bug id Math74
### Patch Diff Hash-SHA-256:

44935a0836f605bbf0f7765093098fe84f54a923942b6feeedc4b7bf2359c480

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -62,6 +62,7 @@
 					}
 					updateHighOrderDerivativesPhase2(predictedScaled, correctedScaled, nordsieckTmp);
 					interpolatorTmp.reinitialize(stepEnd, stepSize, correctedScaled, nordsieckTmp);
+					setMaxGrowth(10.0);
 					interpolatorTmp.storeTime(stepStart);
 					interpolatorTmp.shift();
 					interpolatorTmp.storeTime(stepEnd);
```


---
## Patch 3 of bug id Math74
### Patch Diff Hash-SHA-256:

b2637b4e5b1d87008bab2b1016421f0bccfa1b734e41385c4897396897e6a592

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -45,6 +45,7 @@
 				stepSize = hNew;
 				final double stepEnd = (stepStart) + (stepSize);
 				interpolator.setInterpolatedTime(stepEnd);
+				setMaxGrowth(10.0);
 				java.lang.System.arraycopy(interpolator.getInterpolatedState(), 0, yTmp, 0, y0.length);
 				computeDerivatives(stepEnd, yTmp, yDot);
 				final double[] predictedScaled = new double[y0.length];
```


---
## Patch 4 of bug id Math74
### Patch Diff Hash-SHA-256:

dc6aabf8b641977cc7340ab41a7b9d7ef84944cbe0b8dd844b73e3f61ea4948c

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -19,6 +19,7 @@
 		setEquations(equations);
 		resetEvaluations();
 		final boolean forward = t > t0;
+		setMaxGrowth(10.0);
 		if (y != y0) {
 			java.lang.System.arraycopy(y0, 0, y, 0, n);
 		}
```


---
## Patch 5 of bug id Math74
### Patch Diff Hash-SHA-256:

81c539ff9ba5ba7d2c1f0728f48482c5de634f92a3f93cbd41431a41a1ee0070

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -78,6 +78,7 @@
 						nordsieck = nordsieckTmp;
 						interpolator.reinitialize(stepEnd, stepSize, scaled, nordsieck);
 						loop = false;
+						setMaxGrowth(10.0);
 					}
 				}else {
 					final double factor = computeStepGrowShrinkFactor(error);
```


---