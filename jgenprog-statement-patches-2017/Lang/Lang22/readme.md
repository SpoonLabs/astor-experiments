
# Patches of Lang22 from Defects4J 
Total patches 3
## Patch 1 of bug id Lang22
### Patch Diff Hash-SHA-256:

418d7e7c2c6f72a4400dc305c39082452b7638221500cd334afab7d44114b789

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -286,7 +286,6 @@
 
 	private static int greatestCommonDivisor(int u, int v) {
 		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
-			return 1;
 		}
 		if (u > 0) {
 			u = -u;
```


---
## Patch 2 of bug id Lang22
### Patch Diff Hash-SHA-256:

d1bd204035cbe4bd9b68460d8b0404a7ee5da33ae938a60663a8b9280f5b8d08

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,9 +285,6 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
-			return 1;
-		}
 		if (u > 0) {
 			u = -u;
 		}
```


---
## Patch 3 of bug id Lang22
### Patch Diff Hash-SHA-256:

c6c9230bc91812007e16e57ca0f90fdf0f2ce6e061794ce7d0f10d5a4856ad32

### Patch Diff:
```
--- /original/org/apache/commons/lang3/math/Fraction.java	
+++ /fixed/org/apache/commons/lang3/math/Fraction.java	
@@ -285,8 +285,8 @@
 	}
 
 	private static int greatestCommonDivisor(int u, int v) {
-		if (((java.lang.Math.abs(u)) <= 1) || ((java.lang.Math.abs(v)) <= 1)) {
-			return 1;
+		if (u > 0) {
+			u = -u;
 		}
 		if (u > 0) {
 			u = -u;
```


---