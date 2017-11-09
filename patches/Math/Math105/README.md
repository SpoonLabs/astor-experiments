
# Patches of Math105 from Defects4J 
Total patches 3
## Patch 1 of bug id Math105
### Patch Diff Hash-SHA-256:

95a9dcc065d21dd4d5ab96f6bf4a63b620afe3d4011d3383631ccdf44fdefa92

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/regression/SimpleRegression.java	
+++ /fixed/org/apache/commons/math/stat/regression/SimpleRegression.java	
@@ -27,7 +27,7 @@
 	}
 
 	public void addData(double x, double y) {
-		if ((n) == 0) {
+		if (((sumXX) < (sumYY)) && ((sumYY) < (xbar))) {
 			xbar = x;
 			ybar = y;
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 2 of bug id Math105
### Patch Diff Hash-SHA-256:

a990f31c560b77ed60ef467baefe6f45d665514ac6ae8d317730a2c1abf85aa9

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/regression/SimpleRegression.java	
+++ /fixed/org/apache/commons/math/stat/regression/SimpleRegression.java	
@@ -27,7 +27,7 @@
 	}
 
 	public void addData(double x, double y) {
-		if ((n) == 0) {
+		if (((sumXX) < (sumYY)) && ((sumYY) < x)) {
 			xbar = x;
 			ybar = y;
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---
## Patch 3 of bug id Math105
### Patch Diff Hash-SHA-256:

fe264443ea3ab4fd2fa6a19a5e8e27ea5305d751d146a5a07f5f630282deb1f6

### Patch Diff:
```
--- /original/org/apache/commons/math/stat/regression/SimpleRegression.java	
+++ /fixed/org/apache/commons/math/stat/regression/SimpleRegression.java	
@@ -27,7 +27,7 @@
 	}
 
 	public void addData(double x, double y) {
-		if ((n) == 0) {
+		if (((sumXX) < (sumXY)) && ((sumXY) < (xbar))) {
 			xbar = x;
 			ybar = y;
 		}else {
```

### Correctness:
Date|Approach|Correctness
------------ | ------------ | -------------
 8/2017 | Cardumen 472e63e3016c7d3255395289f92872a55940cb7f | Original Test-suite adequate

---