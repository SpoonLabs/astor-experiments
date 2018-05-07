
# Patches of Math78 from Defects4J 
Total patches 1
## Patch 1 of bug id Math78
### Patch Diff Hash-SHA-256:

9954ad5d462b79e463bc7d3ec78002285112477b7a541b035aaa5a917bd62910

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/events/EventState.java	
+++ /fixed/org/apache/commons/math/ode/events/EventState.java	
@@ -69,11 +69,12 @@
 		try {
 			forward = interpolator.isForward();
 			final double t1 = interpolator.getCurrentTime();
-			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (t0)))) / (maxCheckInterval))))));
-			final double h = (t1 - (t0)) / n;
-			double ta = t0;
+			final int n = java.lang.Math.max(1, ((int) (java.lang.Math.ceil(((java.lang.Math.abs((t1 - (this.t0)))) / (maxCheckInterval))))));
+			final double h = (t1 - (this.t0)) / n;
+			double ta = this.t0;
 			double ga = g0;
-			double tb = (t0) + (interpolator.isForward() ? convergence : -(convergence));
+			double tb = (this.t0) + (interpolator.isForward() ? convergence : -(convergence));
+			ta = tb;
 			for (int i = 0; i < n; ++i) {
 				tb += h;
 				interpolator.setInterpolatedTime(tb);
```


---