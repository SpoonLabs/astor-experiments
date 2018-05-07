
# Patches of Math39 from Defects4J 
Total patches 1
## Patch 1 of bug id Math39
### Patch Diff Hash-SHA-256:

4cf1704a853cd8b3930a71489767a319d5a7dae05880d71cb603aa6a2abdc4ce

### Patch Diff:
```
--- /original/org/apache/commons/math/ode/nonstiff/EmbeddedRungeKuttaIntegrator.java	
+++ /fixed/org/apache/commons/math/ode/nonstiff/EmbeddedRungeKuttaIntegrator.java	
@@ -108,6 +108,9 @@
 						yTmp[j] = (y[j]) + ((stepSize) * sum);
 					}
 					computeDerivatives(((stepStart) + ((c[(k - 1)]) * (stepSize))), yTmp, yDotK[k]);
+					if ((forward && (((stepStart) + (stepSize)) > t)) || ((!forward) && (((stepStart) + (stepSize)) < t))) {
+						stepSize = t - (stepStart);
+					}
 				}
 				for (int j = 0; j < (y0.length); ++j) {
 					double sum = (b[0]) * (yDotK[0][j]);
```


---