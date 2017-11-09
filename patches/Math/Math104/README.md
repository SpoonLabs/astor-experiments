
# Patches of Math104 from Defects4J 
Total patches 2
## Patch 1 of bug id Math104
### Patch Diff Hash-SHA-256:

470db9b2586a8b37ad9e320ca622171549ead082bc92992336ffd4d05598dfaa

### Patch Diff:
```
--- /original/org/apache/commons/math/special/Gamma.java	
+++ /fixed/org/apache/commons/math/special/Gamma.java	
@@ -51,7 +51,7 @@
 					double n = 0.0;
 					double an = 1.0 / a;
 					double sum = an;
-					while (((java.lang.Math.abs(an)) > epsilon) && (n < maxIterations)) {
+					while (an != 0) {
 						n = n + 1.0;
 						an = an * (x / (a + n));
 						sum = sum + an;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math104
### Patch Diff Hash-SHA-256:

b2065b2e1fce9999539ee9c3617cc1d109bd8a8563b2d5b3a092c535b0092616

### Patch Diff:
```
--- /original/org/apache/commons/math/special/Gamma.java	
+++ /fixed/org/apache/commons/math/special/Gamma.java	
@@ -51,7 +51,7 @@
 					double n = 0.0;
 					double an = 1.0 / a;
 					double sum = an;
-					while (((java.lang.Math.abs(an)) > epsilon) && (n < maxIterations)) {
+					while (an > 0) {
 						n = n + 1.0;
 						an = an * (x / (a + n));
 						sum = sum + an;
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---