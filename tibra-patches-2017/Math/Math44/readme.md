
# Patches of Math44 from Defects4J 
Total patches 1
## Patch 1 of bug id Math44
### Patch Diff Hash-SHA-256:

b99f25eb65212fb8244b68de53465793c3f2a1e50c2f7eb4af43d273ad6173d9

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -77,6 +77,7 @@
 
 	public boolean evaluateStep(final org.apache.commons.math.ode.sampling.StepInterpolator interpolator) throws org.apache.commons.math.exception.ConvergenceException {
 		forward = interpolator.isForward();
+		t0 = interpolator.getPreviousTime();
 		final double t1 = interpolator.getCurrentTime();
 		final double dt = t1 - (t0);
 		if ((org.apache.commons.math.util.FastMath.abs(dt)) < (convergence)) {
```


---