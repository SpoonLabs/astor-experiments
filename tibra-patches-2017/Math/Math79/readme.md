
# Patches of Math79 from Defects4J 
Total patches 5
## Patch 1 of bug id Math79
### Patch Diff Hash-SHA-256:

c5043259605eb74897a6df3eff2490a78e2cc34d3c5d8d37180ebe1a48684b71

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -748,6 +748,9 @@
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
 			final int dp = (p1[i]) - (p2[i]);
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return java.lang.Math.log(sum);
+			}
 			sum += dp * dp;
 		}
 		return java.lang.Math.sqrt(sum);
```


---
## Patch 2 of bug id Math79
### Patch Diff Hash-SHA-256:

749deafcb9c30b60ed9ed2142245c0ba3fbf61316b57a998dfa5c6f7035a3edd

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -748,6 +748,9 @@
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
 			final int dp = (p1[i]) - (p2[i]);
+			if ((dp == 1) || (dp == (sum - 1))) {
+				return java.lang.Math.log(sum);
+			}
 			sum += dp * dp;
 		}
 		return java.lang.Math.sqrt(sum);
```


---
## Patch 3 of bug id Math79
### Patch Diff Hash-SHA-256:

a2725ca835d841117eb91c75e2dd427ffb2eee988dd9f77dd8f25171e89cb5d9

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -748,6 +748,9 @@
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
 			final int dp = (p1[i]) - (p2[i]);
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return sum;
+			}
 			sum += dp * dp;
 		}
 		return java.lang.Math.sqrt(sum);
```


---
## Patch 4 of bug id Math79
### Patch Diff Hash-SHA-256:

286fb3554000ab69c19e133e41adefb8690cfec3bc7f8e5e8610713e25bfea1b

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -747,6 +747,9 @@
 	public static double distance(int[] p1, int[] p2) {
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return java.lang.Math.log(sum);
+			}
 			final int dp = (p1[i]) - (p2[i]);
 			sum += dp * dp;
 		}
```


---
## Patch 5 of bug id Math79
### Patch Diff Hash-SHA-256:

5fb506c5a1cd4b5efed16ed07712d40c8634a8fb76b7a5e71939f6e59671ba2d

### Patch Diff:
```
--- /original/org/apache/commons/math/util/MathUtils.java	
+++ /fixed/org/apache/commons/math/util/MathUtils.java	
@@ -747,6 +747,9 @@
 	public static double distance(int[] p1, int[] p2) {
 		int sum = 0;
 		for (int i = 0; i < (p1.length); i++) {
+			if ((sum == 1) || (sum == (sum - 1))) {
+				return sum;
+			}
 			final int dp = (p1[i]) - (p2[i]);
 			sum += dp * dp;
 		}
```


---