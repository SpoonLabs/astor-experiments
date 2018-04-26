
# Patches of Math74 from Defects4J 
Total patches 2
## Patch 1 of bug id Math74
### Patch Diff Hash-SHA-256:

927d46aa5fc8b3e81593fdf43f7dd989be8a44e99a277f45e71b695fa3948b43

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/MultistepIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/MultistepIntegrator.java	
@@ -110,7 +110,7 @@
 			final double prev = interpolator.getPreviousTime();
 			final double curr = interpolator.getCurrentTime();
 			stepStart = prev;
-			stepSize = (curr - prev) / ((nSteps) + 1);
+			stepSize = (curr - prev) / ((n) + 1);
 			interpolator.setInterpolatedTime(prev);
 			scaled = interpolator.getInterpolatedDerivatives().clone();
 			for (int j = 0; j < (n); ++j) {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math74
### Patch Diff Hash-SHA-256:

338d1665eee129f08fa3d9eb62de7cb0fb426b61e7a2dbbd369e3d20910d0955

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/AdamsMoultonIntegrator.java	
@@ -91,7 +91,7 @@
 			manager.stepAccepted(nextStep, y);
 			lastStep = manager.stop();
 			for (org.apache.commons.math.ode.sampling.StepHandler handler : stepHandlers) {
-				interpolator.setInterpolatedTime(nextStep);
+				setMaxGrowth(10.0);
 				handler.handleStep(interpolator, lastStep);
 			}
 			stepStart = nextStep;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---